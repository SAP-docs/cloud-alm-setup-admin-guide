<!-- loio713bf838ea614dbf8a4408a5d3d046f8 -->

# SAP Order and Delivery Scheduling

This page explains how to connect SAP Order and Delivery Scheduling to SAP Cloud ALM to enable monitoring.

Currently, SAP Order and Delivery Scheduling supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio713bf838ea614dbf8a4408a5d3d046f8__section_kts_y2t_bhc"/>

## Prerequisites

You have a subscription for SAP Order and Delivery Scheduling.



<a name="loio713bf838ea614dbf8a4408a5d3d046f8__section_czt_z2t_bhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

