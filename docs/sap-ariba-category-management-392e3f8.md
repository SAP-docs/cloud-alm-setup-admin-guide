<!-- loio392e3f8306c349509fa5b15ad11e7b81 -->

# SAP Ariba Category Management

This document provides guidance on connecting SAP Ariba Category Management to SAP Cloud ALM for monitoring purposes.

Currently, SAP Ariba Category Management supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio392e3f8306c349509fa5b15ad11e7b81__section_ilj_jpt_sgc"/>

## Prerequisites

You have a subscription for SAP Ariba Category Management.



<a name="loio392e3f8306c349509fa5b15ad11e7b81__section_emm_kpt_sgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

