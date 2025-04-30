<!-- loiod5f36cc72b4443f6abfa95f6e1a17782 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Services

The import method of services in SAP Cloud ALM depends on the service type of your [solution](../supported-solutions-3ebab44.md).

To find out which setup steps are required for your service, refer to [Setup Managed Services / Systems](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services.html) in the SAP Cloud ALM for Operations Expert Portal.

> ### Note:  
> Observability data from your connected services isn't automatically sent to your SAP Cloud ALM tenant. If you want to start monitoring observability data, the data transfer to SAP Cloud ALM first needs to be configured.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_lfz_rng_cfc"/>

## Case 1: Automatic Import

Most service types are imported into SAP Cloud ALM automatically if they are assigned to the same customer number as your SAP Cloud ALM tenant. This import is done on a daily basis by the System Landscape Information service.

To display the current status in the *Landscape Management* app, open the *Configuration* \(:gear:\), expand the section *Import of Subscribed SAP Services*, and click on the first icon after *Status of imports*.

If required, you can also start an import on demand by choosing *Import My Subscribed SAP Services*. This is usually only necessary if recommended by SAP.



### Additional Steps for Global Ultimate Customers

If you have services that are assigned to a different customer number \(for example, as a global ultimate customer\) and you want to use one SAP Cloud ALM tenant to monitor other customer numbers in the customer hierarchy, you need to enter an S-user that has the authorizations to access the system data for all subsidiary customer accounts to ensure that the *Landscape Management* app has access to the data.

To be able to access the required system data, the S-user must be one of the following:

-   A **technical** S-user that was created on top of the group hierarchy \(for the main or parent account\). By default, these technical S-users can see all subsidiary customer numbers of the corporate group.

-   A **standard** S-user in the corporate group. You can manage the authorizations of standard S-users yourself and to your requirements, which gives you more control over which customer numbers they can access.


To add the S-user, open the *Landscape Management* app and choose <span style="font-size:16px;"><span class="SAP-icons-V5"></span></span> \(Configuration\). Under *Import of Subscribed SAP Services*, choose :heavy_plus_sign: and enter the credentials of the S-user.

You can verify that the user name and the password are correct and that the S-user has access to the customer number of the SAP Cloud ALM tenant by performing the *S-User Logon Check* \(<span class="SAP-icons-V5"></span>\).

The customer numbers you have access to will then be stored in the section *Imported Customer Numbers*. Please note that initially, the customer name may be missing in this table. If the customer is available in the cloud landscape directory, the name will be added with the next daily sync.

For more information about corporate groups and corporate group s-users, refer to [Troubleshooting for Landscape Management](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/calm-op-troubleshooting/lms-troubleshooting.html?anchorId=section_665299547_co) on SAP Support Portal.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_kvy_vng_cfc"/>

## Case 2: Registration

Other services types \(such as *SAP SuccessFactors* and *SAP S/4HANA Cloud*\) are push-enabled services that register themselves in SAP Cloud ALM. These services are created automatically in the *Landscape Management* app as part of the communication arrangement or registration.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_pht_h13_wtb"/>

## Case 3: Manual Creation

Only some service types \(for example, *Unspecific Cloud Service \(HTTP\)* or *Managed Gateway for Spend & Network*\) must be added to the *Landscape Management* app manually.

