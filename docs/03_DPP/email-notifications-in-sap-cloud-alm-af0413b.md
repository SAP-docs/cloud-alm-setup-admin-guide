<!-- loioaf0413b7e06e4a89b794db6c18210f75 -->

# Email Notifications in SAP Cloud ALM

Email notifications can be set up for named users \(that is, users that are maintained in the Identity Authentication tenant\) and for unnamed users. Only the recipient email ID is stored as part of the *Notification Management* app.



<a name="loioaf0413b7e06e4a89b794db6c18210f75__section_zyl_xqm_vvb"/>

## Giving Consent

As soon as new recipients are added to the notification management, they receive an email from **cloudalm-notification@sap.com**, requesting them to verify their email ID and to offer consent to store their email ID and receive notification emails from SAP Cloud ALM.

Once given, the consent is valid for 6 months. Shortly before their consent expires, recipients can renew their own subscription.

Recipients can unsubscribe from notifications at any time by choosing *Unsubscribe* in the footer of any email sent by the *Notification Management* app.



<a name="loioaf0413b7e06e4a89b794db6c18210f75__section_yxb_1rm_vvb"/>

## Housekeeping

Recipients who are not required are deleted once every 10 days. This includes:

-   Recipients who unsubscribed

-   Recipients who were added but did not offer consent to receive emails

-   Recipients whose consent expired


