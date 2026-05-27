<!-- loiobe4df90141ec4abfa6a53f584a8e943f -->

# SAP Cloud Application Event Hub

This page explains how to connect SAP Cloud Application Event Hub to SAP Cloud ALM to enable monitoring.

Currently, SAP Cloud Application Event Hub supports the following monitoring applications:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)Specific setup information for Integration & Exception Monitoring: [SAP Cloud Application Event Hub](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-event-broker.html).



<a name="loiobe4df90141ec4abfa6a53f584a8e943f__section_a21_jzv_xgc"/>

## Prerequisites

You have a subscription for SAP Cloud Application Event Hub.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Cloud Application Event Hub](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-event-broker.html).



<a name="loiobe4df90141ec4abfa6a53f584a8e943f__section_vr5_xzv_xgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)
-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

