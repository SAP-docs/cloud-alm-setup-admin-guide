<!-- loio448f9f17151f4dc2beeda248ca092618 -->

# Retrieving Service Credentials

The connection between individual SAP Cloud applications and your managed systems and/or services is handled via an SAP Cloud ALM API service instance in your SAP Cloud ALM subaccount.

To set up the connection, you need to retrieve the service credentials \(that is, service binding or service key\) from the SAP Cloud ALM API instance.

Depending on the provisioning date of your SAP Cloud ALM tenant, some or all steps described in this document have already been automatically completed for you:


<table>
<tr>
<th valign="top">

Provisioning Date

</th>
<th valign="top">

Actions

</th>
</tr>
<tr>
<td valign="top">

On or after October 16, 2023

</td>
<td valign="top">

The required service credentials have already been generated automatically as part of the provisioning of your SAP Cloud ALM tenant.

You can skip the steps on the subsequent pages altogether and access your credentials in the SAP BTP cockpit or in the *Landscape Management* app, as described in [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md).

</td>
</tr>
<tr>
<td valign="top">

Between June 12, 2023 and October 16, 2023

</td>
<td valign="top">

Service credentials that can be used to connect managed services to SAP Cloud ALM for operations monitoring applications was generated automatically.

You can access them in the SAP BTP cockpit or in the *Landscape Management* app, as described in [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md).

You only need to carry out the steps on the subsequent pages if you want to set up transport management, but you no longer have to configure your entitlements.

</td>
</tr>
<tr>
<td valign="top">

Before June 12, 2023

</td>
<td valign="top">

No service credentials have been created as part of the provisioning of your SAP Cloud ALM tenant. To create one manually, carry out the steps on the subsequent pages.

</td>
</tr>
</table>

-   **[Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md "To set up the connection between SAP Cloud ALM and your managed systems and/or services,
		you need to create a service binding from the SAP Cloud ALM API
		instance.")**  
To set up the connection between SAP Cloud ALM and your managed systems and/or services, you need to create a service binding from the SAP Cloud ALM API instance.
-   **[Enabling SAP Cloud ALM API in Cloud Foundry](enabling-sap-cloud-alm-api-in-cloud-foundry-7d4c180.md "To set up the connection between SAP Cloud ALM and your managed systems and/or services,
		you need to create a service key from the SAP Cloud ALM API
		instance.")**  
To set up the connection between SAP Cloud ALM and your managed systems and/or services, you need to create a service key from the SAP Cloud ALM API instance.
-   **[Managing Your Service Credentials](managing-your-service-credentials-87b7851.md "If you requested SAP Cloud ALM on or after June 14, 2023, automatically generated SAP
		Cloud ALM service credentials was uploaded to the Landscape
			Management app for you. These credentials can be used to connect managed
		services to push monitoring data using OAuth 2.0.")**  
If you requested SAP Cloud ALM on or after June 14, 2023, automatically generated SAP Cloud ALM service credentials was uploaded to the *Landscape Management* app for you. These credentials can be used to connect managed services to push monitoring data using OAuth 2.0.

