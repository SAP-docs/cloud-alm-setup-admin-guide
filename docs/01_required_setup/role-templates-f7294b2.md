<!-- loiof7294b2640b849d4adc7d43a30cf75dd -->

# Role Templates

For most SAP Cloud ALM capabilities, you can use the predefined and ready-to-use role collections, which correspond to a single role template. Some areas also offer role templates without a 1:1 relationship with a role collection. Before you can use these role templates, you need to assign them to a custom role collection.



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

Actions

</th>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Task Management** 

</td>
<td valign="top">

`imp_tkm_TaskViewer` 

</td>
<td valign="top">

View tasks, defects, quality gates, requirements, and risks

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Task Management** 

</td>
<td valign="top">

`imp_tkm_TaskManager` 

</td>
<td valign="top">

Manage tasks, defects, quality gates, requirements, risks, and test cases

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

`imp_cdm_ChangeManager` 

</td>
<td valign="top">

Change feature status to *Ready for Production*

Perform transport checks

Display transport check results

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

Perform transport checks

Display transport check results

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

Perform transport checks

Display transport check results

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

Access to *Features* app

Edit features

Create transports

Assign or unassign transports

Create transport of copies

Add or remove transport references

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
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Change & Deployment Management** 

</td>
<td valign="top">

`imp_cdm_RetrofitConfigurator` 

</td>
<td valign="top">

Access to *Projects and Setup* app

View, create, and update retrofit configurations in deployment plans

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

`imp_cdm_RetrofitPerformer` 

</td>
<td valign="top">

Perform retrofit

Create features

Create transports

Access to *Projects and Setup* app

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Library Management** 

</td>
<td valign="top">

`imp_lib_LibraryViewer` 

</td>
<td valign="top">

View library elements

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Library Management** 

</td>
<td valign="top">

`imp_lib_LibraryManager` 

</td>
<td valign="top">

Manage library elements

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

**Library Management** 

</td>
<td valign="top">

`imp_lib_LibraryAdministrator` 

</td>
<td valign="top">

Manage library elements

Permanently delete library elements

</td>
</tr>
</table>

**Related Information**  


[Define a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection)

[Add Roles to a Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection)

