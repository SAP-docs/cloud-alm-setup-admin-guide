<!-- loio528b8fc04f6d46a4858fb4cc259e7b22 -->

# SAP Revenue Growth Optimization

This page explains how to connect SAP Revenue Growth Optimization to SAP Cloud ALM to enable monitoring.

Currently, SAP Revenue Growth Optimization supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Revenue Growth Optimization](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-rgo.html).




## Prerequisites

You have a subscription for SAP Revenue Growth Optimization.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Revenue Growth Optimization](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-rgo.html).



<a name="loio528b8fc04f6d46a4858fb4cc259e7b22__section_gpg_rxt_bhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

