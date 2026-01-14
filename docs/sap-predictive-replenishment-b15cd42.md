<!-- loiob15cd42f590b440aa7bdf0a3f69d43fe -->

# SAP Predictive Replenishment

This page explains how to connect SAP Predictive Replenishment to SAP Cloud ALM to enable monitoring.

Currently, SAP Predictive Replenishment supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loiob15cd42f590b440aa7bdf0a3f69d43fe__section_rp3_gnt_bhc"/>

## Prerequisites

You have a subscription for SAP Predictive Replenishment.



<a name="loiob15cd42f590b440aa7bdf0a3f69d43fe__section_mxm_hnt_bhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

