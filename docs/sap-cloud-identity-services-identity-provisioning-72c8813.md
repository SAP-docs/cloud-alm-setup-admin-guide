<!-- loio72c8813ad58e40419795abf3e3f51fba -->

# SAP Cloud Identity Services – Identity Provisioning

This page explains how to connect SAP Cloud Identity Services – Identity Provisioning to SAP Cloud ALM to enable monitoring.

Currently, SAP Cloud Identity Services – Identity Provisioning supports the following monitoring applications:

-   [Configuration and Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)



<a name="loio72c8813ad58e40419795abf3e3f51fba__section_mcc_nrw_xgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

Activate the data collection:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)
-   [Activate the data collection for Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-job-monitoring)

