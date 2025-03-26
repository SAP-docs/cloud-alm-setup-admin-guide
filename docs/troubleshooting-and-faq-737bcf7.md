<!-- loio737bcf73077c4ed1bc3400648a60f1a8 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Troubleshooting and FAQ

In this document, you can find answers to some of the most common questions and issues that may arise while requesting and setting up SAP Cloud ALM.

To get started, find your current phase or the subject of your issue and jump to the corresponding section:

-   [Before the Provisioning](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_epf_hxk_swb)

-   [After the Provisioning](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_gxf_dyk_swb)

-   [Identity Authentication](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_vhr_kyk_swb)

-   [User Management](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_egv_g1l_swb)

-   [Logon Issues \(Administrators\)](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_zxf_ntv_ryb)

-   [Logon Issues \(Users\)](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_w23_pgp_ryb)

-   [Your SAP Cloud ALM Subaccount](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_a1p_nyk_swb)

-   [Lifecycle Management of Your SAP Cloud ALM Tenant](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_w4v_qq5_tyb)

-   [Related FAQs and Troubleshooting Guides](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_lzj_qcp_wwb)

-   [Further Support](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_ayj_ccr_crb)




<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_epf_hxk_swb"/>

## Before the Provisioning


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You want to know how much it costs to use SAP Cloud ALM.

You're looking for information about license details that entitle you to use SAP Cloud ALM.

</td>
<td valign="top">

SAP Cloud ALM is part of SAP Enterprise Support and other contracts. To find out if you're entitled to provision SAP Cloud ALM, refer to [Availability](availability-288d15a.md). You can start the provisioning process [here](https://me.sap.com/systemsprovisioning/provisioning).

SAP Cloud ALM options for which you may get charged are documented in our [Fair Use](fair-use-94cd95e.md) statement.

</td>
</tr>
<tr>
<td valign="top">

You want to request SAP Cloud ALM on SAP for Me, but you can't access the request dashboard.

</td>
<td valign="top">

Make sure you fulfill the following prerequisites:

-   Your company number has sufficient product and support contracts.

-   You're assigned to the respective customer.

-   You have an S-user with the role `Edit Cloud Data` on SAP for Me.




</td>
</tr>
<tr>
<td valign="top">

You want to determine if an SAP Cloud ALM tenant has already been provisioned for your customer number, or if it can still be provisioned.

</td>
<td valign="top">

