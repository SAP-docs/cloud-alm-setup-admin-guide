<!-- loiod5f36cc72b4443f6abfa95f6e1a17782 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Services

The import method of services in SAP Cloud ALM depends on the service type of your solution.



-   Most service types are imported into SAP Cloud ALM automatically if they are assigned to the same customer number as your SAP Cloud ALM tenant. This import is done on a daily basis by the System Landscape Information service.

    To display the current status in the *Landscape Management* app, open the *Configuration* \(:gear:\), expand the section *Import of Subscribed SAP Services*, and click on the first icon after *Status of imports*.

    > ### Note:  
    > If you have services that are assigned to a different customer number \(for example, as a global ultimate customer\), you need to enter an S-user that has the authorizations to access the system data for all subsidiary customer accounts to ensure that the *Landscape Management* app has access to the data.
    > 
    > The S-user must not be a **technical** S-user but a standard **dialog** S-user with CCC Group authorizations. For more information on how to create such an S-user, refer to SAP Note [3070306](https://me.sap.com/notes/3070306).
    > 
    > To add the S-user, open the *Landscape Management* app and choose <span style="font-size:16px;"><span class="SAP-icons"></span></span> \(Configuration\). Under *Import of Subscribed SAP Services*, choose :heavy_plus_sign: and enter the credentials of the S-user.

-   Other services types \(such as *SAP SuccessFactors* and *SAP S/4HANA Cloud*\) are push-enabled services that register themselves in SAP Cloud ALM. These services are created automatically in the *Landscape Management* app as part of the communication arrangement or registration.

-   Only some service types \(for example, *Unspecific Cloud Service \(HTTP\)* or *Managed Gateway for Spend & Network*\) must be added to the *Landscape Management* app manually.


Observability data from your connected services isn't automatically sent to your SAP Cloud ALM tenant. If you want to start monitoring observability data, the data transfer to SAP Cloud ALM first needs to be configured.

To find out which additional setup steps are required to monitor your service, refer to [Setup Managed Services / Systems](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services.html) in the SAP Cloud ALM for Operations Expert Portal.

