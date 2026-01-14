<!-- loioe5e950e438bc4041963e0e12b8549e71 -->

# SAP Credential Store

This page explains how to connect SAP Credential Store to SAP Cloud ALM to enable monitoring.

Currently, SAP Credential Store supports the following monitoring applications:

-   [Configuration and Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loioe5e950e438bc4041963e0e12b8549e71__section_rpk_m4s_ygc"/>

## Prerequisites

You have a subscription for SAP Credential Store.



<a name="loioe5e950e438bc4041963e0e12b8549e71__section_ty3_44s_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

