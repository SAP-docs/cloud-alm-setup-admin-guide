<!-- loio175ee8e057cc4d4b8cc22abed92095e9 -->

# SAP Advanced Commodity Risk Analytics

This page explains how to connect SAP Advanced Commodity Risk Analytics to SAP Cloud ALM to enable monitoring.

Currently, SAP Advanced Commodity Risk Analytics supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio175ee8e057cc4d4b8cc22abed92095e9__section_tsh_lbc_fhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

