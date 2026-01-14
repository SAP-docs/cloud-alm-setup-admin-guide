<!-- loiof2a8a8cd38044f1aae04d8e5491530d4 -->

# Step 1: Onboard Users in the Identity Authentication Service

To give further users access to SAP Cloud ALM, you need to create or import users in your [SAP Cloud Identity Services – Identity Authentication](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/what-is-identity-authentication?version=LATEST&locale=en-US) tenant. For users to be able to sign in to SAP Cloud ALM, they need to be maintained both in the Identity Authentication tenant and in SAP Cloud ALM.



<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_lr3_dpm_wnb"/>

## Context

In SAP Cloud ALM, the Identity Authentication service \(IAS\) assumes the role of the identity provider. This means that business users sign in to SAP Cloud ALM with the mechanisms and credentials defined in the Identity Authentication tenant.

> ### Note:  
> You can also use an already existing corporate identity provider \(LDAP\), in which case you need to set up Identity Authentication as a proxy. Changing to a corporate identity provider while already using SAP Cloud ALM productively can result in invalidated user IDs and can cause users in SAP Cloud ALM to be deactivated. For more information, see [Onboard to SAP Cloud Identity Services](https://help.sap.com/docs/btp/best-practices/onboard-to-sap-cloud-identity-services) and [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/19f3eca47db643b6aad448b5dc1075ad.html).

When you requested SAP Cloud ALM, you either selected an existing Identity Authentication tenant or received a new one:

-   **Reused existing Identity Authentication tenant**:

    If you selected one of your existing productive Identity Authentication tenants, it was assigned to your SAP Cloud ALM subaccount during the provisioning and can be reused for user authentication in SAP Cloud ALM.

    Your authorizations in the Identity Authentication tenant remain the same. If the *Main IT Contact* of SAP Cloud ALM didn't have a user in the tenant before, they were added as a member.

    Your pre-existing tenant may already contain identity information. If you don't need new users in the tenant, you can proceed directly to [Step 2: Assign Roles to Users in SAP Cloud ALM](step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md) to add these users to SAP Cloud ALM and assign roles to them. If you do want to create new users in the tenant, follow the procedure below.

-   **New Identity Authentication tenant**:

    If you didn't have a productive Identity Authentication tenant before, a new tenant was automatically created for you. This tenant was then assigned to the SAP Cloud ALM subaccount.

    As the *Main IT Contact*, you were made an administrator in this new tenant and received an email asking you to activate your account in the Identity Authentication service. Once activated, the tenant contains no identity information. Before SAP Cloud ALM can be used, users have to be created or imported, as described below.




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_cyj_lcy_hnb"/>

## Prerequisites

-   Your Identity Authentication tenant has been activated.

    If your Identity Authentication tenant was created when your SAP Cloud ALM was requested, the *Main IT Contact* has received an email with the subject **Activate Your Account for Identity Authentication Service**.

-   In your Identity Authentication tenant, you have a user with the role *Manage Users*.

    If you don't have this role, the tenant administrator can assign it to you by following [Managing Administrators in Identity Authentication](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/786eea2e06fa4bef84d914a7c319d74c.html). To find the administrator of your Identity Authentication tenant, see [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/f56e6f24e373404087d6a1a9a13515a2.html).




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_h1w_1dy_hnb"/>

## Procedure



1.  In the administration console of the SAP Cloud Identity Services, open the *User Management* app.

    > ### Tip:  
    > The URL has the following pattern: `https://<tenant ID>.accounts.ondemand.com/admin`
    > 
    > The first administrator in the Identity Authentication tenant received an activation email with a link to the administration console.

2.  Choose *\+ Add User*.

    If you've already defined users elsewhere in your landscape, you can also import them to the Identity Authentication service. For more information, see [Import or Update Users for a Specific Application](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/33838e0760f8411daf758a1c11818cc4.html).

3.  Fill in the required fields.

    > ### Note:  
    > Remember the email address, as you need it to assign roles to the user later.

4.  Under *Personal Information*, enter the first and last name of the user. Use only the allowed characters A-Z, a-z, spaces, and hyphens.

5.  Save.

6.  Select *Send activation e-mail*.

7.  Save your entries.




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_sq4_qvb_kbc"/>

## Result and Next Steps

The new user now receives an activation email and can set a password.

To give them access to SAP Cloud ALM, you additionally need to add them to SAP Cloud ALM and assign the required roles to them, as described in [Step 2: Assign Roles to Users in SAP Cloud ALM](step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md).

**Related Information**  


[SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d17a116432d24470930ebea41977a888.html)

[Connected Identity Provider](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/4af49e80d5a04495bdef2168a26a1c12.html "This topic contains information on whether your identity provider configuration complies with SAP's recommendations.") :arrow_upper_right:

