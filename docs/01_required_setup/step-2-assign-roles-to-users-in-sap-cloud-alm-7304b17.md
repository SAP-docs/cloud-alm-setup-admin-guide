<!-- loio7304b17f3aac4ebaa24c5c6a3a8e236e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Step 2: Assign Roles to Users in SAP Cloud ALM

After onboarding your users to your Identity Authentication tenant, you need to add them to SAP Cloud ALM and assign roles to them.

You can add users and assign roles to them directly in the SAP Cloud ALM *User Management* app \(recommended\) or as corresponding role collections in the SAP BTP cockpit.

To assign role templates to users, first create a role collection and add the role template to it. After a daily sync job, the role collection you've created also appears under *Custom Roles* in the *User Management* app and can be assigned to other users from there.



> ### Note:  
> If you're working with role mapping to user groups in your identity provider, you need to assign role collections in the SAP BTP cockpit. In this case, you can't view or change roles in the *User Management* app and use the role request and assignment features in SAP Cloud ALM, so we don't recommend this method.



<a name="loio7304b17f3aac4ebaa24c5c6a3a8e236e__section_g43_crh_jmb"/>

## SAP Cloud ALM User Management \(Recommended\)



### Prerequisites

-   Your user has the role *Global Administrator* or *User Administrator*.

    As the *Main IT Contact* for SAP Cloud ALM, you've automatically received the role *Global Administrator*. If you don't have this role, another *Global Administrator* or *User Administrator* can assign one of the required roles to you by following the process below.

-   The identities of the users to whom you want to assign roles already exist in the identity provider, as described in [Step 1: Onboard Users in Your Identity Authentication Service](step-1-onboard-users-in-the-identity-authentication-service-f2a8a8c.md).

-   Only relevant for EU Access: You've set up an SMTP mail destination named **SAP\_Business\_Notifications\_Mail** in your SAP BTP subaccount for SAP Cloud ALM, as described in [Configuring an SMTP Mail Destination](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/configuring-smtp-mail-destination).

    Context: If your SAP Cloud ALM tenant is hosted in the region `eu11` \(EU Access\), no email service is provided by the data center. You need to use your own email server that you are operating under your responsibility, or your users won't receive a welcome email after they've been created.




### Procedure

1.  Access SAP Cloud ALM. A link is included in the email *Welcome to SAP Cloud ALM*.

    Sign in with the email address and password you've defined when activating your account in the Identity Authentication service. Don't sign in with your S-user.

2.  Open the *User Management* app, which is located on the *Administration* page.

3.  To go to the user list, choose <span class="SAP-icons-V5"></span> \(Users\).

4.  Choose *Add User*.

5.  Enter the *User ID* and/or *Email* as you've defined them in the settings of your identity provider. If you've selected your email address as your user ID in your identity provider, you only need to enter the email address.

6.  Select a type for your user. Possible types are:


    <table>
    <tr>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Not Assigned* 
    
    </td>
    <td valign="top">
    
    No user type \(default value\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Employee* 
    
    </td>
    <td valign="top">
    
    Employee of your company
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP* 
    
    </td>
    <td valign="top">
    
    Consultant from SAP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Partner* 
    
    </td>
    <td valign="top">
    
    Consultant from official SAP partner
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Other* 
    
    </td>
    <td valign="top">
    
    Person from a company other than SAP or official SAP partner
    
    </td>
    </tr>
    </table>
    
7.  Assign one or multiple roles to the user.

    For an overview of all predefined role collections that are available in SAP Cloud ALM, refer to [Role Collections](roles-e1915af.md).

8.  Save your settings.

9.  If you want the added user to receive updates regarding SAP Cloud ALM and your other SAP cloud services, for example, about planned and unplanned downtimes and other customer communications, consider signing them up for cloud availability notifications. For more information, refer to KBA [2900069](https://me.sap.com/notes/2900069).




### Result

The user now receives a welcome email from SAP Cloud ALM.

For more information on how to use the *User Management* app to view, add, and change roles, refer to [User Management](https://help.sap.com/docs/cloud-alm/applicationhelp/user-management).



<a name="loio7304b17f3aac4ebaa24c5c6a3a8e236e__section_amj_f5z_tqb"/>

## SAP BTP Cockpit

The roles in SAP Cloud ALM are available as role collections in your subaccount in the SAP BTP cockpit.

> ### Note:  
> The role collections that you assign in the SAP BTP cockpit are synchronized by the *User Management* app only once a day.
> 
> As a result, although the role collection assignment takes effect in SAP Cloud ALM immediately \(with the next logon of the user\), it may not be displayed in the *User Management* app for up to 24 hours.



### Prerequisites

-   Your user has the role *Subaccount Administrator* in the subaccount that contains your SAP Cloud ALM subscription.

    As the *Main IT Contact* for SAP Cloud ALM, your user has received this authorization during the creation of the subaccount. If you don't have this authorization, the *Subaccount Administrator* can assign the role to you by following [Add Members to Your Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/LATEST/en-US/1e1b7b60bb1b4764a2d4bb96bd73182d.html).

-   The identities of the users to whom you want to assign roles already exist in the identity provider, as described in [Step 1: Onboard Users in Your Identity Authentication Service](step-1-onboard-users-in-the-identity-authentication-service-f2a8a8c.md).




### Procedure

1.  Open the [SAP BTP cockpit](https://cockpit.btp.cloud.sap/).

2.  Select the global account that contains your SAP Cloud ALM entitlement, which was created when you requested SAP Cloud ALM.

3.  Under *Subaccounts*, select the subaccount that contains your SAP Cloud ALM subscription.

4.  Navigate to *Security* \> *Role Collections*.

    > ### Caution:  
    > If you map role collections to user groups in SAP BTP, the users have the corresponding authorizations, but these roles are not displayed in the User Management of SAP Cloud ALM. For more information, see KBA [3472730](https://me.sap.com/notes/3472730).

5.  Select the role collection to which you want to add users.

6.  Choose *Edit*.

7.  Add users to this role collection as follows:

    -   If you’re using the standard configuration in trust settings and identity provider that was set when you requested SAP Cloud ALM, enter the email address of the user into the fields *ID* **and** *E-Mail*. Select *Custom IAS Tenant* as identity provider.

    -   If you've manually connected the identity provider or selected a different identification attribute \(such as user ID\) in your identity provider, enter the identification attribute that you maintained there in the field *ID* and select the correct identity provider.

        > ### Caution:  
        > Don't use the identity provider *Default identity provider*, *SAP ID Service*, or *sap.default*.


8.  If you want the added users to receive updates regarding SAP Cloud ALM and your other SAP cloud services, for example, about planned and unplanned downtimes and other customer communications, consider signing them up for cloud availability notifications. For more information, refer to KBA [2900069](https://me.sap.com/notes/2900069).


-   **[Roles](roles-e1915af.md "Roles in SAP Cloud ALM are delivered predefined and ready to use.")**  
Roles in SAP Cloud ALM are delivered predefined and ready to use.
-   **[Role Templates](role-templates-f7294b2.md "For most SAP Cloud ALM capabilities, you can use the predefined and ready-to-use role
		collections, which correspond to a single role template. Some areas also offer role
		templates without a 1:1 relationship with a role collection. Before you can use these role
		templates, you need to assign them to a custom role collection.")**  
For most SAP Cloud ALM capabilities, you can use the predefined and ready-to-use role collections, which correspond to a single role template. Some areas also offer role templates without a 1:1 relationship with a role collection. Before you can use these role templates, you need to assign them to a custom role collection.

