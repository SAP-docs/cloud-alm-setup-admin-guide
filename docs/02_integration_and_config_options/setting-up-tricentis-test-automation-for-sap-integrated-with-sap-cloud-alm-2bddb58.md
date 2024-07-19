<!-- loio2bddb584d07d4833b7e33454c3c4a79d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Setting Up Tricentis Test Automation for SAP Integrated with SAP Cloud ALM

Tricentis Test Automation for SAP integrated with SAP Cloud ALM is a joint cloud-based offering from SAP and Tricentis.



It combines the application lifecycle management capabilities of SAP Cloud ALM with the test automation capabilities of Tricentis, allowing you to design automated, functional, end-to-end software tests and manage them with test orchestration, execution monitoring, and reporting capabilities.

Before you can start your automated testing activities, a Tricentis tenant needs to be set up and connected to SAP Cloud ALM for you.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_wqn_kt5_4wb"/>

## Prerequisites

-   Your user in SAP Cloud ALM has the role *Global Administrator* or *Project Administrator*.

-   You have an S-user with the role `Edit Cloud Data` and an email address that corresponds to the email address used in SAP Cloud ALM.

    You can evaluate valid S-users for your organization in SAP for Me, under [Important Contacts](https://me.sap.com/userscontacts/impcont).

-   You're using an Identity Authentication tenant as your identity provider and you haven't changed the hierarchy of the SAP Cloud ALM application within it.

    > ### Note:  
    > The Tricentis provisioning currently doesn't support default identity providers \(`sap.default`\). If you've assigned a default identity provider to your SAP Cloud ALM subaccount **in addition to** an Identity Authentication tenant, the Identity Authentication tenant is automatically selected for your Tricentis tenant during the provisioning.
    > 
    > If you've connected multiple Identity Authentication tenants, configurations with *OpenID Connect* are chosen over *SAML*.
    > 
    > If all of your connected Identity Authentication tenants are based on the same identity protocol or if you're using a completely different identity provider setup, please open an incident under component SV-CLM-IMP-TAT with the subject *"Request manual provisioning of Tricentis test automation for SAP tenant"* after you've accepted the terms and conditions. In the incident description, provide the URL of your SAP Cloud ALM tenant along with information about your identity provider and/or application hierarchy setup.
    > 
    > **Tip**: You can check the identity providers that are assigned to your SAP Cloud ALM subaccount in the SAP BTP cockpit by choosing *Security* \> *Trust Configuration*.


If you were the one who requested SAP Cloud ALM and you haven't changed any roles and trust configurations, these prerequisites are met.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_dvv_kt5_4wb"/>

## Procedure

1.  In the SAP Cloud ALM launchpad, open the *Implementation* page.

2.  Open the app *Set Up Tricentis Test Automation for SAP*.

3.  Open the terms and conditions and read them carefully.

    Once you've opened the document, the *I accept* checkbox is enabled.

4.  Accept the terms and conditions and save.

    > ### Tip:  
    > The terms and conditions are stored on SAP Support Portal. You can read or download them from there at any time.

5.  To start the automated setup, choose *Set Up Tricentis Test Automation for SAP integrated with SAP Cloud ALM*.

6.  The following setup steps are performed:

    -   Setup of the Tricentis application

    -   Provisioning of the Tricentis tenant

    -   Update of the Tricentis application

    -   Configuration of the endpoint for the test automation


7.  Set up Tricentis execution agents for remote execution, as described in [Set up team agents](https://documentation.tricentis.com/sap/tta_cloud_es/en/content/admin_guide/agents_team.htm).




<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_nln_ytb_kbc"/>

## Result and Next Steps

The connection between SAP Cloud ALM and Tricentis Test Automation for SAP integrated with SAP Cloud ALM has been established.

There's no need to create any additional users in your Tricentis tenant. If the users are maintained in the Identity Authentication tenant that was used for the Tricentis provisioning, they are automatically created in test automation tool when they access it for the first time.

The authoring of test cases happens directly in the automation provider, as described in the Tricentis documentation linked below.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_olf_bmk_lzb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Alternatively, you can create a case in [SAP for Me](https://me.sap.com/app/casecreate) on one of the following components:

-   For issues while setting up or using the integration with SAP Cloud ALM, use the component SV-CLM-IMP-TAT.

-   For issues with the test automation tool itself, use the component XX-PART-TRI-TTA-CLD.


**Related Information**  


[Usage Rights for Tricentis Test Automation for SAP](https://support.sap.com/en/alm/usage-rights.html?anchorId=section_138430085)

[Tricentis Test Automation for SAP Cloud ALM: Online Help](https://documentation.tricentis.com/sap/tta_cloud_es/en/content/get_started.htm)

