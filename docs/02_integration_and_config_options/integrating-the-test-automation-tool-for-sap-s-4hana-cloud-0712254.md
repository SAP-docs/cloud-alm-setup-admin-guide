<!-- loio07122541847b48fa9766044a8fc8c404 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrating the Test Automation Tool for SAP S/4HANA Cloud

You can integrate automated test cases from the test automation tool for SAP S/4HANA Cloud for use in test orchestration in SAP Cloud ALM.



The test automation tool for SAP S/4HANA Cloud is a free automation provider delivered as part of the guided configuration tools for SAP S/4HANA Cloud in SAP Activate. It enables you to test SAP Best Practice processes after implementation or upgrade of SAP S/4HANA Cloud Public Edition.

To use this integration in your project, you need to configure a service and an endpoint in the *Landscape Management* app in SAP Cloud ALM.



<a name="loio07122541847b48fa9766044a8fc8c404__section_w5v_kcx_x4b"/>

## Prerequisites

-   You have a **Test** system for the test automation tool for SAP S/4HANA Cloud.

    > ### Note:  
    > Don't connect your SAP S/4HANA Cloud **Production** system to SAP Cloud ALM. Test cases shouldn't be tested in production.

-   You've set up the app *Test Your Processes* in the test automation tool for SAP S/4HANA Cloud, as described [here](https://help.sap.com/docs/SAP_S4HANA_CLOUD/2ab07d21f68c41109a2eef21b8fd8466/5d867592753c465aadb81115de672f91.html).




<a name="loio07122541847b48fa9766044a8fc8c404__section_tg2_sbx_x4b"/>

## Procedure

> ### Caution:  
> SAP recently revisited the way test automation providers are modeled in the *Landscape Management* app.
> 
> If you've already created a test automation endpoint for the test automation tool for SAP S/4HANA Cloud, **do not change or delete it**. It will continue to work. If you delete it and re-create it, it might impact the existing automated test cases that have been already synchronized with SAP Cloud ALM.
> 
> If you want to add a new automation provider, follow the new procedure described below.

1.  To communicate with the test automation tool for SAP S/4HANA Cloud, a communication user is required. If you need to create the communication user, follow the procedure described in [Communication Management](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/2e84a10c430645a88bdbfaaa23ac9ff7.html). The communication scenario is `COM0620`.

2.  In the SAP Cloud ALM launchpad, open the *Administration* page.

3.  Open the *Landscape Management* app.

4.  In the <span class="SAP-icons-V5"></span> *Select a Scope* dialog, make sure that the service *SAP S/4HANA Cloud* is selected.

5.  On the *Services & Systems* page, choose <span class="SAP-icons-V5"></span> \(Cloud Service Filter\) and filter by the service type *SAP S/4HANA Cloud* and by the tenant role *Test*.

    The list now displays all SAP S/4HANA Cloud tenants that are currently connected to your SAP Cloud ALM tenant.

6.  Check whether there's an existing service for which the root URL matches the root URL of your test SAP S/4HANA Cloud system. If so, proceed directly to step 8.

7.  If no service exists for your SAP S/4HANA Cloud system, choose *Add* \> *New Cloud Service* and enter the following parameters:

    -   *Name*: Enter a name that follows a naming convention that fits your organization, for example `<Root_URL_S/4>` or `<S/4_System_SID>`.

        Please note that spaces and special characters other than hyphens and underscores aren't allowed.

    -   *Description*: Enter a short description, such as `Test SAP S/4HANA Cloud for <Department, if relevant>`.

    -   *Tenant ID*: Enter a meaningful tenant ID for the test automation tool for SAP S/4HANA Cloud that uniquely identifies the service in the *Landscape Management* app. This ID can be freely chosen.

    -   *Service Type*: Select `SAP S/4HANA Cloud`.

    -   *Tenant Type*: Select `Test`.

    -   *Root URL*: Enter the root URL of your SAP S/4HANA Cloud launchpad, starting with `https` and ending with `.com` or `.sap`.

    -   *External ID*: Leave empty.

    -   *Customer Number*: Enter your customer number.

    -   *Customer Name*: Enter your customer name.


8.  Save the new service.

    You can now see it in the list.

9.  To create an endpoint, select the service.

10. Under *Endpoints*, check whether there's an existing endpoint with the use case *Test Automation* or *Test Management*. If so, you can update it by choosing :pencil2:.

11. If no endpoint exists for the *Test Automation* or *Test Management* use case, choose *Add* and enter the following parameters:

    -   *Endpoint Name*: Enter a meaningful and unique endpoint name that helps you easily identify the test automation tool. This name will later be displayed in the test management apps.

    -   *Description*: Enter a short endpoint description, such as `Endpoint for test automation for system <SID>`. This description will later be displayed in the *General Information* section of the test cases.

    -   *Use Case*: Select `Test Automation`.

    -   *Root URL*: The root URL of your previously specified service is prefilled. After `.com` or `.sap`, add the suffix `/sap/bc/http/sap/sap_calm_testautomation_api/`.

        The final URL follows the pattern `https://<SAP S/4HANA Cloud Root URL>/sap/bc/http/sap/sap_calm_testautomation_api/`.

    -   *Connection Test Path*: Leave empty.

        If this field is already prefilled, make sure to remove any extra parameters.

    -   *Authentication Type*: Select `Basic Authentication`.

    -   *User*: Enter the communication user.

    -   *Password*: Enter the password for the created communication user.


12. Save the new endpoint.


> ### Note:  
> You can maintain multiple endpoints for test automation. However, we strongly recommend only maintaining **one** endpoint per SAP S/4HANA Cloud tenant.
> 
> You should maintain **two** test automation endpoints if you're working with a 3-system landscape setup for SAP S/4HANA Cloud with two test automation tenants \(one for the main line and one for the project line\).



<a name="loio07122541847b48fa9766044a8fc8c404__section_mg4_15b_kbc"/>

## Result and Next Steps

The connection between SAP Cloud ALM and the test automation tool for SAP S/4HANA Cloud has been established. A synchronization with the SAP S/4HANA Cloud system takes place to retrieve the existing automated test cases whenever new processes are scoped in your SAP Cloud ALM projects.



<a name="loio07122541847b48fa9766044a8fc8c404__section_olf_bmk_lzb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Alternatively, you can create a case in [SAP for Me](https://me.sap.com/app/casecreate) on the component SV-CLM-IMP-TAT.

**Related Information**  


[Test Automation Tool for S/4HANA Cloud - Additional Info](https://me.sap.com/notes/2129147)

[Maintain Communication Systems](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/15663c157670410ca366623dff329396.html)

