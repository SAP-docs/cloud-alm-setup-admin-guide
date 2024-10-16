<!-- loio3ef5218bdec14b4d956b6a8c65c79b52 -->

# User Data from Managed Systems

If you've set up integrations with other SAP solutions or third-party applications, some user-related data from the managed systems may be stored in SAP Cloud ALM.

Hyperscalers, on which SAP products are running, can't access personal data.



<a name="loio3ef5218bdec14b4d956b6a8c65c79b52__section_ttc_bgj_2tb"/>

## Transport Management

Once you've enabled transport management, and transport data \(transport request information\) is pushed from the managed system, the transport owner ID is stored in SAP Cloud ALM. No further data related to the transport owner is stored.

The transport owner ID is usually not known in SAP Cloud ALM and therefore can't be found in the *User Management* app. It's only displayed in the *Features* app.

> ### Note:  
> The master data is subject to the lifecycle in the managed system.



<a name="loio3ef5218bdec14b4d956b6a8c65c79b52__section_fgg_jhx_gtb"/>

## SAP Cloud ALM for Operations

-   User-related data that is collected from managed systems as part of the monitoring data, for example in the *Integration and Exception Monitoring*, *Business Process Monitoring*, and *Real User Monitoring* apps, can only be accessed by users with roles with a sensitive scope and API calls with sensitive scopes.

-   The *Configuration & Security Analysis* app collects configuration data and a few config stores contain user IDs.

-   The *Intelligent Event Processing* app collects personal data only in the context of SAP BTP alert messages.


Within standard memory usage, this user-related monitoring data is considered transient data because it's only visible in SAP Cloud ALM for the duration of the defined retention period. Once the retention period is over, all user-related data from managed systems is deleted and not aggregated. For this reason, the retrieval and manual deletion of user-related monitoring data is currently not supported.

If you purchase the [SAP Cloud ALM, tenant extension](../getting-additional-sap-cloud-alm-tenants-29b6a05.md) and extend the retention period beyond the standard length, the data may no longer be considered transient, which can result in DPP non-compliance.

Moreover, if you extract user-related data from monitoring data with an API, such as the [Raw Data Outbound Logs API](https://help.sap.com/docs/cloud-alm/apis/raw-data-outbound-logs), the caller of the API becomes the personal data controller and is thereby fully responsible in regards of local personal data protection regulations.



<a name="loio3ef5218bdec14b4d956b6a8c65c79b52__section_mtl_k4n_j1c"/>

## More Information

For a full list of SAP Cloud ALM applications collecting personal data, refer to KBA [3429058](https://me.sap.com/notes/3429058).

