<!-- loio8f53631da1c041d2aabc45eaf03ebee3 -->

# SAP SuccessFactors Agent Connection

This page explains how to connect SAP SuccessFactors Agent Connection to SAP Cloud ALM to enable monitoring.

Currently, SAP SuccessFactors Agent Connection supports the following monitoring applications:

-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loio8f53631da1c041d2aabc45eaf03ebee3__section_jxs_dx4_chc"/>

## Prerequisites

You have a subscription for SAP SuccessFactors Agent Connection.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio8f53631da1c041d2aabc45eaf03ebee3__section_ad2_fx4_chc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

