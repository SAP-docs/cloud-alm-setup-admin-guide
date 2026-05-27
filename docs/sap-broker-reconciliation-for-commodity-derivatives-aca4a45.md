<!-- loioaca4a455a6254a578fcddfd4893b7c5b -->

# SAP Broker Reconciliation for Commodity Derivatives

This document provides guidance on connecting SAP Broker Reconciliation for Commodity Derivatives to SAP Cloud ALM for monitoring purposes.

Currently, SAP Broker Reconciliation for Commodity Derivatives supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Broker Reconciliation for Commodity Derivatives](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-brcd.html).

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loioaca4a455a6254a578fcddfd4893b7c5b__section_a21_jzv_xgc"/>

## Prerequisites

You have a subscription for SAP Broker Reconciliation for Commodity Derivatives.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Broker Reconciliation for Commodity Derivatives](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-brcd.html).



<a name="loioaca4a455a6254a578fcddfd4893b7c5b__section_pf5_2ng_vgc"/>

## **Setup for Integration and Exception Monitoring**

**Setup in SAP Broker Reconciliation for Commodity Derivatives:**

You need to set up the integration between SAP Cloud ALM and SAP Broker Reconciliation for Commodity Derivatives needs in the managed component.

To manage the registration, refer to [Manage SAP Cloud ALM Registration](https://help.sap.com/docs/SAP_BROKER_RECONCILIATION_FOR_COMMODITY_DERIVATIVES/f8c75e7710204ced821267e0498e524f/00f32caa4e5c44ce826c46f60b900219.html).



<a name="loioaca4a455a6254a578fcddfd4893b7c5b__section_jhw_4ng_vgc"/>

## Setup for Real User Monitoring

**Setup in SAP Cloud ALM:**

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

