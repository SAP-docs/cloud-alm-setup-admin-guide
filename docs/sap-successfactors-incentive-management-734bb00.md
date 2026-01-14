<!-- loio734bb00a42144385b134d1df371cebe6 -->

# SAP SuccessFactors Incentive Management

This page explains how to connect SAP SuccessFactors Incentive Management to SAP Cloud ALM to enable monitoring.

Currently, SAP SuccessFactors Incentive Management supports the following monitoring applications:

-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loio734bb00a42144385b134d1df371cebe6__section_h13_5kl_dhc"/>

## Prerequisites

You have a subscription for SAP SuccessFactors Incentive Management.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio734bb00a42144385b134d1df371cebe6__section_x45_vkl_dhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

