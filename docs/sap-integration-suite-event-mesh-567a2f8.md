<!-- loio567a2f81e7cf42cc905c5a83d58a1f95 -->

# SAP Integration Suite \(Event Mesh\)

This page explains how to connect SAP Integration Suite \(Event Mesh\) to SAP Cloud ALM to enable monitoring.

Currently, SAP Integration Suite \(Event Mesh\) supports the following monitoring applications:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)



<a name="loio567a2f81e7cf42cc905c5a83d58a1f95__section_zjf_r3l_dhc"/>

## Prerequisites

-   You have a subscription for SAP Integration Suite \(Event Mesh\).

-   The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

-   Currently, the following data centers for SAP Integration Suite \(Event Mesh\) are **not** supported: JP10 and CN10.



<a name="loio567a2f81e7cf42cc905c5a83d58a1f95__section_hkk_x3l_dhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)

