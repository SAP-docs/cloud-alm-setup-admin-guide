<!-- loio2bddb584d07d4833b7e33454c3c4a79d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Setting Up Tricentis Test Automation for SAP Integrated with SAP Cloud ALM

Tricentis Test Automation for SAP integrated with SAP Cloud ALM is a continuous testing platform that allows you to design automated, functional, end-to-end software tests across all layers of your enterprise architecture.



By using this integration in your project, you can take advantage of the test orchestration, execution monitoring, and reporting capabilities of SAP Cloud ALM.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_wqn_kt5_4wb"/>

## Prerequisites

-   Your user in SAP Cloud ALM has the role *Global Administrator* or *Project Administrator*.

-   You have an S-user with the role `Edit Cloud Data` and an email address that corresponds to the email address used in SAP Cloud ALM.

    You can evaluate valid S-users for your organization in SAP for Me, under [Important Contacts](https://me.sap.com/userscontacts/impcont).


If you requested SAP Cloud ALM, you've received the authorizations required to set up this integration.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_dvv_kt5_4wb"/>

## Procedure

1.  Open the app *Set Up Tricentis Test Automation for SAP*.

2.  Open the terms and conditions and read them carefully.

    Once you've opened the document, the *I accept* checkbox is enabled.

3.  Accept the terms and conditions and save.

    The following information is checked to determine if you meet the prerequisites to accept the terms and conditions:

    -   In SAP Cloud ALM:

        -   The ID of your SAP Cloud ALM tenant

        -   The customer number for which your SAP Cloud ALM tenant was initially provisioned

        -   The email address of the current user


    -   In the SAP Support Portal back end:

        -   Valid S-users for the given customer number

        -   S-users with an email address that corresponds to the email address used by the current SAP Cloud ALM user

        -   S-users with the role `Edit Cloud Data`


        If one or more such S-users are found, you can give consent. If your user does not meet these criteria, take a look at [Important Contacts](https://me.sap.com/userscontacts/impcont) to identify a user who is authorized to accept the terms and conditions.


    > ### Tip:  
    > The terms and conditions are stored on SAP Support Portal. You can read or download them from there at any time.

4.  To start the automated setup, choose *Set Up Tricentis Test Automation for SAP integrated with SAP Cloud ALM*.

    > ### Caution:  
    > The automated setup can only be performed if the following prerequisites are met:
    > 
    > -   You're using a standard SAP identity provider.
    > 
    > -   You haven't changed the hierarchy of the SAP Cloud ALM application in the identity provider.
    > 
    >     During the automated setup, the Tricentis application in the identity provider is created as a child application to the SAP Cloud ALM application. If your SAP Cloud ALM application was changed to be a child application of another application, the automated setup can't be completed because it's not possible to create a child application for a child application.
    > 
    > 
    > If any of these prerequisites aren't met, please open an incident under component SV-CLM-IMP-TM with the title *Request manual provisioning of Tricentis test automation for SAP tenant* after you've accepted the terms and conditions.
    > 
    > In the incident description, please provide the URL of your SAP Cloud ALM tenant along with information about your identity provider type and/or application hierarchy setup.

5.  The following setup steps are performed:

    -   Setup of the Tricentis application

    -   Provisioning of the Tricentis tenant

    -   Update of the Tricentis application

    -   Configuration of the endpoint for the test automation


6.  Set up Tricentis execution agents for remote execution, as described in [Set up team agents](https://documentation.tricentis.com/sap/tta_cloud_es/en/content/admin_guide/agents_team.htm).


You can now start using Tricentis Test Automation for SAP integrated with SAP Cloud ALM from the *Test Preparation* app in SAP Cloud ALM. The authoring of test cases happens directly Tricentis Test Automation for SAP, as described in the Tricentis documentation linked below.

There's no need to create any additional users. Once an SAP Cloud ALM user accesses Tricentis Test Automation for SAP from SAP Cloud ALM, a user in the tool is automatically created.



<a name="loio2bddb584d07d4833b7e33454c3c4a79d__section_olf_bmk_lzb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Alternatively, you can create a case in [SAP for Me](https://me.sap.com/app/casecreate) on one of the following components:

-   For issues while setting up or using the integration with SAP Cloud ALM, use the component SV-CLM-IMP-TAT.

-   For issues with the test automation tool itself, use the component XX-PART-TRI-TTA-CLD.


**Related Information**  


[SAP Help Portal – Tricentis Test Automation for SAP integrated with SAP Cloud ALM](https://help.sap.com/docs/CloudALM/2b4ce9f491d14691bc554446b57f6e2d/e66fb899e3f6432985061daba26936fc.html)

[Usage Rights for Tricentis Test Automation for SAP](https://support.sap.com/en/alm/usage-rights.html?anchorId=section_138430085)

[Tricentis Test Automation for SAP Cloud ALM: Online Help](https://documentation.tricentis.com/sap/tta_cloud_es/en/content/calm_integration.htm)

