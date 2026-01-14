<!-- loio8637dcf3166f4621baaf36eec0deb556 -->

# SAP Business Network Supply Chain Collaboration, clinical trials add-on

This document provides guidance on connecting SAP Business Network Supply Chain Collaboration, clinical trials add-on to SAP Cloud ALM for monitoring purposes.

Currently, SAP Business Network Supply Chain Collaboration, clinical trials add-on supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio8637dcf3166f4621baaf36eec0deb556__section_hng_xsw_xgc"/>

## Prerequisites

You have a subscription for SAP Business Network Supply Chain Collaboration, clinical trials add-on.



<a name="loio8637dcf3166f4621baaf36eec0deb556__section_l2f_ftw_xgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

