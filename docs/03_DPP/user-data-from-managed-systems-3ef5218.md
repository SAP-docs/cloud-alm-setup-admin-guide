<!-- loio3ef5218bdec14b4d956b6a8c65c79b52 -->

# User Data from Managed Systems

If you've set up integrations with other SAP solutions or third-party applications, some user-related data from the managed systems may be stored in SAP Cloud ALM.



<a name="loio3ef5218bdec14b4d956b6a8c65c79b52__section_ttc_bgj_2tb"/>

## Transport Management

Once you've enabled transport management, and transport data \(transport request information\) is pushed from the managed system, the transport owner ID is stored in SAP Cloud ALM. No further data related to the transport owner is stored.

The transport owner ID is usually not known in SAP Cloud ALM and therefore can't be found in the *User Management* app. It's only displayed in the *Features* app.

> ### Note:  
> The master data is subject to the lifecycle in the managed system.



<a name="loio3ef5218bdec14b4d956b6a8c65c79b52__section_fgg_jhx_gtb"/>

## Monitoring Applications

User-related data that is collected from managed systems as part of the monitoring data, for example in *Integration and Exception Monitoring*, *Business Process Monitoring*, and *Real User Monitoring*, can only be accessed by users with roles with a sensitive scope.

Within standard memory usage, this user-related monitoring data is considered transient data because it's only visible in SAP Cloud ALM for the duration of the defined retention period. Once the retention period is over, all user-related data from managed systems is deleted and not aggregated. For this reason, the retrieval and manual deletion of user-related monitoring data is currently not supported.

