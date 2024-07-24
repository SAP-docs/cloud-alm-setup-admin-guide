<!-- loioaf0413b7e06e4a89b794db6c18210f75 -->

# Email Notifications in SAP Cloud ALM

There are two different ways in which email notifications are handled in SAP Cloud ALM.



<a name="loioaf0413b7e06e4a89b794db6c18210f75__section_jxc_m1c_gzb"/>

## In-App Notifications

Email notifications for in-app notifications, which are used predominantly for SAP Cloud ALM for implementation, can be set up centrally by following [Enabling Email Channel for In-App Notifications](https://help.sap.com/docs/cloud-alm/setup-administration/enabling-email-notifications).

Once this email channel is enabled, every user can configure for themselves in their profile settings if and for which notification types they want to receive emails. If users no longer want to receive email notifications, they can adjust their notification settings at any time.



<a name="loioaf0413b7e06e4a89b794db6c18210f75__section_d5f_l1c_gzb"/>

## Notifications from SAP Cloud ALM for Operations

Email notifications for SAP Cloud ALM for operations applications are managed in the *Notification Management* app. They can be set up for both named users \(that is, users that are maintained in the Identity Authentication tenant\) and for unnamed users. Only the recipient email ID is stored in SAP Cloud ALM.



### Giving Consent

As soon as new recipients are added to the notification management, they receive an email from **cloudalm-notification@sap.com**, requesting them to verify their email ID and to offer consent to store their email ID and receive notification emails from SAP Cloud ALM.

Once given, the consent is valid for 6 months. Shortly before their consent expires, recipients can renew their own subscription.

Recipients can unsubscribe from notifications at any time by choosing *Unsubscribe* in the footer of any email sent by the *Notification Management* app.



### Housekeeping

Recipients who are not required are deleted once every 10 days. This includes:

-   Recipients who unsubscribed

-   Recipients who were added but did not offer consent to receive emails

-   Recipients whose consent expired


