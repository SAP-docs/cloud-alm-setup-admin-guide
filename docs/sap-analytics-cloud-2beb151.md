<!-- loio2beb151850fd4e989ed9b3672b89b18c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Analytics Cloud

This document provides guidance on connecting SAP Analytics Cloud to SAP Cloud ALM for monitoring purposes.

Currently, SAP Analytics Cloud supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



## Prerequisites

To enable SAP Analytics Cloud for monitoring with SAP Cloud ALM, you need a user with administrator authorizations in SAP Analytics Cloud.



## Setup in SAP Analytics Cloud



### Determine your Environment

Before starting the setup, determine whether your SAP Analytics Cloud tenant is running in an SAP or non-SAP data center.

-   SAP data centers run on the SAP BTP Neo environment.
-   Non-SAP data centers, such as AWS or Azure, run in the Cloud Foundry environment.

1.  Open the *Landscape Management* application from the launchpad.
2.  Select your SAP Analytics Cloud service.
3.  Under *Details*, find the value for *Infrastructure Provider*:
    -   SAP: SAP data center
    -   AWS, Azure, and so on: non-SAP data center




### SAP Analytics Cloud running in an SAP Data Center or non-SAP Data Center \(Neo\)

Only Exception Monitoring is supported.

1.  In the SAP Analytics Cloud launchpad, navigate to the *System* \> *Administration* view in the navigation panel.
2.  Copy the *Token URL*. You need this later in SAP Cloud ALM.
3.  Under *Configured Clients*, choose *Add a New OAuth Client*.
    -   *Name*: Enter a name, such as `SAP Cloud ALM integration`.
    -   *Purpose*: *API Access*
    -   *Access*: *Monitoring*

4.  Under *Security*, enter:
    -   *Authorization Grant*: *Client Credentials*
    -   *Secret*: Enter the password and note it down for later use.

5.  Set the *Token Lifetime* to 1 hour.
6.  Copy the *OAuth Client ID*.
7.  Choose *Save*.



### SAP Analytics Cloud running in an SAP data center or non-SAP data center \(Cloud Foundry\)

1.  In the SAP Analytics Cloud launchpad, navigate to *System* \> *App Integration*, in the navigation panel.
2.  Copy the *Token URL*. You needNow, you this later in SAP Cloud ALM.
3.  Under *Configured Clients*, choose *Add a New OAuth Client*.
    -   *Name*: Enter a name, such as SAP Cloud ALM integration.
    -   *Purpose*: API Access
    -   *Access*: Monitoring
    -   *Authorization Grant*: Client credentials

4.  Choose *Add*.
5.  Copy the *OAuth Client ID*.
6.  Choose *Show Secret*.
7.  Copy the secret.
8.  Choose *Done*.



## Setup in SAP Cloud ALM

Now you need to create the endpoint in SAP Cloud ALM, tenant, to enable data collection.

You can add several use-cases to one endpoint. If there's already an endpoint created for one use-case, you can add an additional endpoint for an additional use-case.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  Enter the main URL in the *Root URL* field if it isn't prefilled.
7.  Choose *OAuth2ClientCredentials* and enter the following values:
    -   *Client ID*: OAuth Client ID
    -   *Client Secret*: secret
    -   *Token Service URL*: Token URL
    -   *Token Service User*: OAuth Client ID \(automatically filled, only needed for SAP Neo data centers\)
    -   *Token Service Password*: secret \(automatically filled, only needed for SAP Neo data centers\)

8.  Save your endpoint.



## Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

