<!-- loio1429ec8c56a04ae6969db6a94a6ace73 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Integration Suite \(Cloud Integration\) on Neo

This page explains how to connect SAP Integration Suite \(Cloud Integration\) on Neo to SAP Cloud ALM to enable monitoring.

Currently, SAP Integration Suite \(Cloud Integration\) supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)

The following video demonstrates the setup for application monitoring for SAP Integration Suite \(Cloud Integration\) on Neo. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loio1429ec8c56a04ae6969db6a94a6ace73__section_nyn_x5d_bhc"/>

## Prerequisites

You have access to the SAP BTP cockpit and a user with the *Administrator* role.

In SAP Cloud ALM, you have a user with the role *Integration Monitoring Integration Architect*.



<a name="loio1429ec8c56a04ae6969db6a94a6ace73__section_pfq_z5d_bhc"/>

## Setup in SAP Integration Suite \(Cloud Integration\)

If you want to use OAuth authentication to connect to SAP Integration Suite \(Cloud Integration\) on Neo, create a client with the necessary authorizations.



### Create OAuth Client

1.  In the SAP BTP cockpit, navigate to *Applications* \> *Subscriptions*.
2.  Note down the *Provider Subaccount* for the application. It has the ending `tmn`.
3.  Choose *Security* \> *OAuth*
4.  On the *Clients* tab, choose *Register New Client* and define the following:
    1.  Choose a name
    2.  Set the subscription to the CPI tenant. It ends with `tmn`.
    3.  Generate an ID. We recommend using the suggested unique ID.
    4.  For *Authorization Grant* , select Client Credentials.
    5.  Choose a secret.
    6.  Set the *Token Lifetime* to 60 minutes \(or once per hour\).
    7.  Save.

5.  Note down the client ID and the client secret for later use inSAP Cloud ALM
6.  On the *Branding* tab, note down the *Token Endpoint* URL.



### Assign Roles for SAP Cloud ALM Monitoring

You can use the same client ID for all supported use cases. Make sure to select the appropriate roles for the client ID.

1.  In the SAP BTP cockpit, navigate to *Security* \> *Authorizations*
2.  As a user, enter `oauth_client_<client_ID>`. This is the client ID generated in the previous step.
3.  Grant the user the roles: You find the roles under the correct provider sub-account for the application. The sub-account ends with `tmn`.
    1.  For Integration and Exception Monitoring, assign the roles *IntegrationOperationsServer.read* and *NodeManager.read*.
    2.  For **Health Monitoring**, assign the role *HealthCheckMonitoringData.Read*.

4.  Save your changes.



<a name="loio1429ec8c56a04ae6969db6a94a6ace73__section_vnb_pwd_bhc"/>

## Setup in SAP Cloud ALM

Ensure that your cloud service has been imported from the System Landscape Information Service \(SLIS\) to SAP Cloud ALM. This is a daily, automatic synchronization.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Select your cloud service with the type *SAP Integration Suite \(Cloud Integration\)*. The cloud service name is the tenant ID.

    > ### Note:  
    > Do not choose the service with the service type *SAP BTP Neo environment* even if the cloud service name contains *Cloud Platform Integration*.

3.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
4.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
5.  Enter a description.
6.  Select the use-case you want to use in SAP Cloud ALM, for example *Health Monitoring*.

    For Integration and Exception Monitoring, select *Integration Monitoring* and *Exception Monitoring*.

7.  Ensure that the *Root URL* does **not** contain `/itspaces`.
8.  Choose *OAuth2ClientCredentials* and fill all fields:

    1.  *Client ID*: OAuth *clientid*
    2.  *Client Secret*: *clientsecret*
    3.  *Token Service URL*: token endpoint URL
    4.  *Token Service User*\*: oauth client ID
    5.  *Token Service Password*\*: client secret

    \* Note that you have to add the API client ID and password also to the user and password for the Token Service, for the Exception Management endpoint.

9.  Save your endpoint.



### Activate the Service in the Monitoring App

After creating the endpoint in SAP Cloud ALM, activate the data collection:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)

