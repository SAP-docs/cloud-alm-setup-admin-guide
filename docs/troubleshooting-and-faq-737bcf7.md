<!-- loio737bcf73077c4ed1bc3400648a60f1a8 -->

# Troubleshooting and FAQ

<a name="loio737bcf73077c4ed1bc3400648a60f1a8__table_nvd_bh5_brb"/>


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

When you request SAP Cloud ALM, you get the error message *Error - Provisioning cannot be started, system Unavailable*.



</td>
<td valign="top">

Refer to SAP Note [3076993](https://launchpad.support.sap.com/#/notes/3076993).



</td>
</tr>
<tr>
<td valign="top">

After requesting SAP Cloud ALM, you have two subaccounts.



</td>
<td valign="top">

Determine which subaccount is incomplete and should be deleted. Refer to SAP Note [3050017](https://launchpad.support.sap.com/#/notes/3050017).



</td>
</tr>
<tr>
<td valign="top">

You want to subscribe to additional applications in the subaccount containing your SAP Cloud ALM subscription.



</td>
<td valign="top">

You can't subscribe to any additional applications in the subaccount containing your SAP Cloud ALM subscription. The subaccount is set up exclusively for SAP Cloud ALM.



</td>
</tr>
<tr>
<td valign="top">

You're facing issues with your Identity Authentication tenant after requesting SAP Cloud ALM.



</td>
<td valign="top">

Refer to KBA [3090756](https://launchpad.support.sap.com/#/notes/3090756).



</td>
</tr>
<tr>
<td valign="top">

You can't find or didn't receive your activation email for your Identity Authentication tenant.



</td>
<td valign="top">

Search for an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for...** Don't forget to also check your spam folder.

If you still can't find it, create an incident on component SV-CLM-INF-ONB to have the activation email resent to you.



</td>
</tr>
<tr>
<td valign="top">

You want to find the welcome emails and activation emails that were sent to you when you requested SAP Cloud ALM.



</td>
<td valign="top">

**Welcome Emails from SAP Cloud ALM**

-   If you requested SAP Cloud ALM, you've received a welcome email from **SAP No Reply Provisioning** with the subject **Access information for SAP Cloud ALM**.

-   If someone else requested SAP Cloud ALM and added you to the system, you've received a welcome email from **SAP Cloud ALM Notifications** with the subject **Welcome to SAP Cloud ALM**.


**Activation Emails from the Identity Authentication Service**

-   If you didn't have a productive Identity Authentication tenant when you requested SAP Cloud ALM, a new Identity Authentication tenant was created for you. You've received an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for Identity Authentication Service**.

-   If someone added your user to a productive Identity Authentication tenant, you've received an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for User Profile**.

-   If someone added your user to a productive Identity Authentication tenant as an administrator, you've received an email from **notification@sapnetworkmail.com** with the subject **Activate Your Account for Administration Console**.




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

You want to use a different Identity Authentication tenant than the one that was provisioned with SAP Cloud ALM.



</td>
<td valign="top">

Refer to SAP Note [3020352](https://launchpad.support.sap.com/#/notes/3020352).



</td>
</tr>
<tr>
<td valign="top">

You want to use a different Identity Authentication in SAP Cloud ALM than the one you're using for your managed system.



</td>
<td valign="top">

Creating multiple productive Identity Authentication tenants splits the user base and requires an individual administrator for each tenant. This means that users that are maintained in the Identity Authentication tenant of your managed system also need to be created in the Identity Authentication tenant that is used for SAP Cloud ALM, if they need to work in both solutions.

If the Identity Authentication tenant of your managed system existed before SAP Cloud ALM was created, it was automatically reused as the identity provider for SAP Cloud ALM. If you want to change this assignment, refer to SAP Note [3020352](https://launchpad.support.sap.com/#/notes/3020352).



</td>
</tr>
<tr>
<td valign="top">

Your Identity Authentication tenant was created in a different data center than SAP Cloud ALM.



</td>
<td valign="top">

You can request it be moved by raising an incident on component BC-IAM-IDS.



</td>
</tr>
<tr>
<td valign="top">

You're an Ultimate Global Customer with multiple customer numbers and want to import all your customer numbers for cloud subscriptions into one SAP Cloud ALM system. You don't want to maintain several SAP Cloud ALM systems.



</td>
<td valign="top">

Refer to SAP Note [3070306](https://launchpad.support.sap.com/#/notes/3070306).



</td>
</tr>
<tr>
<td valign="top">

You want to find out which Identity Authentication tenants are assigned to your customer ID.



</td>
<td valign="top">

Refer to [Viewing Assigned Tenants and Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/LATEST/en-US/f56e6f24e373404087d6a1a9a13515a2.html).



</td>
</tr>
<tr>
<td valign="top">

When you log on to SAP Cloud ALM, you can choose between multiple identity providers.



</td>
<td valign="top">

Refer to SAP Note [3086201](https://launchpad.support.sap.com/#/notes/3086201).



</td>
</tr>
<tr>
<td valign="top">

You can't log on to SAP Cloud ALM.



</td>
<td valign="top">

Verify that you've entered the correct credentials: You need to log on with the email address and password defined in the Identity Authentication tenant, not your S-user.

Make sure you've completed all steps in section *Required Setup for SAP Cloud ALM* and that you've activated your user profile in the Identity Authentication tenant.

You can find a link in the activation email that was sent to you when you requested SAP Cloud ALM or when the tenant administrator created a user for you. If you can't find the activation email, go to your Identity Authentication tenant, enter your email address, and choose *Forgot password*. You will receive a new activation email.

For more information, refer to KBA [3117604](https://launchpad.support.sap.com/#/notes/3117604).



</td>
</tr>
<tr>
<td valign="top">

You can log on to SAP Cloud ALM but do not see any apps.



</td>
<td valign="top">

Refer to KBA [2982909](https://launchpad.support.sap.com/#/notes/2982909).



</td>
</tr>
<tr>
<td valign="top">

When you try to access SAP Cloud ALM via the tenant URL the following error messages appear:

*Sorry a technical error occurred during the logon process. Please contact your technical support.*

*Sorry, you can't sign in right now.*



</td>
<td valign="top">

Refer to SAP Note [3046343](https://launchpad.support.sap.com/#/notes/3046343).



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
<tr>
<td valign="top">

When you execute the report `/SDF/CALM_SETUP` to register an ABAP Business Suite system with SAP Cloud ALM, you get the error message *Cannot Create HTTP client: Operation Successfully executed*.



</td>
<td valign="top">

Refer to SAP Note [3090768](https://launchpad.support.sap.com/#/notes/3090768).



</td>
</tr>
<tr>
<td valign="top">

After executing the report `/SDF/CALM_SETUP` to register SAP Solution Manager 7.2, the system appears in the *Landscape Management* app. However, you can't enable monitoring scenarios for it.



</td>
<td valign="top">

There is no support for SAP Solution Manager in SAP Cloud ALM.



</td>
</tr>
<tr>
<td valign="top">

A syntax error occurs after the ST-PI upgrade and short dumps occur after the configuration of SAP Cloud ALM.



</td>
<td valign="top">

After an ST-PI update, there are missing code corrections, batch user, and roles. The roles needed for the technical user specified for batch processing are not usable or not available.

Refer to SAP Note [3054258](https://i7p.wdf.sap.corp/sap/support/notes/3054258) and [2985521](https://launchpad.support.sap.com/#/notes/2985521).



</td>
</tr>
<tr>
<td valign="top">

You want to change the language settings in SAP Cloud ALM.



</td>
<td valign="top">

The default display language of the solution is based on the language that is maintained in your browser settings.

You can change the language either by changing it in your browser settings or by clicking on your user profile at the top-right corner of the SAP Cloud ALM launchpad and choosing *Settings* \> *Language & Region*.



</td>
</tr>
<tr>
<td valign="top">

You want to create a user in your SAP Cloud ALM tenant that SAP development can use for troubleshooting and support purposes.



</td>
<td valign="top">

Refer to KBA [3032960](https://launchpad.support.sap.com/#/notes/3032960).



</td>
</tr>
<tr>
<td valign="top">

You want to decommission SAP Cloud ALM.



</td>
<td valign="top">

Official decommission of SAP Cloud ALM isn't yet available. However, you can use a housekeeping job to delete cloud services from the *Landscape Management* app.



</td>
</tr>
</table>



<a name="loio737bcf73077c4ed1bc3400648a60f1a8__section_ayj_ccr_crb"/>

## Further Support

If you encounter issues that aren't listed here or if you're unable to perform the described resolutions yourself, raise an incident on the following components:


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

**Related Information**  


[Troubleshooting for Managed ABAP Systems \(SAP Support Portal\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/calm-op-troubleshooting/calm-troubleshooting-abap.html)

