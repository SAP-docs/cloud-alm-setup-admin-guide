<!-- loiobd998fbd4a3943d98c49cca895c462ee -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Integration Suite \(Cloud Integration\) on Cloud Foundry

This page explains how to connect SAP Integration Suite \(Cloud Integration\) on Cloud Foundry to SAP Cloud ALM to enable monitoring.

Currently, SAP Integration Suite \(Cloud Integration\) supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)

The following video demonstrates the setup for application monitoring for SAP Integration Suite \(Cloud Integration\). A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loiobd998fbd4a3943d98c49cca895c462ee__section_nyn_x5d_bhc"/>

## Prerequisites

You have access to the SAP BTP cockpit and an entitlement for the service *Process Integration Runtime* for the plan *api*. You can check this in the SAP BTP cockpit under *Subaccount for Integration Suite* \> *Entitlements*.

Your user in the SAP BTP cockpit is a member with the space role *Space Developer*, for the space where you want to create the service instance.



<a name="loiobd998fbd4a3943d98c49cca895c462ee__section_pfq_z5d_bhc"/>

## Setup in SAP Integration Suite \(Cloud Integration\)

To enable OAuth authentication between SAP Cloud ALM and SAP Integration Suite \(Cloud Integration\), create an instance with a service key for the *Process Integration* service with the necessary authorizations.



### Create Service Instance

1.  Go to the SAP BTP cockpit and access the sub-account used for SAP Cloud Integration.
2.  Go to *Instances and Subscriptions*.
3.  Choose *Create* to create a new instance.
4.  Basic Info:
    1.  *Service*: *Process Integration \(it-rt\)*
    2.  *Plan*: *api*
    3.  *Runtime Environment*: *Cloud Foundry*
    4.  *Space*: Select the appropriate space, depending on your company.
    5.  *Instance Name*: Enter an instance name.
    6.  Choose *Next*

5.  Under *Parameters*, select the roles:
    -   For *Integration and Exception Monitoring*: *MonitoringDataRead* and *MonitoringArtifactsDeploy*.
    -   For *Health Monitoring*: *HealthCheckMonitoringDataRead*

6.  Choose *Create* to create the instance.



### Create Service Key

1.  Select the row of the instance.
2.  Go to the *Service Keys* tab.
3.  Choose *Create*.
4.  Enter a name for the service key.
5.  Choose *Create*.

Download the service key file. You need it when you create the endpoint in SAP Cloud ALM.



<a name="loiobd998fbd4a3943d98c49cca895c462ee__section_vnb_pwd_bhc"/>

## Setup in SAP Cloud ALM

Ensure that your cloud service has been imported from the System Landscape Information Service \(SLIS\) to SAP Cloud ALM. This is a daily, automatic synchronization.

If you have more than one entry with the same name in the *Landscape Management* app in SAP Cloud ALM, choose the one for which the tenant and the host part of the root URL match the parameter "url" in the service key.

You can use the same endpoint for all supported use cases.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Select your cloud service SAP Integration Suite \(Cloud Integration\).

    Do not choose the service with the service type *SAP BTP Cloud Foundry environment* even if the cloud service name contains *Cloud Platform Integration*.

3.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
4.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
5.  Enter a description.
6.  Select the use-cases you want to use in SAP Cloud ALM, for example *Health Monitoring*.

    For Integration and Exception Monitoring, select *Integration Monitoring* and *Exception Monitoring*.

7.  Overwrite the value in the *Root URL* field with the value of the *url* parameter in the service key.
8.  Choose *OAuth2ClientCredentials*: Enter the following values from the SAP Integration Suite service key:
    1.  *Client ID*: *clientid*
    2.  *Client Secret*: *clientsecret*
    3.  *Token Service URL*: *tokenurl*

9.  Save your endpoint.



### Activate the Service in the Monitoring App

After creating the endpoint in SAP Cloud ALM, activate the data collection:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)

