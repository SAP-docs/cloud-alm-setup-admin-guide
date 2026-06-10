<!-- loiod122ae8bc64840a4810137b2bc0c4840 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Field Service and Asset Management

This page explains how to connect SAP Field Service and Asset Management to SAP Cloud ALM to enable monitoring.

Currently, SAP Field Service and Asset Management supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Field Service Management](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-fsm.html).


The following video demonstrates the setup steps for Integration and Exception Monitoring for SAP Field Service and Asset Management. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loiod122ae8bc64840a4810137b2bc0c4840__section_dtd_vtn_zgc"/>

## Prerequisites

You have a user with administrator authorizations on *account-level*.

Log on to your SAP Field Service and Asset Management account with the option "Sign In with Account"

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Field Service Management](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-fsm.html).



<a name="loiod122ae8bc64840a4810137b2bc0c4840__section_mnv_y5n_zgc"/>

## Setup in SAP Field Service and Asset Management

By default, Integration Monitoring is disabled in SAP Field Service and Asset Management. Before you can access the data with SAP Cloud ALM, monitoring needs to be activated.

Activate Integration Monitoring for the connector you use for your company. Which connector is used depends on the product SAP Field Service and Asset Management integrates with:

-   SAP ERP or SAP Business One: *ERP Connector*
-   SAP S/4HANA or SAP Sales and Services Cloud: *FSM Connector*

1.  Log on to your main account page in SAP Field Service and Asset Management.

    Make sure to choose *Sign In with Account*.

2.  Choose the company name in the *Companies* panel.
    1.  For the *ERP Connector*:
        1.  Go to *ERP Connector*.
        2.  Change the value for *Integration Monitoring* from *false* to *true*.

    2.  For the *FSM Connector*:
        1.  Go to *FSM Integrations* \> *FSM Connector*.
        2.  Check the box next to *Integration Monitoring enabled*.





### Activate Integration Monitoring in SAP Field Service and Asset Management

Create the OAuth credentials with client ID and client secret:

1.  Log on to your main account page in SAP Field Service and Asset Management.

    Make sure to choose *Sign In with Account*.

2.  Go to the *Clients* section.
3.  Choose *Create*.
4.  Ensure the *Client Authentication Method* is set to *CLIENT\_SECRET*.
5.  In the *User Groups* section:
    1.  Find the companies for which you want to use this OAuth client.
    2.  Change the value in the drop-down list to *Admin \(pre-configured\)*.

6.  Choose *Save*.
7.  Copy the client ID and the client Secret for the next step.



## Setup in SAP Cloud ALM

Create an endpoint in SAP Cloud ALM:

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  Adjust the entry for *Root URL*. To access the backend API, enter the URL for your region, without any trailing path, as found under [Full Migration List from Old to New Domains](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_product_announcements/sap-superdomain-for-fsm.html#full-migration-list-from-old-to-new-domains).

    You can find your region under the properties of the service in the *Landscape Management* app.

7.  Choose *OAuth2ClientCredentials* and enter the OAuth credentials retrieved from SAP Field Service and Asset Management:
    -   *Client ID*: Enter the client ID.
    -   *Client Secret*: Enter the client secret.
    -   *Token Service URL*: `https://{cluster}.fsm.cloud.sap/api/oauth2/v2/token`. More under [Get Access Token](https://help.sap.com/docs/SAP_FIELD_SERVICE_MANAGEMENT/fsm_access_api/get-access-token.html).




## Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use-cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

