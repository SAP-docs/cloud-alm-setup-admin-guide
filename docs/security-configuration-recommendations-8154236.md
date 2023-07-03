<!-- loio8154236e15404350ae3c53b792b87e72 -->

# Security Configuration Recommendations

Use the information in this table to secure the configuration and operation of SAP Cloud ALM services in your landscape.


<table>
<tr>
<th valign="top">

Capability



</th>
<th valign="top">

Priority



</th>
<th valign="top">

Secure Operations Map



</th>
<th valign="top">

Topic



</th>
<th valign="top">

Default Setting or Behavior



</th>
<th valign="top">

Recommendation



</th>
<th valign="top">

More Information



</th>
<th valign="top">

Last Update



</th>
<th valign="top">

Index



</th>
</tr>
<tr>
<td valign="top">

Cross



</td>
<td valign="top">

Critical



</td>
<td valign="top">

Audit Logging



</td>
<td valign="top">

Audit



</td>
<td valign="top">

By integrating the SAP Audit Log Viewer service for SAP BTP, you can view the audit logs for your SAP Cloud ALM tenant to track the end user activity in SAP Cloud ALM.



</td>
<td valign="top">

Enable the SAP Audit Log Viewer service for SAP BTP.



</td>
<td valign="top">

[Audit Log Viewer for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/audit-log-viewer-for-cloud-foundry-environment)



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-X-0001



</td>
</tr>
<tr>
<td valign="top">

Cross



</td>
<td valign="top">

Recommended



</td>
<td valign="top">

Client Security



</td>
<td valign="top">

Cookies



</td>
<td valign="top">

Depending on your browser, third-party cookies may be disabled by default.



</td>
<td valign="top">

To be able to use the in-app help and Built-In Support, either allow third-party cookies or enter the respective domain as **Sites that can always use cookies**.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-X-0002



</td>
</tr>
<tr>
<td valign="top">

Cross



</td>
<td valign="top">

Advanced



</td>
<td valign="top">

Client Security



</td>
<td valign="top">

External APIs



</td>
<td valign="top">

You can add and configure service instances to allow external applications to access the APIs published on [SAP Business Accelerator Hub](https://api.sap.com/package/SAPCloudALM/rest).

To do this, you need to configure authentication for the service instances and set allowed scopes in the service instance.



</td>
<td valign="top">

To protect information about the service instance, such as the OAuth secret, choose certificate-based authentication.

To prevent external applications from performing unauthorized operations, assign the minimal set of scopes. Create separate service instances with individual scopes for required purposes instead of assigning all scopes in one instance and using them for all API access.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-X-0003



</td>
</tr>
<tr>
<td valign="top">

External API Management



</td>
<td valign="top">

Advanced



</td>
<td valign="top">

Authentication and Single Sign-On



</td>
<td valign="top">

Secure System-to-System Integration



</td>
<td valign="top">

When configuring a webhook to point to the target external service API, you need to select either an SAP BTP destination or an endpoint in the *Landscape Management* app.



</td>
<td valign="top">

Use the authentication method that is recommended by the *Landscape Management* app or SAP BTP.



</td>
<td valign="top">

 [SAP BTP Security Recommendations](https://help.sap.com/docs/BTP/c8a9bb59fe624f0981efa0eff2497d7d/531f33def8074ccdb6f1f784a34dafcb.html) 



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-EXTAPI-0001



</td>
</tr>
<tr>
<td valign="top">

User & Access Management



</td>
<td valign="top">

Critical



</td>
<td valign="top">

Roles and Authorizations



</td>
<td valign="top">

Roles



</td>
<td valign="top">

Roles in SAP Cloud ALM are delivered as predefined collections.

The initial user receives the role *Global Administrator*, which provides the complete set of authorizations in SAP Cloud ALM.



</td>
<td valign="top">

Assign suitable roles that give users only the authorizations they need to perform their tasks.



</td>
<td valign="top">

[Role Collections](01_required_setup/role-collections-e1915af.md)



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-UAM-0001



</td>
</tr>
<tr>
<td valign="top">

Landscape Management



</td>
<td valign="top">

Critical



</td>
<td valign="top">

Authentication and Single Sign-On



</td>
<td valign="top">

Strong Authentication



</td>
<td valign="top">

When adding a service manually, you can choose between several authentication settings for new endpoints. The available options depend on the cloud service.



</td>
<td valign="top">

Choose one of the more secure methods according to the capabilities of the endpoint providing cloud service:

-   *OAuth2ClientCredentials*

-   *ClientCertificateAuthentication*

-   *Auth2SAMLBearerAuthentication*




</td>
<td valign="top">

[Step 3: Set Up Landscape Management – Services](01_required_setup/services-d5f36cc.md)



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-LM-0001



</td>
</tr>
<tr>
<td valign="top">

Project Management



</td>
<td valign="top">

Advanced



</td>
<td valign="top">

Roles and Authorizations



</td>
<td valign="top">

Project Access Restrictions



</td>
<td valign="top">

The access level of the initial, automatically created project is *Public*.

Any additional projects that you create manually are set to *Restricted* by default.



</td>
<td valign="top">

Select the appropriate access level for your project:

-   *Public*

-   *Restricted*

-   *Private*




</td>
<td valign="top">

[Configuring Project User Permissions](02_integration_and_config_options/configuring-project-user-permissions-a2c0029.md)



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-PTM-0001



</td>
</tr>
<tr>
<td valign="top">

Business Process Monitoring



</td>
<td valign="top">

Recommended



</td>
<td valign="top">

Roles and Authorizations



</td>
<td valign="top">

KPI Access Control



</td>
<td valign="top">

You can restrict the data access of a defined user group to a particular business process scope.

By default, access control is deactivated.



</td>
<td valign="top">

Use access groups to grant users access only to data relevant to their tasks.



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

CALM-BM-0001



</td>
</tr>
</table>

-   **[Explanations of Table Properties](explanations-of-table-properties-3afa465.md "")**  


