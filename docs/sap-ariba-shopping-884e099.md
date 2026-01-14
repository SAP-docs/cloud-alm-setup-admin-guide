<!-- loio884e09938d3f47309fcd3202819202e6 -->

# SAP Ariba Shopping

This document provides guidance on connecting SAP Ariba Shopping to SAP Cloud ALM for monitoring purposes.

Currently, SAP Ariba Shopping supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio884e09938d3f47309fcd3202819202e6__section_ijk_gk5_sgc"/>

## Prerequisites

You have a subscription for SAP Ariba Shopping.



<a name="loio884e09938d3f47309fcd3202819202e6__section_z4q_hk5_sgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

