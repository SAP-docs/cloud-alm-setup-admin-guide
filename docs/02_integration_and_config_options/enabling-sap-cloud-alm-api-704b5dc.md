<!-- loio704b5dc854f549888a238f94015e1eac -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling SAP Cloud ALM API

To integrate certain products or connect on-premise systems with SAP Cloud ALM, you need to create a service binding from the SAP Cloud ALM API instance.

> ### Note:  
> This document describes how to retrieve service credentials without Cloud Foundry.
> 
> If your SAP Cloud ALM tenant was provisioned before October 2023, you can also follow [Enabling SAP Cloud ALM API in Cloud Foundry](https://help.sap.com/doc/d97695e60e5847609b439d0ba8f2ab28/latest/en-US/88405e3f78724ba995b0aebe8dd705a4.pdf). However, we strongly recommend following the approach **without** Cloud Foundry.



<a name="loio704b5dc854f549888a238f94015e1eac__section_zvy_ttj_yfc"/>

## Prerequisites

Your user has the role *Global Account Administrator* in the SAP Cloud ALM global account and is a member of the subaccount containing the SAP Cloud ALM subscription.

If you don't have this role, the global account administrator can assign it to you by following the steps described in [Add Members to Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/4a0491330a164f5a873fa630c7f45f06.html).



<a name="loio704b5dc854f549888a238f94015e1eac__section_lv5_hh4_xlbs"/>

## Procedure



### Configure Entitlements

An entitlement is your right to provision and consume a resource. In other words, entitlements are the service plans that you're entitled to use.

1.  Open the [SAP BTP cockpit](https://cockpit.btp.cloud.sap/).

2.  Select the global account that contains your SAP Cloud ALM entitlement and open the subaccount that contains your SAP Cloud ALM subscription.

3.  In the menu, go to *Entitlements*.

4.  Choose *Edit* \> *Add Service Plans*.

5.  Add the required service plan as follows:

    1.  Select the entitlement *SAP Cloud ALM API*.

    2.  Under *Available Plans*, check the option *standard*.

    3.  Choose *Add 1 Service Plan*.

        ![Select a Service Plan for SAP Cloud ALM APIs](images/Enabling_APIs_-_Add_Service_Plan_f2a4ae2.png)


6.  Save.




### Create or Update an Instance

To consume the selected service plan, you need to create a service instance.

1.  Choose *Services* \> *Instances and Subscriptions*.

2.  If you already have an instance, choose <span class="SAP-icons-V5"></span> \(Actions\) and select *Update*. Then proceed to step 4.

    If you don't have an instance yet, choose *Create*.

3.  Under *Basic Info*, provide the following details:

    -   *Service*: `SAP Cloud ALM API`

    -   *Plan*: `standard`

    -   *Runtime Environment*: `Other`

    -   *Instance Name*: Enter a meaningful instance name.

        The length of the instance name must not exceed 32 characters. Use only alphanumeric characters, numbers from 0 to 9, periods, and hyphens. Instead of spaces, use underscores.

        ![](images/New_Instance_a1c66a5.png)


4.  Choose *Next*.

5.  \(Optional\) If you intend to enable transport management with the resulting service binding at any point in the future, we recommend already adding the relevant `cdm` scopes now.

    To add the scopes, insert the following JSON. If you're updating an existing instance, replace `<your-instance-name>` with your instance ID \(GUID\).

    ```
    {
        "xs-security": {
            "xsappname": "<your-instance-name>",
            "authorities": [
              "$XSMASTERAPPNAME.imp-cdm-feature-display-ui",
              "$XSMASTERAPPNAME.imp-cdm-feature-manage-ui"
            ],
            "oauth2-configuration": {
                "credential-types": [
                    "binding-secret"
                ]
            }
        }
    }
    
    ```

6.  Choose *Create*.

7.  When your instance has been created or updated, click on it.




### Create a Binding

1.  Next to your instance, choose <span class="SAP-icons-V5"></span> \(Actions\) and select *Create Binding*.

    ![](images/NOCF-CreateServiceBinding_647e290.png)

2.  Enter a name for your binding.

    > ### Caution:  
    > To avoid conflicts with automatically created service credentials, use a name that differs from the naming convention `<system ID>_<client number>_<system number>`.

3.  Choose *Create*.

4.  Next to the created binding, choose <span class="SAP-icons-V5"></span> \(Actions\) and select *View*.




<a name="loio704b5dc854f549888a238f94015e1eac__section_obt_b5j_yfc"/>

## Result

You can now see your service credentials in JSON format. They include the following information:

-   The application base URL \(`endpoints.Api`\)

-   The `clientid` and `clientsecret` to access the service

-   The oAuth URL to generate the oAuth token \(`uaa.url`\)


![](images/SUI-ServiceKey_2fca8a5.png)

> ### Caution:  
> Outside of the SAP BTP cockpit, service credentials must be stored securely. If you need new ones, create them directly in the SAP BTP cockpit, and access it from there whenever you need it.

**Related Information**  


[Entitlements and Quotas](https://help.sap.com/viewer/3504ec5ef16548778610c7e89cc0eac3/Cloud/en-US/00aa2c23479d42568b18882b1ca90d79.html)

[API Guide for SAP Cloud ALM](https://help.sap.com/docs/cloud-alm/apis/about)

