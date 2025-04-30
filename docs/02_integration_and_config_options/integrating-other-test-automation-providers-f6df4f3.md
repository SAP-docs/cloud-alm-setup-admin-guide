<!-- loiof6df4f3c3c994b6e9714cbe1fe217506 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrating Other Test Automation Providers

You can integrate automated test cases from any external test automation provider that has implemented our public [Test Automation API](https://api.sap.com/api/CALM_TEST_AUTOMATION/overview).



<a name="loiof6df4f3c3c994b6e9714cbe1fe217506__section_w5v_kcx_x4b"/>

## Prerequisites

-   Your user in SAP Cloud ALM has the role *Global Administrator*.

-   You have a user in the automation provider tool.




<a name="loiof6df4f3c3c994b6e9714cbe1fe217506__section_tg2_sbx_x4b"/>

## Procedure

1.  On the *Administration* page of the SAP Cloud ALM launchpad, open the *Landscape Management* app.

2.  In the <span class="SAP-icons-V5"></span> *Select a Scope* dialog, make sure that the service type *Test Automation* is selected.

3.  On the *Services & Systems* page, choose *Add* \> *New Service* and enter the following parameters:

    -   *Name*: Enter a name that follows a naming convention that fits your organization.

        Please note that spaces and special characters other than hyphens and underscores aren't allowed.

    -   *Description*: Enter a short description.

    -   *System Number*: Enter a unique identifier for the automation provider, such as the tenant ID or your customer number.

    -   *Service Type*: Select `Test Automation`.

    -   *Role*: Select `Test`.

    -   *Root URL*: Enter the root URL of your automation provider application.

    -   *Deployment Model*: Choose `Other Public Cloud`.


4.  Save the new service.

    You can now see it in the list.

5.  To create an endpoint, select the service.

6.  Under *Endpoints*, check whether there's an existing endpoint with the use case *Test Automation*. If so, you can update it by choosing :pencil2:.

7.  If no endpoint exists for the *Test Automation* use case, choose *Add* and enter the following parameters:

    -   *Endpoint Name*: Enter a meaningful and unique endpoint name that helps you easily identify the test automation tool. This name will later be displayed in the test management apps.

    -   *Description*: Enter a short endpoint description, such as `Endpoint for test automation for system <SID>`. This description will later be displayed in the *General Information* section of the test cases.

    -   *Use Case*: Select `Test Automation`.

    -   *Root URL*: The root URL of your previously specified service is prefilled.

    -   *Authentication Type*: You can decide between `Basic Authentication` and `OAuth2ClientCredentials`.

        `Basic Authentication`:

        -   *User*: Enter the communication user.

        -   *Password*: Enter the password for the created communication user.


        `OAuth2ClientCredentials`:

        -   *Client ID*: Enter the client ID.

        -   *Client Secret*: Enter the client secret.

        -   *Token Service URL*: Enter the token service URL.



8.  Save the new endpoint.




<a name="loiof6df4f3c3c994b6e9714cbe1fe217506__section_mg4_15b_kbc"/>

## Result and Next Steps

The connection between SAP Cloud ALM and the external test automation provider has been established. A synchronization with the automation provider takes place to retrieve the existing automated test cases whenever new processes are scoped in your SAP Cloud ALM projects.



<a name="loiof6df4f3c3c994b6e9714cbe1fe217506__section_olf_bmk_lzb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Alternatively, you can create a case in [SAP for Me](https://me.sap.com/app/casecreate) on the component SV-CLM-IMP-TAT.

