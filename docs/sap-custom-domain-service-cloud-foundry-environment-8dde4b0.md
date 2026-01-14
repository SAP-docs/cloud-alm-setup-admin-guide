<!-- loio8dde4b05acd84a698cf15377f1851c2a -->

# SAP Custom Domain service, Cloud Foundry environment

This page explains how to connect SAP Custom Domain service, Cloud Foundry environment to SAP Cloud ALM to enable monitoring.

Currently, SAP Custom Domain service supports the following monitoring applications:

-   [Configuration and Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loio8dde4b05acd84a698cf15377f1851c2a__section_khc_1ps_ygc"/>

## Prerequisites

You have a subscription for SAP Custom Domain service, Cloud Foundry environment.



<a name="loio8dde4b05acd84a698cf15377f1851c2a__section_s5w_2ps_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

