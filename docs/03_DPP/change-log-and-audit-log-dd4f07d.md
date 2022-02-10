<!-- loiodd4f07d7011d44218d7ed3ba25c07407 -->

# Change Log and Audit Log



<a name="loiodd4f07d7011d44218d7ed3ba25c07407__section_vyj_bdl_kkb"/>

## Change Log

SAP Cloud ALM uses change logging to ensure its integrity.

In SAP Cloud ALM, only the *User Management* app is holding master data. This app uses change logging for all changes to its data: authorization changes and changes of user master data.

Change logging in SAP Cloud ALM is implemented on application level and reflects changes, for example:

-   Date and time of access and change

-   New and old values of attributes changed




<a name="loiodd4f07d7011d44218d7ed3ba25c07407__section_iy3_gdl_kkb"/>

## Audit Log Viewer

The audit log records the following information:

-   **Security event log:**

    For applications in SAP Cloud ALM security events are written into the audit log.

-   **Changes to personal data:**

    All changes to the user master data are written into the audit log.

-   **Read access to sensitive personal data:**

    No application in SAP Cloud ALM stores sensitive personal data.

-   **Configuration changes**:

    For some applications, configuration changes are registered in the audit log. For example, changes to project teams in *Projects* are registered.


You can access the audit log of SAP Cloud ALM with the Audit Log Viewer. For information about subscribing to the viewer and authorizing your business users to access the log, see the [Audit Log Viewer for the Cloud Foundry Envionment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e3baa5f1a0c64c44aac8ab3ea3d1b500.html) in the SAP BTP documentation.

> ### Note:  
> Audit log entries are automatically deleted after a defined retention period. For information about audit log retention, see [Audit Log Retention for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/adaefa64228e49ddbe40c15f63a4f74b.html) in the SAP BTP documentation.

