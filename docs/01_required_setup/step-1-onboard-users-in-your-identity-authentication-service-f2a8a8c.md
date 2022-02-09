<!-- loiof2a8a8cd38044f1aae04d8e5491530d4 -->

# Step 1: Onboard Users in Your Identity Authentication Service

Before you can use SAP Cloud ALM, you need to create or import users in the Identity Authentication tenant.

For information about the Identity Authentication service \(IAS\), including multi-factor-authentication, please refer to [SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d17a116432d24470930ebea41977a888.html).



In SAP Cloud ALM, the Identity Authentication service assumes the role of the identity provider. This means that business users log on to SAP Cloud ALM with the mechanisms and credentials defined in the Identity Authentication tenant.

> ### Note:  
> You can also use an already existing corporate identity provider \(LDAP\), in which case we strongly recommend using Identity Authentication as a proxy. Please note that changing to a corporate identity provider while already using SAP Cloud ALM productively can result in invalidated user IDs and can cause users in SAP Cloud ALM to be deactivated.
> 
> For more information, refer to [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/19f3eca47db643b6aad448b5dc1075ad.html).

When you requested SAP Cloud ALM, SAP automatically established the mutual trust relationship between the Identity Authentication tenant and the subaccount:

-   If you already had an Identity Authentication tenant from the SAP cloud service that you want to manage, it's automatically used as your identity provider for SAP Cloud ALM. As the requesting user, you were made a member in this tenant and didn't automatically receive administrator authorizations in this tenant. You did not receive an additional activation email for your Identity Authentication tenant.

    Your pre-existing tenant may already contain identity information. If you don't want to create new users in the tenant, you can proceed directly to [Step 2: Assign Roles to Users in SAP Cloud ALM](step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md) to add these users to SAP Cloud ALM and assign roles to them.

    If you do want to create new users in the tenant, contact the administrator of the Identity Authentication tenant that is connected to SAP Cloud ALM and either request that they follow the procedure below, or ask them to assign the required role to you by following the steps described in [Managing Administrators in Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/786eea2e06fa4bef84d914a7c319d74c.html).

-   If you didn't have a productive Identity Authentication tenant when you requested SAP Cloud ALM, a new tenant was automatically created for you in the same data center where SAP Cloud ALM is provisioned. This tenant is connected to the SAP Cloud ALM subaccount. As the requesting user, you were made an administrator in this new tenant and received an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for Identity Authentication Service**.

    In the newly generated tenant, no identity information is currently maintained. Before SAP Cloud ALM can be used, users have to be created or imported.








<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_cyj_lcy_hnb"/>

## Prerequisites

-   Your Identity Authentication tenant has been activated.

    If your Identity Authentication tenant was newly created when you requested SAP Cloud ALM, you've received an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for Identity Authentication Service**. Follow the instructions to activate the account and create a user profile for yourself.

-   In your Identity Authentication tenant, you have a user with the role *Manage Users*.

    If you've requested SAP Cloud ALM and a new Identity Authentication tenant was set up for you, your user has automatically received this authorization during the creation of the tenant.

    If someone else requested SAP Cloud ALM or you're using an existing Identity Authentication tenant, in which you don't have this authorization, the tenant administrator can assign the role to you by following the steps described in [Managing Administrators in Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/786eea2e06fa4bef84d914a7c319d74c.html). If you don’t know who your tenant administrator is, create an incident on component BC-IAM-IDS.




<a name="loiof2a8a8cd38044f1aae04d8e5491530d4__section_h1w_1dy_hnb"/>

## Procedure

1.  In the tenant's administration console for Identity Authentication, open the *User Management* app.

    > ### Tip:  
    > You can find a direct link to the administration console of your Identity Authentication tenant in the activation email sent out by **notification@sapnetworkmail.com**.

2.  Choose *+ Add User*.

3.  Fill in the required fields.

    Remember the email address, as you need it to assign roles to the user later.

4.  Choose *Save*.

5.  Select *Send activation e-mail*.

6.  Save your entries.


The new user now receives an activation email and can set a password.

> ### Note:  
> If you've already defined users elsewhere in your landscape, you can also replicate them in the Identity Authentication service by using various tools, such as SAP Identity Management and the Identity Provisioning service.
> 
> For more information, refer to the section [User Management](http://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/228428f9f476449cafd841a68d75b234.html) in the documentation for the Identity Authentication service.

