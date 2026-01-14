<!-- loio0eede18f658f4ab0a9c4d0a2e45a1857 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Fieldglass

This page explains how to connect SAP Fieldglass to SAP Cloud ALM to enable monitoring.

Currently, SAP Fieldglass supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)

The following video demonstrates the setup steps for Integration and Exception Monitoring for SAP Fieldglass. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loio0eede18f658f4ab0a9c4d0a2e45a1857__section_m4n_dbf_zgc"/>

## Prerequisites

-   You have a user with *Fieldglass Configuration Manager* authorization.
    -   For temporary access, your SAP Fieldglass administrator can link this user to your personal user.
    -   In rare cases, no user from your company has access to the *API Application Key* application. In this case, create a case with SAP on component BNS-FG-FAS.

-   You have a user in SAP Fieldglass that you can use in the web service that was created for the API application key.

    Do not use a personal user for this purpose.




## Setup in SAP Fieldglass



### Create API Key and Web Service

1.  Log on to SAP Fieldglass.
2.  Switch to the configuration manager user:

    Choose your user icon in the upper right corner and choose *Linked Accounts*.

3.  Open the *Create Api Application Key* application.
4.  Enter an application name and an application description.
5.  Choose *Create*.
6.  Under *Setup Web Service*, choose *New*.
7.  Select the user created for this web service from the drop-down field for *Virtual Person Name*.
8.  Set the status to *Enabled*.
9.  Save the web service.



### Obtain OAuth Connection Information

1.  Open the *View Api Application Key* application.
2.  Retrieve the following information from the *API Application Keys* table:

    *Api Application Key* for the application for the SAP Cloud ALM integration.

3.  Retrieve the following information from the *Web Services* table:
    -   The *License Key* for the user you created for the integration.
    -   The *Username* in the column *Virtual Person Name \(Username\)* for the user you created for the integration.

4.  Do not use the *Client ID* and the *Client Secret* that are provided in the *API Application Key* application. They aren't applicable for SAP Cloud ALM endpoints. Instead, SAP Cloud ALM uses the following information:
    -   The *Virtual Person Name* used as the *Client ID* in SAP Cloud ALM.
    -   The *License Key* used as the *Client Secret* phrase in SAP Cloud ALM.




<a name="loio0eede18f658f4ab0a9c4d0a2e45a1857__section_nc4_3cf_zgc"/>

## Setup in SAP Cloud ALM



### Create Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  Choose *OAUTH* authentication and enter the OAuth credentials that you retrieved from SAP Fieldglass:
    -   *Client ID*: Enter the *Virtual Person Name*.
    -   *Client Secret*: Enter the *License Key*.
    -   *Token Service URL*: Extend your SAP Fieldglass root URL with `/api/oauth2/v2.0/token?grant_type=client_credentials&response_type=token`.
    -   *API Key*: Enter the *API Application Key*.




### Activate Monitoring Data Collection

After creating the endpoint in SAP Cloud ALM, you need to activate the monitoring use-cases:

-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

