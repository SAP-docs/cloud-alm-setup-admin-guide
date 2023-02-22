<!-- loio07122541847b48fa9766044a8fc8c404 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrating the Test Automation Tool for SAP S/4HANA Cloud

You can integrate automated test cases from the test automation tool for SAP S/4HANA Cloud for use in test orchestration in SAP Cloud ALM.



The test automation tool for SAP S/4HANA Cloud is a free automation provider delivered as part of the guided configuration tools for SAP S/4HANA in SAP Activate. It enables you to test SAP Best Practice processes after implementation or upgrade of SAP S/4HANA Cloud.

To use this integration in your project, you need to configure a service and an endpoint in the *Landscape Management* app in SAP Cloud ALM.



<a name="loio07122541847b48fa9766044a8fc8c404__section_w5v_kcx_x4b"/>

## Prerequisites

You have a **Test** or, depending on your landscape setup, **Development** system for the test automation tool for SAP S/4HANA Cloud.

> ### Note:  
> Don't connect your SAP S/4HANA Cloud **Production** system to SAP Cloud ALM. Test cases shouldn't be tested in production.



<a name="loio07122541847b48fa9766044a8fc8c404__section_tg2_sbx_x4b"/>

## Procedure

> ### Caution:  
> SAP recently revisited the way test automation providers are modeled in the *Landscape Management* app.
> 
> If you've already created a test automation endpoint for the test automation tool for SAP S/4HANA Cloud, **do not change or delete it**. It will continue to work. If you delete it and re-create it, it might impact the existing automated test cases that have been already synchronized with SAP Cloud ALM.
> 
> If you want to add a new automation provider, follow the new procedure described below.

1.  To communicate with the test automation tool for SAP S/4HANA Cloud, a communication user is required. If you need to create the communication user, follow the procedure described in [Communication Management](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/2e84a10c430645a88bdbfaaa23ac9ff7.html). The communication scenario is `COM0620`.

2.  In the SAP Cloud ALM launchpad, open the *Landscape Management* app.

3.  On the *Services* page, choose <span class="SAP-icons"></span> \(Cloud Service Filter\) and filter by the service type *SAP S/4HANA Cloud* and by the tenant roles *Test* and *Development*.

    > ### Note:  
    > Most of the time, the test automation tool is enabled on the test tenant, but it can also be enabled on the development tenant.

    The list now displays all SAP S/4HANA Cloud tenants that are currently connected to your SAP Cloud ALM tenant.

4.  Check whether there's an existing service for which the root URL matches the root URL of your test or development SAP S/4HANA Cloud system. If so, proceed directly to step 7.

5.  If no service exists for your SAP S/4HANA Cloud system, choose *Add* and enter the following parameters:

    -   *Name*: Enter a name that follows a naming convention that fits your organization, for example ***<Root\_URL\_S/4\>*** or ***<S/4\_System\_SID\>***.

    -   *Description*: Enter a short description, such as ***Test SAP S/4HANA Cloud for <Department, if relevant\>***.

    -   *Tenant ID*: Enter your tenant ID for the test automation tool for SAP S/4HANA Cloud.

    -   *Service Type*: Select ***SAP S/4HANA Cloud***.

    -   *Tenant Type*: Depending on your landscape setup, select ***Development*** or ***Test***.

    -   *Root URL*: Enter the root URL of your SAP S/4HANA Cloud system, starting with ***https***.

    -   *External ID*: Leave empty.

    -   *Customer Number*: Enter your customer number.

    -   *Customer Name*: Enter your customer name.


6.  Save the new service.

    You can now see it in the list.

7.  To create an endpoint, select the service.

8.  Under *Endpoints*, check whether there's an existing endpoint with the use case *Test Automation* or *Test Management*. If so, you can update it by choosing :pencil2:.

9.  If no endpoint exists for the *Test Automation* or *Test Management* use case, choose *Add* and enter the following parameters:

    -   *Endpoint Name*: Enter a meaningful and unique endpoint name that helps you easily identify the test automation tool. This name will later be displayed in the test management apps.

    -   *Description*: Enter a short endpoint description, such as ***Endpoint for test automation for system <SID\>***. This description will later be displayed in the *General Information* section of the test cases.

    -   *Use Case*: Select ***Test Automation***.

    -   *Root URL*: The root URL of your previously specified service is prefilled. Simply add the suffix ***/sap/bc/http/sap/sap\_calm\_testautomation\_api/***.

        The final URL follows the pattern ***https://<SAP S/4HANA Cloud System\>/sap/bc/http/sap/sap\_calm\_testautomation\_api/***.

    -   *Connection Test Path*: Leave empty.

        If this field is already prefilled, make sure to remove any extra parameters.

    -   *Authentication Type*: Select ***Basic Authentication***.

    -   *User*: Enter the communication user.

    -   *Password*: Enter the password for the created communication user.


10. Save the new endpoint.


> ### Note:  
> You can maintain multiple endpoints for test automation. However, we strongly recommend only maintaining **one** endpoint per SAP S/4HANA Cloud tenant.
> 
> You should maintain **two** test automation endpoints if you're working with a 3-system landscape setup for SAP S/4HANA Cloud with two test automation tenants \(one for the main line and one for the project line\).

Once you've established the connection between SAP Cloud ALM and the test automation tool for SAP S/4HANA Cloud, a synchronization with the SAP S/4HANA Cloud system takes place to retrieve the existing automated test cases whenever new processes are scoped in your SAP Cloud ALM projects.

**Related Information**  


[Test Automation Tool for S/4HANA Cloud - Additional Info](https://launchpad.support.sap.com/#/notes/2129147)

[Maintain Communication Systems](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/15663c157670410ca366623dff329396.html)

