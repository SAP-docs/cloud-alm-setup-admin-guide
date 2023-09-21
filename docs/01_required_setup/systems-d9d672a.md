<!-- loiod9d672a2e8944067af5a914cf1e22d82 -->

# Systems

Most systems \(technical systems\) can be registered by running an ABAP report. Only some system types need to be set up manually.



<a name="loiod9d672a2e8944067af5a914cf1e22d82__section_xlh_mps_vyb"/>

## Registration \(Recommended\)

To register on-premise systems, run the ABAP report program `/SDF/ALM_SETUP` as described in [Setup Steps in the SAP ABAP On-Premise System](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap.html) on the SAP Cloud ALM for Operations Expert Portal.

When the registration in the system has been completed, the registered system is automatically displayed on the *Services & Systems* page. Once a technical system has been registered, a default logical system \(client\) is created and displayed in the *System Details*.



<a name="loiod9d672a2e8944067af5a914cf1e22d82__section_ucr_1rs_vyb"/>

## Manual Creation \(Only If Required\)

The automatic import by SAP is the preferred way to import service information for services. However, the system types *SAP Focused Run*, *Cloud Connector*, and *SAP Process Integration* can't be registered but need to be set up manually.

For more information, refer to [Creating Systems Manually](https://help.sap.com/docs/CloudALM/877c96cf971648b09ee0d0a64f7f4fef/7a2c7b0cf2d54d93b83b5ce6951b7fa6.html).



<a name="loiod9d672a2e8944067af5a914cf1e22d82__section_zt4_cps_vyb"/>

## Next Steps

After adding your system to the *Landscape Management* app, you may need to establish a connection between the system and SAP Cloud ALM to collect monitoring data. How this connection is established depends on the individual system type.

For detailed, system type-specific information on the managed system's setup, refer to [Setup Managed Services / Systems](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services.html) in the SAP Cloud ALM for Operations Expert Portal.

