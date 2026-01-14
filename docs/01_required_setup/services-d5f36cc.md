<!-- loiod5f36cc72b4443f6abfa95f6e1a17782 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Services

The import method of services in SAP Cloud ALM depends on the service type of your [solution](../supported-solutions-3ebab44.md).

To find out which setup steps are required for your service, refer to [Connecting Systems and Services](../connecting-systems-and-services-31159aa.md).

> ### Note:  
> Observability data from your connected services isn't automatically sent to your SAP Cloud ALM tenant. If you want to start monitoring observability data, the data transfer to SAP Cloud ALM first needs to be configured.





<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_lfz_rng_cfc"/>

## Case 1: Automatic Import

Most service types are imported into SAP Cloud ALM automatically if they are assigned to the same customer number as your SAP Cloud ALM tenant. This import is done on a daily basis by the System Landscape Information service.

To display the current status in the *Landscape Management* app, open the *Configuration* \(:gear:\), expand the section *Import of Subscribed SAP Services*, and click on the first icon after *Status of imports*.

If required, you can also start an import on demand by choosing *Import My Subscribed SAP Services*. This is usually only necessary if recommended by SAP.

> ### Note:  
> **Additional steps if you have multiple customer numbers**:
> 
> If you have services that are assigned to a different customer number \(for example, as a global ultimate customer or as a subsidiary of a parent company\) and you want to use one SAP Cloud ALM tenant to monitor other customer numbers in the customer hierarchy, make sure that the customer numbers are already linked in a corporate group \(CCC group\), as described in [2459283](https://me.sap.com/notes/2459283).
> 
> Then, you need to link an S-user that is authorized to access the system data for all subsidiary customer accounts with the *Landscape Management* app to ensure that SAP Cloud ALM has access to the data. To do this, carry out the following steps:
> 
> 1.  In the *Landscape Management* app, choose <span style="font-size:16px;"><span class="SAP-icons-V5"></span></span> \(Configuration\).
> 
> 2.  Under *Import of Subscribed SAP Services*, choose :heavy_plus_sign:.
> 
> 3.  Enter the credentials of the S-user that can read system data for a customer in the CCC group. To be able to access the required system data, the S-user must be one of the following:
> 
>     -   A **technical** S-user that was created on top of the group hierarchy \(for the main or parent account\) and can therefore see all subsidiary customer numbers of the corporate group.
> 
>     -   A **standard** S-user in the corporate group with the required authorizations. You can manage the authorizations of standard S-users yourself and to your requirements, which gives you more control over which customer numbers they can access.
> 
> 
> 4.  Save.
> 
> 5.  Verify that the user name and the password are correct and that the S-user has access to the customer number of the SAP Cloud ALM tenant by performing the *S-User Logon Check* \(<span class="SAP-icons-V5"></span>\).
> 
> 
> The customer numbers you have access to will then be fetched from the cloud landscape directory. With the next daily sync, the services are added to *Landscape Management* app and stored in the section *Imported Customer Numbers*.
> 
> For more information about corporate groups and corporate group S-users, refer to [Troubleshooting for Landscape Management](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/9d68fc2749c84c4a8d3c9bc1b7ddfb89.html "This page helps you to analyze common errors in the Landscape Management app of SAP Cloud ALM.") :arrow_upper_right:.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_kvy_vng_cfc"/>

## Case 2: Registration

Other services types \(such as *SAP SuccessFactors* and *SAP S/4HANA Cloud*\) are push-enabled services that register themselves in SAP Cloud ALM. These services are created automatically in the *Landscape Management* app as part of the communication arrangement or registration.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_pht_h13_wtb"/>

## Case 3: Manual Creation

Only some service types \(for example, *Unspecific Cloud Service \(HTTP\)* or *Managed Gateway for Spend&Network*\) must be added to the *Landscape Management* app manually.

