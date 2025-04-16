<!-- loioff524644d161496886994fbb3f6c7634 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrate SAP LeanIX

You can integrate SAP LeanIX with SAP Cloud ALM for an integration of project and task management, as well as landscape management.

Gain comprehensive and consistent transparency by discovering your SAP landscape through SAP Cloud ALM.

Set up SAP Cloud ALM and connect your SAP LeanIX workspace to SAP Cloud ALM via API, as described in the following sections.

For the overall setup of SAP LeanIX, see [Configuring SAP Landscape Discovery](https://docs-eam.leanix.net/docs/configuring-sap-landscape-discovery#connecting-sap-leanix-to-the-sap-cloud-alm-api).



<a name="loioff524644d161496886994fbb3f6c7634__section_wpy_rnj_jmb"/>

## Prerequisites

Your user has the role *Global Account Administrator* in the global account that was created when you requested SAP Cloud ALM, and is a member of the subaccount containing your SAP Cloud ALM subscription.

If you don't have this role, the global account administrator can assign it to you by following the steps described in [Add Members to Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/4a0491330a164f5a873fa630c7f45f06.html).



<a name="loioff524644d161496886994fbb3f6c7634__section_lv5_hh4_xlbs"/>

## Procedure



### Create an Instance

> ### Caution:  
> Make sure that you create a new API instance and **do not update an existing instance**. Updating an existing instance can interfere with the connection between managed systems and SAP Cloud ALM, as they also use a service key.

To consume the SAP Cloud ALM API, you need to create a service instance for the SAP Cloud ALM tenant in the SAP BTP cockpit:

1.  In the [SAP BTP cockpit](https://cockpit.btp.cloud.sap/) from *Account Explorer*, select the global account that contains your SAP Cloud ALM entitlement and open the subaccount that contains your SAP Cloud ALM subscription.
2.  Choose *Services* \> *Instances and Subscriptions*.

3.  Choose *Create*.

4.  Under *Basic Info*, provide the following details:

    -   *Service*: `SAP Cloud ALM API`

    -   *Plan*: `standard`

    -   *Runtime Environment*: `Other`

    -   *Instance Name*: Enter a meaningful instance name.

        The length of the instance name must not exceed 32 characters. Use only alphanumeric characters, numbers from 0 to 9, periods, and hyphens. Instead of spaces, use underscores.

        ![](images/NOCF-NewInstance_85b4cb4.png)


5.  Choose *Next*.

6.  To use the service binding to access the APIs for the SAP LeanIX integration you need to add the appropriate scopes to it.

    You find the required scopes for the LeanIX integrations under:

    -   Configuring SAP Landscape Discovery: [Enabling API Access to SAP Cloud ALM](https://docs-eam.leanix.net/docs/configuring-sap-landscape-discovery#enabling-api-access-to-sap-cloud-alm)

    -   Configuring SAP Cloud ALM Integration For Managing Projects: [Enabling API Access to SAP Cloud ALM](https://docs-eam.leanix.net/docs/configuring-sap-cloud-alm-integration-for-managing-projects#enabling-api-access-to-sap-cloud-alm)


    To add the scopes, insert the following JSON and replace the relevant parameters with your instance name and the required scopes, respectively. The instance name must be the **same** one that you entered under *Basic Info*, in step 4.

    Optional: If you want to use just one service binding for the SAP LeanIX integration, you need to merge the scopes.

    ```
    
    {
        "xs-security": {
            "xsappname": "<your-instance-name>",
            "authorities": [
               "$XSMASTERAPPNAME.calm-api.landscape.read",
               "$XSMASTERAPPNAME.calm-api.subscriptions.read"
            ],
            "oauth2-configuration": {
                "credential-types": [
                    "binding-secret"
                ]
            }
        }
    }
    
    ```

7.  Choose *Create*.

8.  When your instance has been created or updated, click on it.




### Create a Binding

1.  Next to your instance, choose <span class="SAP-icons-V5"></span> \(Actions\) and select *Create Binding*.

    ![](images/NOCF-CreateServiceBinding_647e290.png)

2.  Enter a name for your binding.

    > ### Caution:  
    > To avoid conflicts with automatically created service credentials, use a name that differs from the naming convention `<system ID>_<client number>_<system number>`.

3.  Choose *Create*.

4.  Next to the created binding, choose <span class="SAP-icons-V5"></span> \(Actions\) and select *View*.




<a name="loioff524644d161496886994fbb3f6c7634__section_eb3_y5b_kbc"/>

## Result and Next Steps

You can now see your service credentials in JSON format. They include the following information:

-   The application base URL \(`endpoints.Api`\)

-   The `clientid` and `clientsecret` to access the service

-   The oAuth URL to generate the oAuth token \(`uaa.url`\)


![](images/SUI-ServiceKey_2fca8a5.png)

> ### Caution:  
> Outside of the SAP BTP cockpit, service credentials must be stored securely. If you need new ones, create them directly in the SAP BTP cockpit, and access it from there whenever you need it.

If you encounter issues with the connection in SAP Cloud ALM, please contact support under component SV-CLM-INF-LMS \(*Landscape Management*\) or SV-CLM-IMP-PRJ \(*Projects and Setup*\).



<a name="loioff524644d161496886994fbb3f6c7634__section_d3t_3w2_k2c"/>

## Further Steps in SAP LeanIX

For the overall setup of SAP LeanIX, see:

-   [Configuring SAP Landscape Discovery](https://docs-eam.leanix.net/docs/configuring-sap-landscape-discovery)

-   [Configuring SAP Cloud ALM Integration For Managing Projects](https://docs-eam.leanix.net/docs/configuring-sap-cloud-alm-integration-for-managing-projects)


