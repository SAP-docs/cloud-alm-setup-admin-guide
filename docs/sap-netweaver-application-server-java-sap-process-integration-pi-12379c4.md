<!-- loio12379c4ab565457e87c70d8d2b6b2169 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP NetWeaver Application Server Java \(SAP Process Integration, PI\)

This page explains how to connect SAP NetWeaver Application Server Java to SAP Cloud ALM to enable monitoring.

SAP NetWeaver AS Java was formerly known as SAP Process Integration \(PI\).

Currently, SAP NetWeaver AS for Java supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio12379c4ab565457e87c70d8d2b6b2169__section_o3t_d4t_bhc"/>

## Prerequisites

We only support **PI message monitoring** for SAP NetWeaver AS Java systems.

SAP Cloud ALM only support PI message monitoring for SAP NetWeaver AS Java systems. You can only connect your SAP NetWeaver AS Java systems to SAP Cloud ALM if they're systems for **SAP Process Integration** or **SAP Process Orchestration**.

You've installed the Cloud Connector in your SAP NetWeaver AS Java system network as described under [Installation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/LATEST/en-US/57ae3d62f63440f7952e57bfcef948d3.html).



## Setup in Cloud Connector



### Connect the SAP Cloud ALM Subaccount

1.  In the Cloud Connector, go to the *Cloud Connector Administration* page.
2.  On the *Connector* page, choose *Add Subaccount*.
3.  Connect your SAP Cloud ALM tenant.

If the SAP Cloud ALM tenant is the first subaccount in this cloud connector, you're automatically forwarded to the *First Subaccount* page.



### Add Connection to SAP System

1.  Go to *Cloud Connector Administration* \> *SAP Cloud ALM tenant* \> *Cloud To On-Premise* \> *ACCESS CONTROL*.
2.  Choose :heavy_plus_sign: to add a new entry.
3.  Select *Back-end Type*: *SAP Application Server Java*.
4.  Choose *Finish*.
5.  Select the entry for your new system.
6.  Note down the value of the column *Virtual Host* for later use.
7.  In the section *Resources Of SAP system*, choose :heavy_plus_sign:. Enter the following values:
    1.  *URL Path*: `/mdt_soa/frun` with *Access Policy*: *Path And All Sub-Paths*
    2.  *URL Path*: */AdapterMessageMonitoring/basic* with *Access Policy*: *Path And All Sub-Paths*

8.  Choose *Save*.



### Verify SAP Web Dispatcher Rules

If you use an SAP Web Dispatcher in your landscape, ensure that the requests can be routed successfully.

To connect successfully to the SAP system, verify that the following paths are permitted in your Web Dispatcher:

-   `/mdt_soa/frun/*`
-   `/AdapterMessageMonitoring/basic/*`



## Setup in SAP NetWeaver AS Java



### Create a Technical User

Create a technical user for data collection and assign a custom copy of the following SAP roles:

1.  To collect PI monitoring data: *SAP\_XI\_MONITOR\_J2EE* and *NWA\_READONLY*.
2.  To collect message payload: *XI\_FRUN\_GET\_MSG* \(Available with SAP PI 7.31 SP17+, SAP PI 7.40 SP12+, and SAP PI 7.50 SP05+\).

These roles are available only in SAP NetWeaver AS Java with usage type *SAP Process Integration to SAP Process Orchestration* 



<a name="loio12379c4ab565457e87c70d8d2b6b2169__section_gll_mrt_bhc"/>

## Setup in SAP Cloud ALM



### Add SAP NetWeaver AS Java to Landscape Management

> ### Note:  
> If your SAP Process Integration system is hosted by SAP ECS, for example as part of your RISE with SAP journey, it's automatically discovered and imported into SAP Cloud ALM. The system is imported with the system type *SAP NetWeaver AS for Java*.
> 
> You don't need to create a system manually in the *Landscape Management* app. In this case, proceed to the next section to create the endpoint for data collection.

1.  In SAP Cloud ALM open the *Landscape Management* app and open the *Services and Systems* view.
2.  Choose :heavy_plus_sign:.
3.  Enter:
    1.  *Product*: Select *SAP NetWeaver AS for Java*.
    2.  *System ID*: The SID of the SAP Process Integration system.
    3.  *Role*: Select the correct system role.
    4.  *Virtual Host and Port*: The value from the field *Virtual Host* maintained for the SAP system in Cloud Connector, which you've gotten during the Cloud Connector setup described earlier.
    5.  *Logon URL*: The actual URL for the SAP system \(host and HTTPS port\). Only HTTPS is supported as URL type.

4.  *System Number*: The SAP system number.
5.  *Installation Number*: The installation number.
6.  Choose *Save*.



### Create HTTP Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Select your *SAP Netweaver AS for Java* system.
3.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
4.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
5.  Enter a description.
6.  Choose the use case *Integration Monitoring*.

    The value for *Virtual Host and Port* is filled automatically.

7.  *Cloud Connector Location ID*: Enter the name \(description\) of the Cloud Connector instance that you want to use. You find this information in your Cloud Connector or in the SAP BTP Cockpit in the SAP Cloud ALM subaccount, under *Connectivity* \> *Cloud Connectors*. The location ID is the value in parenthesis next to the phrase *Master Instance* for the Cloud Connector that you want to use. If you only have one Cloud Connector, this value can be empty.
8.  Under *Authentication*, enter:
    1.  *Authentication Type*: *Basic Authentication*.
    2.  *User*: The technical user created in SAP Process Integration \(Java\) for this purpose.
    3.  *Password*: The password for the user.

9.  Choose *Save* the endpoint.

> ### Note:  
> Endpoint Check for SAP NetWeaver AS Java Endpoint
> 
> Since SAP Cloud ALM currently only supports PI message monitoring, the endpoint check verifies that the connected SAP NetWeaver AS Java system has indeed the usage type *SAP Process Integration or SAP Process Orchestration*.
> 
> If you connect a SAP NetWeaver AS Java system with another usage type, the endpoint check fails.



### Activate Monitoring Data Collection

After creating the endpoint in SAP Cloud ALM, you have to perform the following steps to activate the monitoring use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

