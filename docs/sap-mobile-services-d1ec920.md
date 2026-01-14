<!-- loiod1ec9207c7604a9eb4a780797781ce1b -->

# SAP Mobile Services

This page explains how to connect SAP Mobile Services to SAP Cloud ALM to enable monitoring.

Currently, SAP Mobile Services supports the following monitoring applications:

-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loiod1ec9207c7604a9eb4a780797781ce1b__section_vdz_z5r_bhc"/>

## Prerequisites

You have a subscription for SAP Mobile Services.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loiod1ec9207c7604a9eb4a780797781ce1b__section_ejx_gvr_bhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

> ### Note:  
> In the past, there was an additional registration procedure with service type SAP BTP, Cloud Foundry environment or SAP BTP, Neo environment.
> 
> If you're still using this service type, you need to change to the service type SAP Mobile Services by deleting the current configuration and setting up the system again.

