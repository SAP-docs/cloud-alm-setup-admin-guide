<!-- loio7940f543907b48e5b89bbd086cf4cb4e -->

# Commodity Expense ManagementCommodity expense management

This page explains how to connect commodity expense management to SAP Cloud ALM to enable monitoring.

Currently, commodity expense management supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)



## Prerequisites

You have a subscription for commodity expense management.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/bpmon-connecting-services#activating-the-data-collection)

