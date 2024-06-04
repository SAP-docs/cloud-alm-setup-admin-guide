<!-- loiof2a8a8cd38044f1aae04d8e5491530d4 -->

# Step 1: Onboard Users in the Identity Authentication Service

To give further users access to SAP Cloud ALM, you need to create or import users in your Identity Authentication tenant.

For users to be able to sign in to SAP Cloud ALM, they need to be maintained both in the Identity Authentication tenant and in SAP Cloud ALM.



<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_lr3_dpm_wnb"/>

## Context

In SAP Cloud ALM, the Identity Authentication service assumes the role of the identity provider. This means that business users sign in to SAP Cloud ALM with the mechanisms and credentials defined in the Identity Authentication tenant.

> ### Note:  
> You can also use an already existing corporate identity provider \(LDAP\), in which case we strongly recommend using Identity Authentication as a proxy. Changing to a corporate identity provider while already using SAP Cloud ALM productively can result in invalidated user IDs and can cause users in SAP Cloud ALM to be deactivated. For more information, see [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/19f3eca47db643b6aad448b5dc1075ad.html).

When you requested SAP Cloud ALM, you either selected an existing Identity Authentication tenant or requested a new one:

-   **Reusing an existing Identity Authentication tenant**:

    If you already had a productive Identity Authentication, it was assigned to your SAP Cloud ALM subaccount during the provisioning and can be reused for user authentication in SAP Cloud ALM.

    If you didn't have a user in the Identity Authentication tenant before, you were added as a member. However, you didn't receive administrator authorizations in this tenant and you didn't receive an additional activation email for it.

    Your pre-existing tenant may already contain identity information. If you don't need new users in the tenant, you can proceed directly to [Step 2: Assign Roles to Users in SAP Cloud ALM](step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md) to add these users to SAP Cloud ALM and assign roles to them. If you do want to create new users in the tenant, contact the administrator of the Identity Authentication tenant that is connected to SAP Cloud ALM and either request that they follow the procedure below, or ask them to assign the required roles to you.

-   **Creating a new Identity Authentication tenant**:

    If you didn't have a productive Identity Authentication tenant when you requested SAP Cloud ALM, a new tenant was automatically created for you in the same data center where SAP Cloud ALM is provisioned. This tenant was then assigned to the SAP Cloud ALM subaccount.

    **Tip**: The productive Identity Authentication tenant you received for SAP Cloud ALM may also be used for other productive SAP cloud offerings \(such as SAP S/4HANA Cloud\) that you may want to use in the future.

    As the requesting user, you were made an administrator in this new tenant and received an email asking you to activate your account in the Identity Authentication service. Once activated, the tenant contains no identity information. Before SAP Cloud ALM can be used, users have to be created or imported, as described below.


> ### Note:  
> During the provisioning of SAP Cloud ALM, additional technical administrator users with names such as *SAP Cockpit* or *Service Cockpit* may be created in your Identity Authentication tenant. You'll receive a notification email if such a user is created.
> 
> These users are needed to onboard applications in back-end management systems. Please don't change or delete them. For more information, refer to KBA [3281767](https://me.sap.com/notes/3281767).



<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_cyj_lcy_hnb"/>

## Prerequisites

-   Your Identity Authentication tenant has been activated.

    If your Identity Authentication tenant was newly created when you requested SAP Cloud ALM, you've received an email with the subject **Activate Your Account for Identity Authentication Service**. Follow the guidance to activate the account and create a user profile for yourself.

-   In your Identity Authentication tenant, you have a user with the role *Manage Users*.

    If you've requested SAP Cloud ALM and a new Identity Authentication tenant was set up for you, your user has automatically received this authorization during the creation of the tenant. If someone else requested SAP Cloud ALM or you're using an existing Identity Authentication tenant in which you don't have this authorization, the tenant administrator can assign the role to you by following the steps described in [Managing Administrators in Identity Authentication](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/786eea2e06fa4bef84d914a7c319d74c.html).

    To find the administrator of your Identity Authentication tenant, see [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/f56e6f24e373404087d6a1a9a13515a2.html).




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_h1w_1dy_hnb"/>

## Procedure



1.  In the administration console of the SAP Cloud Identity Services, open the *User Management* app.

    > ### Tip:  
    > The URL has the following pattern: `https://<tenant ID>.accounts.ondemand.com/admin`
    > 
    > The first administrator that was created for the Identity Authentication tenant received an activation email containing a direct link to the administration console.

2.  Choose *\+ Add User*.

    > ### Note:  
    > If you've already defined users elsewhere in your landscape, you can also import them to the Identity Authentication service by using various tools, such as SAP Identity Management and the Identity Provisioning service.
    > 
    > For more information, see [Import or Update Users for a Specific Application](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/33838e0760f8411daf758a1c11818cc4.html) in the documentation for the Identity Authentication service.

3.  Fill in the required fields.

    Remember the email address, as you need it to assign roles to the user later.

    For information about the available user types, see [User Types](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/70e95d1d4f514710a0de56067081fd7f.html).

4.  Under *Personal Information*, enter the first and the last name of the user. Use only the allowed characters A-Z, a-z, spaces, and hyphens.

5.  Save.

6.  Select *Send activation e-mail*.

7.  Save your entries.




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_sq4_qvb_kbc"/>

## Result and Next Steps

The new user now receives an activation email and can set a password.

To give them access to SAP Cloud ALM, you additionally need to add them to SAP Cloud ALM and assign the required roles to them, as described in the next step.

**Related Information**  


[SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d17a116432d24470930ebea41977a888.html)