Open the [Provisioning](https://me.sap.com/systemsprovisioning/provisioning) dashboard on SAP for Me:

-   If SAP Cloud ALM is available in the section *Products Available for Provisioning*, it hasn't been provisioned yet and you can request it.

-   If SAP Cloud ALM is available in the section *Provisioning Status*, the provisioning is either in progress or completed.




</td>
</tr>
<tr>
<td valign="top">

You have questions about which region \(data center location\) to use for your SAP Cloud ALM tenant.

</td>
<td valign="top">

The region that you select when requesting SAP Cloud ALM corresponds to the location of the data center where your SAP Cloud ALM tenant will be operated.

The *Region* drop-down menu on SAP for Me offers a complete list of all data center locations that are currently available for SAP Cloud ALM. You can also find them under [Supported Data Centers](supported-data-centers-79af00d.md).

For an overview of the data centers that are currently available and those that are planned in the future, see [SAP Cloud ALM Data Centers](https://support.sap.com/en/alm/sap-cloud-alm.html?anchorId=section_1424572767_c) on SAP Support Portal.

[Data Center Locations](https://www.sap.com/about/trust-center/data-center.html?currentLevel=world&mode=solutions&solutionId=NZA842) under SAP Security and Trust contains a full list of all **live** data centers, even ones that are no longer supported for new SAP Cloud ALM tenants \(see next FAQ entry\).

</td>
</tr>
<tr>
<td valign="top">

You want to provision your SAP Cloud ALM tenant in the **Netherlands | Amsterdam** region.

</td>
<td valign="top">

The **Netherlands | Amsterdam** region was available during the initial phase of the SAP Cloud ALM rollout, which is why it may still be listed at different places on SAP websites, for example, under [Data Center Locations](https://www.sap.com/about/trust-center/data-center.html?currentLevel=world&mode=solutions&solutionId=NZA842) under SAP Security and Trust.

However, this region is no longer available for the provisioning of SAP Cloud ALM.

</td>
</tr>
<tr>
<td valign="top">

You have questions about which subdomain name to use for your SAP Cloud ALM tenant.

</td>
<td valign="top">

For more information and recommendations, take a look at the following resources:

-   In the *Start New Provisioning Request* dialog on SAP for Me, choose <span class="SAP-icons-V5"></span> *Help* in the *Subdomain* section.

-   Refer to step 5 in [Requesting SAP Cloud ALM](requesting-sap-cloud-alm-2ba35e6.md).




</td>
</tr>
<tr>
<td valign="top">

You have questions about which Identity Authentication tenant to select for the provisioning.

</td>
<td valign="top">

For more information and recommendations, take a look at the following resources:

-   In the *Start New Provisioning Request* dialog on SAP for Me, choose <span class="SAP-icons-V5"></span> *Help* in the *SAP Cloud Identity Services* section.

-   Refer to step 6 in [Requesting SAP Cloud ALM](requesting-sap-cloud-alm-2ba35e6.md).




</td>
</tr>
<tr>
<td valign="top">

When requesting SAP Cloud ALM on SAP for Me, your Identity Authentication tenant isn't available for selection.

</td>
<td valign="top">

Your Identity Authentication tenant may not show up for the following reasons:

-   It may not be a **productive** tenant.

-   It may be assigned to a different customer ID.


You can find all Identity Authentication tenants assigned to your customer ID and their type at [https://iamtenants.accounts.cloud.sap](https://iamtenants.accounts.cloud.sap).

</td>
</tr>
<tr>
<td valign="top">

You've selected the EU Access region but don't have an Identity Authentication tenant that is located in Europe.

</td>
<td valign="top">

You can either request to migrate one of your existing Identity Authentication tenants to Europe or request a new one, as described in [Get Your Tenant](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/get-your-tenant#loio460766b1b08d48a0b4adfb230c60a001__note_dd4_jk4_12c).

</td>
</tr>
<tr>
<td valign="top">

You want to know in which SAP BTP global account SAP Cloud ALM will be provisioned.

</td>
<td valign="top">

During the provisioning, a dedicated global account is created on SAP BTP specially for SAP Cloud ALM.

For the reasoning behind this, refer to KBA [3152095](https://me.sap.com/notes/3152095).

</td>
</tr>
<tr>
<td valign="top">

You're a customer based in China and can't request SAP Cloud ALM because the *Start Provisioning* button on SAP for Me is grayed out.

</td>
<td valign="top">

Refer to KBA [3451531](https://me.sap.com/notes/3451531).

</td>
</tr>
<tr>
<td valign="top">

You're looking for general information on how to start the provisioning for cloud products on SAP for Me.

</td>
<td valign="top">

Refer to KBA [3066901](https://me.sap.com/notes/3066901).

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_gxf_dyk_swb"/>

## After the Provisioning


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You want to find the welcome emails and activation emails that were sent to you when you requested SAP Cloud ALM.

</td>
<td valign="top">

**Welcome Emails from SAP Cloud ALM**

-   If you requested SAP Cloud ALM, you've received a welcome email with the subject **Access information for SAP Cloud ALM**.

-   If someone else requested SAP Cloud ALM and added you to the system, you've received a welcome email with the subject **Welcome to SAP Cloud ALM**.


**Activation Emails from the Identity Authentication Service**

-   If you didn't have a productive Identity Authentication tenant when you requested SAP Cloud ALM, a new Identity Authentication tenant was created for you. You've received an email with the subject **Activate Your Account for Identity Authentication Service**.

-   If someone added your user to a productive Identity Authentication tenant, you've received an email with the subject **Activate Your Account for User Profile**.

-   If someone added your user to a productive Identity Authentication tenant as an administrator, you've received an email with the subject **Activate Your Account for Administration Console**.




</td>
</tr>
<tr>
<td valign="top">

You can't find or didn't receive your activation email for your Identity Authentication tenant.

</td>
<td valign="top">

Search for an email with the subject **Activate Your Account for...** Don't forget to also check your spam folder.

If you still can't find it, create a case on component SV-CLM-INF-ONB to have the activation email resent to you.

</td>
</tr>
<tr>
<td valign="top">

You want to add an administrator to the global account and/or subaccounts for SAP Cloud ALM in SAP BTP.

</td>
<td valign="top">

Refer to KBA [3342350](https://me.sap.com/notes/3342350).

</td>
</tr>
<tr>
<td valign="top">

You requested SAP Cloud ALM and want to assign additional administrators who can complete the setup of SAP Cloud ALM.

</td>
<td valign="top">

Refer to KBA [3248116](https://me.sap.com/notes/3248116).

</td>
</tr>
<tr>
<td valign="top">

You want to find out who originally requested your SAP Cloud ALM tenant.

</td>
<td valign="top">

Open the [Provisioning](https://me.sap.com/systemsprovisioning/provisioning) dashboard on SAP for Me and find the entry for *SAP Cloud ALM* in the *Provisioning Status* section.

Click on the *Provided* status. Under *Requested at*, you can see which S-user has requested SAP Cloud ALM.

</td>
</tr>
<tr>
<td valign="top">

The person who originally requested SAP Cloud ALM is no longer available and you want to give yourself or another user full administrator privileges.

</td>
<td valign="top">

Refer to KBA [3365171](https://me.sap.com/notes/3365171).

</td>
</tr>
<tr>
<td valign="top">

You're an Ultimate Global Customer with multiple customer numbers and want to import all your customer numbers for cloud subscriptions into one SAP Cloud ALM system. You don't want to maintain several SAP Cloud ALM systems.

</td>
<td valign="top">

Refer to SAP Note [3070306](https://me.sap.com/notes/3070306).

</td>
</tr>
<tr>
<td valign="top">

You want to know more about the entities that were created as part of the provisioning of your SAP Cloud ALM tenant, which are listed on the [Systems & Provisioning](https://me.sap.com/systemsprovisioning/systems) page on SAP for Me.

</td>
<td valign="top">

Refer to [Finding Your Systems on SAP for Me](finding-your-systems-on-sap-for-me-9d4aa2a.md).

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_vhr_kyk_swb"/>

## Identity Authentication


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You have questions about which Identity Authentication tenant to select for the provisioning.

</td>
<td valign="top">

Refer to the section [Before the Provisioning](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_epf_hxk_swb).

</td>
</tr>
<tr>
<td valign="top">

You want to connect SAP Cloud ALM to a non-production Identity Authentication tenant.

</td>
<td valign="top">

We don't recommend connecting SAP Cloud ALM to a non-production Identity Authentication tenant because there's no way to migrate users from a test Identity Authentication tenant to a production Identity Authentication tenant. This could cause issues in your landscape if you later decide to use SAP Cloud ALM in a productive manner.

</td>
</tr>
<tr>
<td valign="top">

You want to use a different Identity Authentication tenant than the one that was provisioned with SAP Cloud ALM.

</td>
<td valign="top">

Refer to KBA [3020352](https://me.sap.com/notes/3020352).

</td>
</tr>
<tr>
<td valign="top">

You want to use a different Identity Authentication in SAP Cloud ALM than the one you're using for your managed system.

</td>
<td valign="top">

Creating multiple productive Identity Authentication tenants splits the user base and requires an individual administrator for each tenant. This means that users that are maintained in the Identity Authentication tenant of your managed system also need to be created in the Identity Authentication tenant that is used for SAP Cloud ALM, if they need to work in both solutions.

If you still want to change your Identity Authentication tenant assignment in SAP Cloud ALM, refer to KBA [3020352](https://me.sap.com/notes/3020352).

</td>
</tr>
<tr>
<td valign="top">

You want to use a corporate identity provider \(LDAP\) for SAP Cloud ALM.

</td>
<td valign="top">

You can also use an already existing corporate identity provider \(LDAP\), in which case we strongly recommend using Identity Authentication as a proxy. Changing to a corporate identity provider while already using SAP Cloud ALM productively can result in invalidated user IDs and can cause users in SAP Cloud ALM to be deactivated.

For more information, refer to [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/19f3eca47db643b6aad448b5dc1075ad.html).

</td>
</tr>
<tr>
<td valign="top">

You want to find out which Identity Authentication tenants are assigned to your customer ID and who the administrator is.

</td>
<td valign="top">

Refer to [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/f56e6f24e373404087d6a1a9a13515a2.html).

</td>
</tr>
<tr>
<td valign="top">

You want to find out which Identity Authentication tenant is used for your SAP Cloud ALM tenant.

</td>
<td valign="top">

Follow the first 6 steps described in KBA [3020352](https://me.sap.com/notes/3020352).

</td>
</tr>
<tr>
<td valign="top">

You're facing issues with your Identity Authentication tenant after requesting SAP Cloud ALM.

</td>
<td valign="top">

Refer to KBA [3090756](https://me.sap.com/notes/3090756).

</td>
</tr>
<tr>
<td valign="top">

Your Identity Authentication tenant was created in a different data center than SAP Cloud ALM.

</td>
<td valign="top">

You can request it be moved by raising a case on component BC-IAM-IDS.

</td>
</tr>
<tr>
<td valign="top">

You can't access your Identity Authentication tenant. The following error message appears:

*Sorry... You entered a valid URL, but you are not authorized to view the content; contact your system administrator.*

</td>
<td valign="top">

Refer to KBA [2579343](https://i7p.wdf.sap.corp/sap/support/notes/2579343).

</td>
</tr>
<tr>
<td valign="top">

When you sign in to SAP Cloud ALM, you can choose between multiple identity providers.

</td>
<td valign="top">

Refer to KBA [3086201](https://me.sap.com/notes/3086201).

</td>
</tr>
<tr>
<td valign="top">

There's an unknown user with one of the following names in your Identity Authentication tenant:

-   *SAP Cockpit* 

-   *Service Cockpit*

-   *SAP Cloud Platform NEO Service Cockpit* 

-   *Service Provider Cockpit* 

-   *SF Admin Center* 




</td>
<td valign="top">

Refer to KBA [3281767](https://me.sap.com/notes/3281767).

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_egv_g1l_swb"/>

## User Management


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You want to create a large number of users for SAP Cloud ALM.

</td>
<td valign="top">

There is no limit to the number of users that can be created for an SAP Cloud ALM system.

</td>
</tr>
<tr>
<td valign="top">

You've added users in the *User Management* app in SAP Cloud ALM, but they haven't received a welcome email.

</td>
<td valign="top">

The onboarding of users consists of two steps that take place in two different applications:

-   *User Management* in your Identity Authentication \(IAS\) tenant

-   *User Management* in SAP Cloud ALM


Before you can add users in SAP Cloud ALM and assign roles to them, you need to create them in your Identity Authentication tenant.

For more information, refer to [Step 1: Onboard Users in the Identity Authentication Service](01_required_setup/step-1-onboard-users-in-the-identity-authentication-service-f2a8a8c.md).

</td>
</tr>
<tr>
<td valign="top">

You want to create a user in your SAP Cloud ALM tenant that SAP development can use for troubleshooting and support purposes.

</td>
<td valign="top">

Refer to KBA [3032960](https://me.sap.com/notes/3032960).

</td>
</tr>
<tr>
<td valign="top">

You have the role *Project Administrator*, but you don't have access to the *User Management* app to create business users in SAP Cloud ALM.

</td>
<td valign="top">

The role *Project Administrator* only enables you to administer projects and assign users that have already been added to SAP Cloud ALM.

To add users to SAP Cloud ALM, you need the role *Global Administrator* or *User Administrator*.

For more information, refer to [Step 2: Assign Roles to Users in SAP Cloud ALM](01_required_setup/step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md).

</td>
</tr>
<tr>
<td valign="top">

Users in SAP Cloud ALM have the status *Expiring Soon*.

</td>
<td valign="top">

In SAP Cloud ALM, the Identity Authentication service \(IAS\) assumes the role of an identity provider. If users are deleted in the Identity Authentication tenant or if user IDs are changed due to changes in the Identity Authentication configuration \(for example, from email to login name\), the affected users are automatically deactivated in SAP Cloud ALM after a grace period of 30 days.

The number of days specified by the *Expires Soon* status indicates the end of the grace period after which the user will be deactivated. A user with this status is not authorized to use SAP Cloud ALM.

If you revert the Identity Authentication configuration within the grace period, the user's personal settings and project assignments are still valid. If you want to keep your current configuration, the personal settings and project assignments are lost and you need to reassign the authorizations to the new user ID.

</td>
</tr>
<tr>
<td valign="top">

You want to centralize the authorization management in SAP Cloud ALM.

</td>
<td valign="top">

You can use the Identity Provisioning Service \(IPS\) as a tool for user provisioning to centralize authorization management in SAP Cloud ALM.

Set up a provisioning job in the IPS to synchronize the users between your identity provider and the SAP BTP Cockpit.

For more information, see the following blog post [Centralize Authorization Management of SAP Cloud ALM Using the Identity Provisioning Service](https://community.sap.com/t5/technology-blogs-by-sap/centralize-authorization-management-of-sap-cloud-alm-using-the-identity/ba-p/13609455)

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_zxf_ntv_ryb"/>

## Logon Issues \(Administrators\)


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You can't find or didn't receive your activation email for your Identity Authentication tenant.

</td>
<td valign="top">

Search for an email with the subject **Activate Your Account for...** Don't forget to also check your spam folder.

If you still can't find it, create a case on component SV-CLM-INF-ONB to have the activation email resent to you.

</td>
</tr>
<tr>
<td valign="top">

You can't sign in to SAP Cloud ALM.

</td>
<td valign="top">

Verify that you've entered the correct credentials: You need to sign in with the email address and password defined in the Identity Authentication tenant, not your S-user.

Make sure you've completed all steps in [Required Setup for SAP Cloud ALM](01_required_setup/required-setup-for-sap-cloud-alm-80b2c30.md) and that you've activated your user profile in the Identity Authentication tenant.

If you can't find the activation email, go to your Identity Authentication tenant, enter your email address, and choose *Forgot password*. You will receive a new activation email.

</td>
</tr>
<tr>
<td valign="top">

When signing in to SAP Cloud ALM, you can choose between multiple identity providers.

</td>
<td valign="top">

Refer to KBA [3086201](https://me.sap.com/notes/3086201).

</td>
</tr>
<tr>
<td valign="top">

When you try to access SAP Cloud ALM via the tenant URL, the following error messages appear:

*Sorry a technical error occurred during the logon process. Please contact your technical support.*

*Sorry, you can't sign in right now.*

</td>
<td valign="top">

Refer to SAP Note [3046343](https://me.sap.com/notes/3046343).

</td>
</tr>
<tr>
<td valign="top">

When you try to access SAP Cloud ALM from the SAP BTP cockpit, an HTTP 500 error occurs. But from outside the organization, for example SAP support, you can access the application.

</td>
<td valign="top">

Check whether you have a firewall setting that prevents you from accessing the application. You may need to specify a port.

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_w23_pgp_ryb"/>

## Logon Issues \(Users\)


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You can't find your SAP Cloud ALM welcome email.

</td>
<td valign="top">

Search for an email with the subject **Welcome to SAP Cloud ALM**. Don't forget to also check your spam folder.

If you can't find one, ask your administrator to give you the URL of your SAP Cloud ALM tenant. You can sign in directly with this URL.

</td>
</tr>
<tr>
<td valign="top">

You can't find your activation email from the Identity Authentication Service.

</td>
<td valign="top">

Search for an email with the subject **Activate Your Account for User Profile**. Don't forget to also check your spam folder.

If you can't find one, ask your administrator to resend the email as described in [Send Reset Password Email](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/da55abf8d0e54eb6825a13777bef4eb1.html).

</td>
</tr>
<tr>
<td valign="top">

You can't sign in to SAP Cloud ALM.

</td>
<td valign="top">

Verify that you've entered the correct credentials: You need to sign in with the credentials defined in the connected Identity Authentication tenant, not your S-user.

Check with your administrator if your user profile in the Identity Authentication tenant has been created.

</td>
</tr>
<tr>
<td valign="top">

When logging on to SAP Cloud ALM, you can choose between multiple identity providers.

</td>
<td valign="top">

Contact your administrator and refer them to KBA [3086201](https://me.sap.com/notes/3086201).

</td>
</tr>
<tr>
<td valign="top">

You can sign in to SAP Cloud ALM but do not see any apps.

</td>
<td valign="top">

Your user may not yet have any roles in SAP Cloud ALM.

Ask your administrator to assign roles to you in the *User Management* app or in the SAP BTP cockpit, as described in [Step 2: Assign Roles to Users in SAP Cloud ALM](01_required_setup/step-2-assign-roles-to-users-in-sap-cloud-alm-7304b17.md).

</td>
</tr>
<tr>
<td valign="top">

You want to know who the administrator of your Identity Authentication tenant is.

</td>
<td valign="top">

Refer to [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/f56e6f24e373404087d6a1a9a13515a2.html).

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_a1p_nyk_swb"/>

## Your SAP Cloud ALM Subaccount


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You can't find your subaccount for SAP Cloud ALM in the SAP BTP cockpit.

</td>
<td valign="top">

Refer to KBA [3123560](https://me.sap.com/notes/3123560).

</td>
</tr>
<tr>
<td valign="top">

You want to know why a new global account is created as part of the provisioning of SAP Cloud ALM.

</td>
<td valign="top">

Refer to KBA [3152095](https://me.sap.com/notes/3152095).

</td>
</tr>
<tr>
<td valign="top">

You want to subscribe to additional products, applications, or services in the subaccount containing your SAP Cloud ALM subscription.

</td>
<td valign="top">

You can't subscribe to any additional products or applications or to services that aren't related to SAP Cloud ALM in the subaccount containing your SAP Cloud ALM subscription. The subaccount is set up exclusively for SAP Cloud ALM.

For more information, refer to KBA [3551681](https://me.sap.com/notes/3551681).

</td>
</tr>
<tr>
<td valign="top">

You want to delete your SAP Cloud ALM subscription in your subaccount.

</td>
<td valign="top">

Refer to KBA [3247776](https://me.sap.com/notes/3247776).

> ### Caution:  
> Deleting your SAP Cloud ALM subscription causes all created artifacts, stored data, and current configurations to be deleted as well. It will not re-enable you to request SAP Cloud ALM on SAP for Me.



</td>
</tr>
<tr>
<td valign="top">

You want to delete your SAP Cloud ALM subaccount.

</td>
<td valign="top">

After you've deleted your SAP Cloud ALM subscription from your subaccount, you can delete the subaccount.

Please note that once you've deleted your subaccount, you won't be able to use the automated provisioning on SAP for Me if you want to use SAP Cloud ALM again in the future. Instead, you'll need to carry out the setup manually.

If you may want to use SAP Cloud ALM again in the future, consider temporarily stopping users from logging on to SAP Cloud ALM, for example by removing the *Available for User Logon* flag in the trust configuration of your identity provider. When you're ready to use SAP Cloud ALM again, you can re-enable the user logon.

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_w4v_qq5_tyb"/>

## Lifecycle Management of Your SAP Cloud ALM Tenant


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Resolution

</th>
</tr>
<tr>
<td valign="top">

You want to set up a second SAP Cloud ALM tenant.

</td>
<td valign="top">

By purchasing *SAP Cloud ALM, tenant extension*, you're entitled to request additional SAP Cloud ALM tenants for the same customer number.

There's no restriction on the number of tenants that you can purchase. You can get as many as you need for your organization and purposes.

For more information, see [Getting Additional SAP Cloud ALM Tenants](getting-additional-sap-cloud-alm-tenants-29b6a05.md).

</td>
</tr>
<tr>
<td valign="top">

You want to move your SAP Cloud ALM application to a different data center.

You want to move your SAP Cloud ALM application to a different region.

You want to change the region of your SAP Cloud ALM application.

</td>
<td valign="top">

It's currently not possible to move your SAP Cloud ALM application from the data center in which it was originally provisioned to a different data center.

However, you can **migrate** your SAP Cloud ALM application to a different data center. For more information, refer to the next FAQ entry.

</td>
</tr>
<tr>
<td valign="top">

You want to migrate your SAP Cloud ALM application to a different data center.

You want to migrate your SAP Cloud ALM application to a different region.

You want to change the region of your SAP Cloud ALM application.

</td>
<td valign="top">

Refer to KBA [3352417](https://me.sap.com/notes/3352417).

Please also consider the data center restrictions listed in KBA [3257720](https://me.sap.com/notes/3257720).

For more information about SAP Cloud ALM data center locations, refer to the FAQ entries about data centers in the section [Before the Provisioning](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_epf_hxk_swb).

</td>
</tr>
<tr>
<td valign="top">

You want to change or rename the subdomain of your SAP Cloud ALM tenant.

</td>
<td valign="top">

It's currently not possible to change or rename the subdomain of an existing SAP Cloud ALM tenant.

However, if you're willing to accept loss of data in your current SAP Cloud ALM tenant, you can follow the FAQ entry about migrating to a new data center. While setting up your new SAP Cloud ALM tenant in the same or in a new data center, you can choose a new subdomain.

</td>
</tr>
<tr>
<td valign="top">

After deleting your SAP Cloud ALM application, you want to set it up again from scratch.

</td>
<td valign="top">

Refer to KBA [3257720](https://me.sap.com/notes/3257720).

</td>
</tr>
<tr>
<td valign="top">

You want to decommission SAP Cloud ALM.

</td>
<td valign="top">

Official decommissioning of SAP Cloud ALM isn't yet available.

However, you can use a housekeeping job to delete services from the *Landscape Management* app.

You can also delete your SAP Cloud ALM subscription in your subaccount and then delete your subaccount. For more information, refer to the corresponding FAQ entries in the section [Your SAP Cloud ALM Subaccount](troubleshooting-and-faq-737bcf7.md#loio737bcf73077c4ed1bc3400648a60f1a8__section_a1p_nyk_swb).

</td>
</tr>
<tr>
<td valign="top">

You want to move your SAP Cloud ALM tenant from one customer number to another customer number.

</td>
<td valign="top">

Refer to SAP Note [3282741](https://me.sap.com/notes/3282741).

</td>
</tr>
<tr>
<td valign="top">

The end of your contract for SAP Cloud ALM is approaching, as illustrated by the following indicators:

-   The end date that is listed under *Contract Start* in the *Provisioning* dashboard on SAP for Me is approaching.

-   A warning message is displayed in the SAP BTP cockpit, such as *"Your global account SAP Cloud ALM is reaching the contract end date"*.




</td>
<td valign="top">

Your entitlement for SAP Cloud ALM is derived from other product and support licenses that you have. To continue to use SAP Cloud ALM, ensure that relevant expiring licenses are renewed in time.

To see details about the license materials that are related to your entitlement, such as entitled quantity, order ID, and duration, open the [Provisioning](https://me.sap.com/systemsprovisioning/provisioning) dashboard on SAP for Me and expand the *Materials* field.

For related information, refer to [Closing Your Account](closing-your-account-219d7d0.md) and KBA [3066901](https://me.sap.com/notes/3066901).

</td>
</tr>
<tr>
<td valign="top">

You want to be informed and receive timely updates regarding SAP Cloud ALM and your other SAP cloud services, for example, about planned and unplanned downtimes.

</td>
<td valign="top">

Refer to KBA [2900069](https://me.sap.com/notes/2900069).

</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_lzj_qcp_wwb"/>

## Related FAQs and Troubleshooting Guides

-   [Most Common Onboarding Issues \(KBA\)](https://launchpad.support.sap.com/#/notes/3270970)

-   [Troubleshooting for Landscape Management](https://help.sap.com/docs/cloud-alm/applicationhelp/troubleshooting-for-landscape-management)

-   [Troubleshooting for Managed ABAP Systems \(SAP Support Portal\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/calm-op-troubleshooting/calm-troubleshooting-abap.html)

-   [Application Lifecycle Management – Questions & Answers \(PDF\)](https://support.sap.com/content/dam/support/en_us/library/ssp/alm/QA_ALM.pdf) \(for general SAP ALM and SAP Cloud ALM questions\)




<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_ayj_ccr_crb"/>

## Further Support

If you encounter issues that aren't listed here or if you're unable to perform the described resolutions yourself, [schedule an expert session](https://me.sap.com/app/sae) or [create a support ticket](https://me.sap.com/app/casecreate) on the following components:


<table>
<tr>
<th valign="top">

Area

</th>
<th valign="top">

Component

</th>
</tr>
<tr>
<td valign="top">

Provisioning and setup of SAP Cloud ALM

</td>
<td valign="top">

SV-CLM-INF-ONB

</td>
</tr>
<tr>
<td valign="top">

Onboarding of users and assignment of roles

</td>
<td valign="top">

SV-CLM-INF-UAM

</td>
</tr>
<tr>
<td valign="top">

Setup and usage of landscape management

</td>
<td valign="top">

SV-CLM-INF-LMS

</td>
</tr>
</table>

