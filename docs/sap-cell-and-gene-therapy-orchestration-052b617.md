<!-- loio052b6179e8f34149a50e498490e4261c -->

# SAP Cell and Gene Therapy Orchestration

This document provides guidance on connecting SAP Cell and Gene Therapy Orchestration to SAP Cloud ALM for monitoring purposes.

Currently, SAP Cell and Gene Therapy Orchestration supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Cell and Gene Therapy Orchestration](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-cgto.html).

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio052b6179e8f34149a50e498490e4261c__section_a21_jzv_xgc"/>

## Prerequisites

You have a subscription for SAP Cell and Gene Therapy Orchestration.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Cell and Gene Therapy Orchestration](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-cgto.html).



<a name="loio052b6179e8f34149a50e498490e4261c__section_t21_5kv_xgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

