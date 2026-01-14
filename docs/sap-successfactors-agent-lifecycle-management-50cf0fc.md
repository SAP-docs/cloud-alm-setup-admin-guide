<!-- loio50cf0fcf3a624a579379a5e7d183a1ef -->

# SAP SuccessFactors Agent Lifecycle Management

This page explains how to connect SAP SuccessFactors Agent Lifecycle Management to SAP Cloud ALM to enable monitoring.

Currently, SAP SuccessFactors Agent Lifecycle Management supports the following monitoring applications:

-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loio50cf0fcf3a624a579379a5e7d183a1ef__section_bsp_bkl_dhc"/>

## Prerequisites

You have a subscription for SAP SuccessFactors Agent Lifecycle Management.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio50cf0fcf3a624a579379a5e7d183a1ef__section_l5n_dkl_dhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

