<!-- loiodd4f07d7011d44218d7ed3ba25c07407 -->

# Change Log and Audit Log



<a name="loiodd4f07d7011d44218d7ed3ba25c07407__section_vyj_bdl_kkb"/>

## Change Log

In SAP Cloud ALM, only the *User Management* app contains master data. This app uses change logging for all changes to its data, such as changes of authorizations and user master data.

Change logging in SAP Cloud ALM is implemented on application level and reflects changes, such as the date and time of the access and the change, and new and old values of the changed attributes.



<a name="loiodd4f07d7011d44218d7ed3ba25c07407__section_iy3_gdl_kkb"/>

## SAP Audit Log Viewer Service for SAP BTP

The SAP Audit Log Viewer service records the following information:

-   **Security event log**: Security events in SAP Cloud ALM applications

-   **Changes to personal data**: All changes to the user master data

-   **Read access to sensitive personal data**: No application in SAP Cloud ALM stores sensitive personal data.

-   **Configuration changes**: For some applications, configuration changes are registered in the SAP Audit Log Viewer service. For example, changes to project teams in *Projects and Setup* are registered.


Audit log entries are automatically deleted after a defined retention period. For information about audit log retention, see [Audit Log Retention for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/adaefa64228e49ddbe40c15f63a4f74b.html) in the SAP BTP documentation.

You can access the audit log of SAP Cloud ALM with the SAP Audit Log Viewer service. For information about subscribing to the viewer and authorizing your business users to access the log, refer to [Audit Log Viewer for the Cloud Foundry Environment](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/e3baa5f1a0c64c44aac8ab3ea3d1b500.html) in the SAP BTP documentation.

