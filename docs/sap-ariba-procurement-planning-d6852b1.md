<!-- loiod6852b1ed5b74f329e5ab27a42bb518b -->

# SAP Ariba Procurement Planning

This document provides guidance on connecting SAP Ariba Procurement Planning to SAP Cloud ALM, for monitoring purposes.

Currently, SAP Ariba Procurement Planning supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loiod6852b1ed5b74f329e5ab27a42bb518b__section_rcc_g4c_tgc"/>

## Prerequisites

You have a subscription for the SAP Ariba Procurement Planning.



<a name="loiod6852b1ed5b74f329e5ab27a42bb518b__section_off_34c_tgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

