<!-- loiod412af0950ad43e183e6b03ab399e5d4 -->

# SAP Sales Cloud and SAP Service Cloud version 2

This page explains how to connect SAP Sales Cloud and SAP Service Cloud version 2 to SAP Cloud ALM to enable monitoring.

Currently, SAP Sales Cloud and SAP Service Cloud supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loiod412af0950ad43e183e6b03ab399e5d4__section_q4k_3hc_chc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

