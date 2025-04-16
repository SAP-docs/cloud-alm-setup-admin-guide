<!-- loiof7294b2640b849d4adc7d43a30cf75dd -->

# Role Templates

For most SAP Cloud ALM capabilites, you can use the predefined and ready-to-use role collections, which correspond to a single role template. Some areas also offer role templates without a 1:1 relationship with a role collection. Before you can use these role templates, you need to assign them to a custom role collection.



<a name="loiof7294b2640b849d4adc7d43a30cf75dd__section_jbk_5kc_pdc"/>

## Prerequisites

You have the role *Subaccount Administrator* in the subaccount that contains your SAP Cloud ALM subscription.



<a name="loiof7294b2640b849d4adc7d43a30cf75dd__section_ytx_5kc_pdc"/>

## Procedure

1.  Open the [SAP BTP cockpit](https://cockpit.btp.cloud.sap/).

2.  In the global account that contains your SAP Cloud ALM entitlement, open the subaccount that contains your SAP Cloud ALM subscription.

3.  Choose *Security* \> *Role Collections*.

4.  Choose *Create*.

5.  Enter a unique name and description for the role collection.

6.  Open the created role collection and choose *Edit*.

7.  Under *Roles*, select the role template or templates that you want to include, and choose *Add*.

8.  Save the role collection.




<a name="loiof7294b2640b849d4adc7d43a30cf75dd__section_uxd_tkc_pdc"/>

## Available Role Templates

> ### Note:  
> This table only lists role templates that are not part of the predefined role collections. However, when creating your own custom role collections, you can also include role templates that are part of the predefined role collections.

****


<table>
<tr>
<th valign="top">

SAP Cloud ALM Area

</th>
<th valign="top">

SAP Cloud ALM Capability

</th>
<th valign="top">

Name

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

RISE with SAP

</td>
<td valign="top">

*System View* 

</td>
<td valign="top">

`rdp_dashboard_ccSystemViewer` 

</td>
<td valign="top">

Access to the System View dashboard \(RISE with SAP\)

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_DeploymentManagerTest` 

</td>
<td valign="top">

Deploy transports into test systems

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_DeploymentManagerProd` 

</td>
<td valign="top">

Deploy transports into production systems

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_DeveloperCore` 

</td>
<td valign="top">

Create and assign transports and transport references, and create transport of copies

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_StartImplementation` 

</td>
<td valign="top">

Change feature status to *In Implementation* 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_HandoverToTest` 

</td>
<td valign="top">

Change feature status to *In Testing* 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_Tester` 

</td>
<td valign="top">

Change feature status to *Successfully Tested* 

</td>
</tr>
</table>

**Related Information**  


[Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection)

[Add Roles to a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection)

