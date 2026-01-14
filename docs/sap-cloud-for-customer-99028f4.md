<!-- loio99028f4fd0f54057ad38ecd29c23e000 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Cloud for Customer

This page explains how to connect SAP Cloud for Customer to SAP Cloud ALM to enable monitoring.

Currently, SAP Cloud for Customer supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio99028f4fd0f54057ad38ecd29c23e000__section_imr_p1w_xgc"/>

## Prerequisites

You have a user with administrator authorizations in SAP Cloud for Customer.



<a name="loio99028f4fd0f54057ad38ecd29c23e000__section_yq3_4bw_xgc"/>

## Setup in SAP Cloud for Customer



### Create Communication Systems

Perform this activity in your SAP Cloud for Customer tenant.

1.  In the navigation panel of the SAP Cloud for Customer launchpad, choose *Administrator* \> *General Settings*.

2.  Choose *Communication Systems* under *Integration*.

3.  Choose *New* to create a new communication system.

    -   ID: Enter, for example, "CRUN" or the SAP Cloud ALM tenant name.

    -   *Host Name*: You can find the host name of your SAP Cloud ALM tenant in the SAP Cloud ALM URL, for example, `eu10.alm.cloud.sap`.

    -   *System Access Type*: Choose *Internet*.


4.  Choose *Add Row* to create a new system instance.

    -   *System Instance ID*: Enter, for example, `CRUN_WS`.

    -   *Preferred Application Protocol*: Choose *Web Service*.


5.  Choose *Add Row* to create a new system instance.

    -   *System Instance ID*: Enter, for example, `CRUN_HTTP`.

    -   *Preferred Application Protocol*: Choose *Http*.


6.  Choose *Add Row* to create another new system instance.

    -   *System Instance ID*: Enter, for example, `CRUN_ODATA`.

    -   *Preferred Application Protocol*: Choose *Web Service*.


7.  Choose *Save* to save the communication system.

8.  Activate the communication system with *Actions* \> *Set to Active*.




## For Real User Monitoring: Expose Data Sources for OData Services

The activities in this section are necessary only if you want to set up Real User Monitoring. Perform these activities in your SAP Cloud for Customer tenant.

If not already done, allow the OData exposure for data sources in your SAP Cloud for Customer tenant.



### Allow OData Exposure for Data Sources

1.  In navigation panel of the SAP Cloud for Customer launchpad, choose *Business Configuration* \> *Implementation Projects*.

2.  Select your implementation project.

3.  Choose *Edit Project Scope*.

4.  Choose *Next* to navigate to *Questions*.

    -   Under *All Elements*, choose *Built-in Services and Support* \> *System Management* \> *Analytics*.

    -   Check the box for *In Scope*, next to the question *Do you want to enable analytical OData services for data sources?*.

    -   Choose *Next*.

    -   In the popup, choose *Accept Preselected Answers*.


5.  Choose *Finish*.

6.  Choose *Close*.




### Expose the Data Source for Response Time Analysis

1.  In navigation panel of the SAP Cloud for Customer launchpad, choose *Business Analytics* \> *Design Data Sources*.

2.  Search for the data source with the name *Response Time Analysis* and select it.

3.  Choose *Expose*.

4.  Switch to Yes for *Expose for OData*.

5.  Choose *OK*.




## Create Communication Arrangements

Perform this task in your SAP Cloud for Customer tenant.



### For Integration and Exception Monitoring: Create the Communication Arrangement

1.  In navigation panel of the SAP Cloud for Customer launchpad, choose *Administrator* \> *General Settings*.

2.  Choose *Integration* \> *Communication Arrangements*.

3.  Choose *New* to create a communication arrangement.

4.  *Select Scenario*: Choose *Query Webservice Messages for Monitoring*.

5.  *Define Business Data*: Select the *CRUN\_WS* communication system instance.

6.  Define technical data:

    -   *Communication Method*: *Direct Connection*
    -   *Application Protocol*: *Web Service*
    -   *Authentication Method*: *Basic Authentication*
    -   *User ID*: Choose *Edit Credentials* to maintain user and password

7.  Review and Confirm.




### For Real User Monitoring: Create Communication Arrangement

1.  In navigation panel of the SAP Cloud for Customer launchpad, choose *Administrator* \> *General Settings*.

2.  Choose *Integration* \> *Communication Arrangements*.

3.  Choose *New* to create a communication arrangement.

4.  *Select Scenario*: Choose *Analytics DataSources OData*.

5.  *Define Business Data*: Select the *CRUN\_HTTP* communication system instance.

6.  Define technical data:

    -   *Communication Method*: *Direct Connection*
    -   *Application Protocol*: *Web Service*
    -   *Authentication Method*: *User ID and Password*
    -   *User ID*: Choose *Edit Credentials* to maintain user and password

7.  Review and Confirm.




### For Business Process Monitoring: Create Communication Arrangement

1.  In navigation panel of the SAP Cloud for Customer launchpad, choose *Administrator* \> *General Settings*.

2.  Choose *Integration* \> *Communication Arrangements*.

3.  Choose *New* to create a communication arrangement.

4.  *Select Scenario*: Choose *OData Services for Business Objects*.

5.  *Define Business Data*: Select the *CRUN\_ODATA* communication system instance.

6.  Define technical data:

    -   *Communication Method*: *Direct Connection*
    -   *Authentication Method*: *User ID and Password*
    -   *User ID*: Choose *Edit Credentials* to maintain user and password.
    -   *Services Used*: Select *opportunity*, *salesorder*, *lead*, and *ticket*.

7.  Review and Confirm.




## Setup in SAP Cloud ALM

Perform this activity in your SAP Cloud ALM tenant.

Integration and Exception Monitoring, Real User Monitoring, and Business Process Monitoring use different APIs to collect their monitoring data. **Create a dedicated endpoint for each of the use cases**, which means you perform the following steps once, for each use case:

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose one of the use cases: Integration and Exception Monitoring, Real User Monitoring, or Business Process Monitoring.
6.  Choose *BASIC* authentication
7.  Enter the user and password that you created in the communication agreement.
8.  Save your endpoint.



## Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use-cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

