<!-- loiofbd50d1ee4694e4eb1e94e387a28ec7f -->

# Enabling Email Channel for In-App Notifications

You can enable the email channel for the in-app notifications that are sent by SAP Cloud ALM.

![](images/Screenshot_Enabling_Email_Channel_for_SAP_Cloud_ALM_In-app_Notifications_1_d147bf0.png)



<a name="loiofbd50d1ee4694e4eb1e94e387a28ec7f__section_sxg_srj_5bc"/>

## Procedure

You have two options for sending email notifications:

-   You can use the email service provided by the data center hosting your SAP Cloud ALM tenant. This option doesn't require any admin-level configuration. The email notifications go out under the sender name `SAP Cloud ALM Notifications` and the address `sapcloudalm@notifications.sap.com`.

    > ### Note:  
    > If your SAP Cloud ALM tenant is hosted in the region `eu11` \(EU Access\), no email service is provided by the data center. Please use your own email server as described below.

-   If you want to use your own infrastructure and determine the sender address yourself, you can use your own email server that you are operating under your responsibility.

    For this case, you need to set up an SMTP mail destination in your SAP BTP subaccount for SAP Cloud ALM, as described in [Configuring an SMTP Mail Destination](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/configuring-smtp-mail-destination). If that destination is configured, then the notification emails will only be sent via your own email server.




### Activating Email Notifications \(User Action\)

No matter how the emails are sent, users can turn on email notifications for different types of notifications individually.

Whereas the in-app notifications are active by default, the email notifications work on an opt-in basis. Each user can choose which notifications should trigger an email notification. Administrators can't mass-activate these settings for multiple or all users in the SAP Cloud ALM tenant.

To enable email notifications for your account, click on your user profile in the top-right corner of the SAP Cloud ALM launchpad and choose *Settings* \> *Notifications*. Here, check the *Email* flags for the notification types you want to receive emails for.

You can only select the notification types that are relevant to you, that is, for which you've received notifications in the past. For example, if you've never been assigned to a task, you don’t see this notification type in the settings and can't check the email flag for this notification type.

![](images/Screenshot_Enabling_Email_Channel_for_SAP_Cloud_ALM_In-app_Notifications_2_2feae19.png)



<a name="loiofbd50d1ee4694e4eb1e94e387a28ec7f__section_zmf_cfd_kfc"/>

## Notification Types

This table shows you the available notification types.

****


<table>
<tr>
<th valign="top">

Notification Type

</th>
<th valign="top">

Notification Trigger

</th>
</tr>
<tr>
<td valign="top">

Defects: Assigned to You

</td>
<td valign="top">

notification to defect responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Defects: New Comment

</td>
<td valign="top">

notification to defect responsible if new comment is added

</td>
</tr>
<tr>
<td valign="top">

Features: Assigned to You

</td>
<td valign="top">

notification to feature responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Features: Transport Checks Completed

</td>
<td valign="top">

notification to user who performed the check when completed

</td>
</tr>
<tr>
<td valign="top">

Features: Transports of Copies Failed

</td>
<td valign="top">

notification to user who created the ToC in case of an error

</td>
</tr>
<tr>
<td valign="top">

Projects: New Updates

</td>
<td valign="top">

notification to project lead if SAP Activate Roadmap tasks were updated

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: Assigned to You

</td>
<td valign="top">

notification to quality gate responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: Assigned to Your Team

</td>
<td valign="top">

notification to quality gate team responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: Assigned to You as Involved Party

</td>
<td valign="top">

notification to quality gate responsible on assignment as involved party

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: New Comment

</td>
<td valign="top">

notification to quality gate responsible if new comment added

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: Service Created

</td>
<td valign="top">

notification to quality gate responsible if service created

</td>
</tr>
<tr>
<td valign="top">

Quality Gates: Service Creation Failed

</td>
<td valign="top">

notification to quality gate responsible if service couldn't be created

</td>
</tr>
<tr>
<td valign="top">

Requirements: Assigned to You

</td>
<td valign="top">

notification to requirement responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Requirements: Assigned to You as Involved Party

</td>
<td valign="top">

notification to users added as involved party to a requirement

</td>
</tr>
<tr>
<td valign="top">

Requirements: New Comment

</td>
<td valign="top">

notification to requirement responsible if new comment added

</td>
</tr>
<tr>
<td valign="top">

Tasks: Assigned to You

</td>
<td valign="top">

notification to user story or project task responsible on assignment

</td>
</tr>
<tr>
<td valign="top">

Tasks: Assigned to You as Involved Party

</td>
<td valign="top">

notification to users added as involved party to a user story or project task

</td>
</tr>
<tr>
<td valign="top">

Tasks: New Comment

</td>
<td valign="top">

notification to user story or project task responsible if new comment added

</td>
</tr>
<tr>
<td valign="top">

User Management: Open Role Assignment Requests

</td>
<td valign="top">

notification to user administrator in case of open role assignment requests

</td>
</tr>
</table>



<a name="loiofbd50d1ee4694e4eb1e94e387a28ec7f__section_tyw_d5b_kbc"/>

## Result

After the configuration, you receive email notifications according to your selection.

The emails contain all relevant information for the notification, and a link to the corresponding application in SAP Cloud ALM to process the issue.

![](images/Screenshot_Enabling_Email_Channel_for_SAP_Cloud_ALM_In-app_Notifications_3_fe2a9de.png)

