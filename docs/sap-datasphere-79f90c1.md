<!-- loio79f90c1d9aea4968b2034a9a3e006485 -->

# SAP Datasphere

This page explains how to connect SAP Datasphere to SAP Cloud ALM to enable monitoring.

Currently, SAP Datasphere supports the following monitoring applications:

-   [Configuration and Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)



<a name="loio79f90c1d9aea4968b2034a9a3e006485__section_dbg_fhx_ygc"/>

## Prerequisites

You have a subscription to SAP Datasphere.

The information for your SAP Datasphere tenant has already been imported into SAP Cloud ALM and is available in the *Landscape Management* app. This happens automatically, once per day.



<a name="loio79f90c1d9aea4968b2034a9a3e006485__section_ryn_lhx_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)
-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)
-   [Activate the data collection for Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-job-monitoring)

