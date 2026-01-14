<!-- loio052b6179e8f34149a50e498490e4261c -->

# SAP Cell and Gene Therapy Orchestration

This document provides guidance on connecting SAP Cell and Gene Therapy Orchestration to SAP Cloud ALM for monitoring purposes.

Currently, SAP Cell and Gene Therapy Orchestration supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio052b6179e8f34149a50e498490e4261c__section_wtl_skv_xgc"/>

## Prerequisites

You have a subscription for SAP Cell and Gene Therapy Orchestration.



<a name="loio052b6179e8f34149a50e498490e4261c__section_t21_5kv_xgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

