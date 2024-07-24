<!-- loio80b2c30a8d194ae8aff496bcff057cf0 -->

# Required Setup for SAP Cloud ALM

After you've requested SAP Cloud ALM, there are additional mandatory configuration steps that are required to set up SAP Cloud ALM for productive use.

SAP Cloud ALM is included in your cloud subscription and helps you to implement and operate intelligent cloud and hybrid business solutions. By following steps 1-3 in the next chapters, you can start to use SAP Cloud ALM immediately.



<a name="loio80b2c30a8d194ae8aff496bcff057cf0__section_e22_lj1_wxb"/>

## Need Support?

If you need support, take a look at the following resources:

-   [Services for SAP Cloud ALM](https://support.sap.com/en/alm/sap-cloud-alm/services-for-sap-cloud-alm.html)

-   [Troubleshooting and FAQ](../troubleshooting-and-faq-737bcf7.md)

-   [Schedule an Expert](https://me.sap.com/app/sae)


> ### Caution:  
> It's currently not possible to move your SAP Cloud ALM application from its original data center to a different data center. For more information, see [Lifecycle Management of Your SAP Cloud ALM Tenant](../troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_w4v_qq5_tyb).



<a name="loio80b2c30a8d194ae8aff496bcff057cf0__section_rdm_3mt_r5b"/>

## Required Authorizations

If you requested SAP Cloud ALM, your user has received all authorizations required to perform the initial setup. However, we recommend also manually assigning these authorizations to at least one more user.

The following authorizations are required to perform the initial setup of SAP Cloud ALM:


<table>
<tr>
<th valign="top">

Environment

</th>
<th valign="top">

Role

</th>
</tr>
<tr>
<td valign="top">

Identity Authentication tenant

</td>
<td valign="top">

*Administrator*

If a new Identity Authentication tenant was created for you when you requested SAP Cloud ALM, you've automatically received the required roles in the Identity Authentication tenant.

If someone else requested SAP Cloud ALM or if you're using a pre-existing Identity Authentication tenant for SAP Cloud ALM, the [administrator](https://iamtenants.accounts.cloud.sap/) can add you as an administrator by following the steps described in [Managing Administrators in Identity Authentication](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/786eea2e06fa4bef84d914a7c319d74c.html).

</td>
</tr>
<tr>
<td valign="top">

SAP BTP cockpit

</td>
<td valign="top">

-   *Global Account Administrator* in the global account that contains your SAP Cloud ALM entitlement

    If you don't have this authorization, the global account administrator can assign it to you by following the steps described in [Add Members to Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/4a0491330a164f5a873fa630c7f45f06.html).

-   *Subaccount Administrator* in the subaccount that contains your SAP Cloud ALM subscription

    If you don't have this authorization, the subaccount administrator can assign the role to you by following the steps described in [Add Members to Your Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/1e1b7b60bb1b4764a2d4bb96bd73182d.html).

-   *Org Manager* for the Cloud Foundry organization in your SAP Cloud ALM subaccount

    This role is only required if a Cloud Foundry org and space exist in your SAP Cloud ALM subaccount and is in use in the context of SAP Cloud ALM APIs.

    If you don't have this role, the org manager can assign it to you by following the steps described in [Add Org Members Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/a4eeaf179ee646b99558f27c0bae7b3e.html).




</td>
</tr>
<tr>
<td valign="top">

SAP Cloud ALM

</td>
<td valign="top">

*Global Administrator* or *User Administrator*

If you don't have this authorization, the *Global Administrator* can assign the roles to you by following [Assign Roles to Users in SAP Cloud ALM](https://help.sap.com/docs/CloudALM/08879d094f3b4de3ac67832f4a56a6de/7304b17f3aac4ebaa24c5c6a3a8e236e.html).

</td>
</tr>
</table>



<a name="loio80b2c30a8d194ae8aff496bcff057cf0__section_hjw_gmt_r5b"/>

## Overview: Onboarding Procedure

![After you've requested SAP Cloud ALM on SAP for Me, you need to onboard
							users in the Identity Authentication service, then add users to SAP
							Cloud ALM and assign roles to them in the User Management app, and then
							(if required) set up landscape management.](images/Image_Map_Required_Setup_for_SAP_Cloud_ALM_d4f9ce5.png)

-   **[Step 1: Onboard Users in the Identity Authentication Service](step-1-onboard-users-in-the-identity-authentication-service-f2a8a8c.md "To give further users access to SAP Cloud ALM, you need to create or import users in
		your Identity Authentication tenant. For users to be able to sign in to SAP Cloud ALM, they
		need to be maintained both in the Identity Authentication tenant and in SAP Cloud
		ALM.")**  
To give further users access to SAP Cloud ALM, you need to create or import users in your Identity Authentication tenant. For users to be able to sign in to SAP Cloud ALM, they need to be maintained both in the Identity Authentication tenant and in SAP Cloud ALM.
-   **[Step 2: Assign Roles to Users in SAP Cloud ALM](step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md "After onboarding your users to your Identity Authentication tenant, you need to add them
		to SAP Cloud ALM and assign roles to them.")**  
After onboarding your users to your Identity Authentication tenant, you need to add them to SAP Cloud ALM and assign roles to them.
-   **[Step 3: Set Up Landscape Management](step-3-set-up-landscape-management-23f1c49.md "As the last step of the required setup, services and systems need to be set up in the
			Landscape Management app in SAP Cloud ALM.")**  
As the last step of the required setup, services and systems need to be set up in the *Landscape Management* app in SAP Cloud ALM.

