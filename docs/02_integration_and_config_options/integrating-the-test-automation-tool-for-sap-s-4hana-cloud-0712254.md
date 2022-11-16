<!-- loio07122541847b48fa9766044a8fc8c404 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrating the Test Automation Tool for SAP S/4HANA Cloud

In addition to manual test cases, you can also integrate automated test cases from the test automation tool for SAP S/4HANA Cloud for use in the *Test Preparation* and *Test Execution* apps.



The test automation tool for SAP S/4HANA Cloud is a free tool delivered as part of the guided configuration tools for SAP S/4HANA in SAP Activate. It enables you to test SAP Best Practice processes after implementation or upgrade of SAP S/4HANA Cloud.

To use this integration in your project, you need to configure a service and an endpoint in the *Landscape Management* app in SAP Cloud ALM.



<a name="loio07122541847b48fa9766044a8fc8c404__section_w5v_kcx_x4b"/>

## Prerequisites

You have a **Quality** or, depending on your landscape setup, **Development** system for the test automation tool for SAP S/4HANA Cloud.

> ### Caution:  
> Don't connect your SAP S/4HANA Cloud **Production** system to SAP Cloud ALM. Test cases shouldn't be tested in production.



<a name="loio07122541847b48fa9766044a8fc8c404__section_tg2_sbx_x4b"/>

## Procedure

> ### Caution:  
> SAP is in the process of integrating new service types for test automation and revisiting the way test automation providers are modeled in the *Landscape Management* app.
> 
> If you've already modeled a test automation endpoint for the test automation tool for SAP S/4 HANA Cloud, **do not change or delete it**. It will continue to work. If you delete it and re-create it, it might impact the existing automated test cases that have been already synchronized with SAP Cloud ALM.

1.  To communicate with the test automation tool for SAP S/4HANA Cloud, a communication user is required. If you need to create the communication user, follow the procedure described in [Communication Management](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/2e84a10c430645a88bdbfaaa23ac9ff7.html). The communication scenario is `COM0620`.

2.  In the SAP Cloud ALM launchpad, open the *Landscape Management* app.

3.  On the *Services* page, choose <span class="SAP-icons"></span> \(Cloud Service Filter\) and filter by the service type *Test Automation \(Deprecated\)*.

    The list displays all available services that have been defined for the test automation.

4.  Check whether there's an existing service for which the root URL matches the root URL of your quality SAP S/4HANA Cloud system. If so, proceed directly to step 7.

5.  If no service exists for your SAP S/4HANA Cloud system, choose *Add* and enter the following parameters:

    -   *Name*: Enter a name that follows a naming convention that fits your organization, for example ***S4TAT\_<SAP S/4HANA Cloud System\_SID\>***.

    -   *Description*: Enter a short description, such as ***Test automation tool for SAP S/4HANA Cloud for <Department, if relevant\>***.

    -   *Tenant ID*: Enter your tenant ID for the test automation tool for SAP S/4HANA Cloud.

    -   *Service Type*: Select ***Test Automation \(Deprecated\)***.

    -   *Tenant Type*: Depending on your landscape setup, select ***Development*** or ***Test***.

    -   *Root URL*: Enter the root URL of your SAP S/4HANA Cloud system, starting with ***https***.

    -   *External ID*: Leave empty.

    -   *Customer Number*: Enter your customer number.

    -   *Customer Name*: Enter your customer name.


6.  Save the new service.

    You can now see it in the list.

7.  To create an endpoint, select the created service.

8.  Under *Endpoints*, check whether there's an existing endpoint with the destination name `SAPS4_TAT`. If so, you can update it by choosing :pencil2:.

9.  If no endpoint exists for the *Test Automation* use case, choose *Add* and enter the following parameters:

    -   *Endpoint Name*: Enter ***SAPS4\_TAT***.

        The endpoint name must be ***SAPS4\_TAT***. It can't be changed.

    -   *Description*: Enter a short endpoint description, such as ***Endpoint for test automation***.

    -   *Use Case*: Select ***Test Automation***.

    -   *Root URL*: The root URL of your previously specified service is prefilled. Simply add the suffix ***/sap/bc/http/sap/sap\_calm\_testautomation\_api/***.

        The final URL follows the pattern ***https://<SAP S/4HANA Cloud System\>/sap/bc/http/sap/sap\_calm\_testautomation\_api/***.

    -   *Connection Test Path*: Leave empty.

    -   *Authentication Type*: Select ***Basic Authentication***.

    -   *User*: Enter the communication user.

    -   *Password*: Enter the password for the created communication user.


10. Save the new endpoint.


Please note that you can maintain only one service and one endpoint for the integration of the test automation tool for SAP S/4HANA Cloud.

Once you've established the connection between SAP Cloud ALM and the test automation tool for SAP S/4HANA Cloud, a synchronization with the SAP S/4 HANA Cloud system takes place to retrieve the existing automated test cases whenever new processes are scoped in your SAP Cloud ALM projects.

**Related Information**  


[Test Automation Tool for S/4HANA Cloud - Additional Info](https://launchpad.support.sap.com/#/notes/2129147)

[Maintain Communication Systems](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/LATEST/en-US/15663c157670410ca366623dff329396.html)

