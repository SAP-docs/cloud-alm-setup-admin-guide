<!-- loiod5f36cc72b4443f6abfa95f6e1a17782 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Services

Depending on your subscribed service, there are different ways of importing or creating service information in the *Landscape Management* app.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_pht_h13_wtb"/>

## Automatic Import by SAP \(Recommended\)

For many subscribed services, related service information is imported automatically on a daily basis by the System Landscape Information service.

To display the current status in the *Landscape Management* app, open the *Configuration* \(:gear:\), expand the section *Import of Subscribed SAP Services*, and click on the first icon after *Status of imports*. If you don't want to wait for the daily import, you can import your services on demand in the *Status of Imports* popover by choosing *Import My Subscribed SAP Services*.

If your service hasn't been imported automatically, you may need to create the service information manually by following the steps described in the section *Manual Creation \(Only If Required\)*.

> ### Note:  
> **Additional information for global ultimate customers**:
> 
> As a global ultimate customer \(that is, a customer managing SAP cloud products that are subscribed under multiple customer accounts, for example after an acquisition\) you need to enter an S-user that has the authorizations to access the system data for all subsidiary customer accounts to ensure that the *Landscape Management* app has access to the data.
> 
> The S-user must not be a **technical** S-user but a standard **dialog** S-user with CCC Group authorizations. For more information on how to create such an S-user, refer to SAP Note [3070306](https://me.sap.com/notes/3070306).
> 
> To add the S-user, open the *Landscape Management* app and choose <span style="font-size:16px;"><span class="SAP-icons"></span></span> \(Configuration\). Under *Import of Subscribed SAP Services*, choose :heavy_plus_sign: and enter the credentials of the S-user.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_wc5_2rs_vyb"/>

## Automatic Creation by Service Registration

There are push-enabled services that register themselves in SAP Cloud ALM \(for example, SAP SuccessFactors and SAP S/4HANA Cloud\). These services are created automatically in the *Landscape Management* app as part of the communication arrangement or registration. If the services already exist in the app, the technical details are updated automatically.



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_pft_frs_vyb"/>

## Manual Creation \(Only If Required\)

The automatic import by SAP is the preferred way to import service information for services. However, you can also manually add any additional services if necessary \(for example, services of the type *Unspecific Cloud Service \(HTTP\)* or *SAP Ariba Cloud Integration Gateway\)*.

For more information, refer to [Creating Services Manually](https://help.sap.com/docs/CloudALM/877c96cf971648b09ee0d0a64f7f4fef/3a6b59fbb92c4882a0513ec1b6f5fda1.html).



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_zt4_cps_vyb"/>

## Next Steps

After adding your service to the *Landscape Management* app, you need to establish a connection between the service and SAP Cloud ALM to collect monitoring data. How this connection is established depends on the individual service type.

For detailed, service type-specific information on the managed service's setup, refer to [Setup Managed Services / Systems](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services.html) in the SAP Cloud ALM for Operations Expert Portal.

