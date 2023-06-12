<!-- loio704b5dc854f549888a238f94015e1eac -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling SAP Cloud ALM API

To set up the connection between your managed systems and individual SAP Cloud ALM applications, you need to retrieve your service key and connect your SAP services and systems to your SAP Cloud ALM instance.





<a name="loio704b5dc854f549888a238f94015e1eac__section_wpy_rnj_jmb"/>

## Prerequisites

-   Your user has the role *Global Account Administrator* in the global account that was created when you requested SAP Cloud ALM, and is a member of the subaccount containing your SAP Cloud ALM subscription.

    If you don't have this role, the global account administrator can assign it to you by following the steps described in [Add Members to Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/4a0491330a164f5a873fa630c7f45f06.html).

-   Your user has the role *Org Manager* in your Cloud Foundry organization.

    If you don't have this role, the org manager can assign it to you by following the steps described in [Add Org Members Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/a4eeaf179ee646b99558f27c0bae7b3e.html). If *Cloud Foundry* is not available in the menu, you can enable it by following the steps described in [Create Orgs](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/a9b1f5445a17427f844a5a43ac53d378.html).


> ### Note:  
> If you've requested SAP Cloud ALM, your user has automatically received the required authorizations during the creation of the global account and the subaccount.



<a name="loio704b5dc854f549888a238f94015e1eac__section_lv5_hh4_xlb"/>

## Procedure

Carry out the following steps to enable SAP Cloud ALM API:



### Create a Space

1.  Open the SAP BTP cockpit.

2.  Select the global account that contains your SAP Cloud ALM entitlement, which was created when you requested SAP Cloud ALM.

3.  Under *Subaccounts*, select the subaccount that contains your SAP Cloud ALM subscription.

4.  Choose *Cloud Foundry* \> *Spaces*.

5.  If you already have a space with the required authorizations, proceed to the **Configure Entitlements** section.

    If you don't have a space yet, choose *Create Space*.

     ![Create a Space](images/Enabling_APIs_-_Create_Space_f46e85f.png) 

6.  Enter a space name and select the roles that you want to assign to your user for this space. To perform the following steps, your user needs at least *Space Developer* authorizations.

7.  Choose *Create*.




### Configure Entitlements

An entitlement is your right to provision and consume a resource.

1.  Choose *Entitlements* \> *Configure Entitlements*.

     ![Configure Entitlements](images/Enabling_APIs_-_Configure_Entitlements_a560903.png) 

2.  Choose *Add Service Plans*.

3.  Add the required service plan as follows:

    1.  Select the entitlement *SAP Cloud ALM API*.

    2.  Under *Available Plans*, check the option *standard*.

    3.  Choose *Add 1 Service Plan*.

         ![Select a Service Plan for SAP Cloud ALM APIs](images/Enabling_APIs_-_Add_Service_Plan_f2a4ae2.png) 


4.  Choose *Save*.




### Maintain an Instance

1.  Choose *Cloud Foundry* \> *Spaces*.

2.  Select your space.

3.  Choose *Services* \> *Instances*.

4.  If you already have an instance, choose <span class="SAP-icons"></span> \(Actions\) and select *Update*. Then proceed to step 6.

    If you don't have an instance yet, click on the *Create* dropdown and select *Service Instance*.

     ![](images/Create_Service_Instance_f00749a.png) 

5.  Under *Basic Info*, provide the following details:

    -   *Service*: ***SAP Cloud ALM API***

    -   *Plan*: ***standard***

    -   *Instance Name*: Enter a meaningful instance name.

        The length of the instance name must not exceed 32 characters. Use only alphanumeric characters, numbers from 0 to 9, periods, and hyphens. Instead of spaces, use underscores.

         ![Choose Service Plan](images/Enabling_APIs_-_Standard_Service_Plan_b9cfbff.png) 


6.  Choose *Next*.

7.  Paste the following JSON code into the text editor:

    ```
    {
        "xs-security": {
            "xsappname": "<Your Instance Name>",
            "authorities": [
    			"$XSMASTERAPPNAME.imp-cdm-feature-display-ui",
    			"$XSMASTERAPPNAME.imp-cdm-feature-manage-ui"
            ]
        }
    }
    
    ```

8.  Replace `<Your Instance Name>` with your instance name.

9.  Choose *Create*.

10. When your instance has been created or updated, click on it.




### Create a Service Key

Service keys allow you to configure an external application so that it can connect to an SAP Cloud ALM API service instance.

1.  In the top right corner, choose <span class="SAP-icons"></span> \(Actions\) and select *Create Service Key*.

     ![Create a Service Key](images/Enabling_APIs_-_Create_Service_Key_515c433.png) 

2.  Enter a name for your service key.

3.  Choose *Create*.

4.  Next to your newly created service key, choose <span class="SAP-icons"></span> \(Actions\) and select *View*.

     ![](images/SUI-ViewServiceKey_7add56b.png) 

5.  You can now see your service key in JSON format.

    It includes the following information:

    -   The application base URL \(`endpoints.Api`\)

    -   The `clientid` and `clientsecret` to access the service

    -   The oAuth URL to generate the oAuth token \(`uaa.url`\)



> ### Caution:  
> Outside of the SAP BTP cockpit, service keys must be stored securely. If you need a service key, create the service key directly in the SAP BTP cockpit, and access it from there whenever you need it.

-   **[Managing Your Service Key](managing-your-service-key-87b7851.md "If you requested SAP Cloud ALM after 2023-06-14, an SAP Cloud ALM service key was
		created and automatically uploaded to the Landscape Management app
		for you. This key can be used to connect managed services to push monitoring data using
		OAuth 2.0.")**  
If you requested SAP Cloud ALM after 2023-06-14, an SAP Cloud ALM service key was created and automatically uploaded to the *Landscape Management* app for you. This key can be used to connect managed services to push monitoring data using OAuth 2.0.

**Related Information**  


[Managing Spaces](http://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/5209d55d8dd84228897112b0655d999b.html)

[Entitlements and Quotas](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/00aa2c23479d42568b18882b1ca90d79.html)

[API Guide for SAP Cloud ALM](https://help.sap.com/viewer/fe419bfabbdc46dfbddbfd78b21483d5/latest/en-US/25fda4490062486e88f0712302e8b801.html "You can use SAP Cloud ALM interfaces to access and manipulate data on your SAP Cloud ALM instance.") :arrow_upper_right:

