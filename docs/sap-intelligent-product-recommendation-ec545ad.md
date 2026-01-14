<!-- loioec545add8e0e4e41a99210c50972a5f0 -->

# SAP Intelligent Product Recommendation

This page explains how to connect SAP Intelligent Product Recommendation to SAP Cloud ALM to enable monitoring.

Currently, SAP Intelligent Product Recommendation supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loioec545add8e0e4e41a99210c50972a5f0__section_v5k_4ff_bhc"/>

## Prerequisites

You have a subscription for SAP Intelligent Product Recommendation.



<a name="loioec545add8e0e4e41a99210c50972a5f0__section_kmx_pff_bhc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

