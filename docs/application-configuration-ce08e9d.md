<!-- loioce08e9d0d647455f962ffc210de1c7de -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Application Configuration

For several apps in SAP Cloud ALM, additional setup steps are required or possible.



<a name="loioce08e9d0d647455f962ffc210de1c7de__section_qts_pm5_qzb"/>

## SAP Cloud ALM for Implementation

There are many integration options that can be used to extend the functionalities of SAP Cloud ALM for implementation. The setup of these integrations is described under [Integration and Configuration Options](02_integration_and_config_options/integration-and-configuration-options-a4ea6fa.md).



<a name="loioce08e9d0d647455f962ffc210de1c7de__section_z12_qm5_qzb"/>

## SAP Cloud ALM for Operations



### Data Collection

You have full control which data from managed services and systems is transferred to SAP Cloud ALM:

When you activate your SAP Cloud ALM tenant and register your systems and services in the *Landscape Management* app of SAP Cloud ALM, the collection of observability data is not started automatically. SAP Cloud ALM follows a central configuration approach: You need to explicitly configure the data collection processes.

In addition, SAP is moving from customer-managed connectivity \(established by customers\) to SAP-managed connectivity \(established by SAP\). To find out which additional steps are necessary to establish customer-managed connectivity, see [Setup Managed Services / Systems](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services.html) in the operations expert portal.



### Personalization and Configuration

In many apps, you can also perform application-specific personalizations and configurations by choosing :gear: in the top-right corner.

For more information, refer to the **Configuration** pages of the respective apps in the [Application Help](https://help.sap.com/docs/cloud-alm/applicationhelp) on SAP Help Portal.



<a name="loioce08e9d0d647455f962ffc210de1c7de__section_mzx_rm5_qzb"/>

## SAP Cloud ALM for Service

The collaboration between SAP and the customer for service delivery requires a transfer of data into the customer's SAP Cloud ALM tenant. This data transfer is automatically activated, and you can request to deactivate it. More under [Enabling Service Delivery](02_integration_and_config_options/enabling-service-delivery-a1b2494.md).

