<!-- loio60f0977dd6b049d79e49aebc1cd0cd38 -->

# SAP Automation Pilot

This document provides guidance on connecting SAP Automation Pilot to SAP Cloud ALM for monitoring purposes.

Currently, SAP Automation Pilot supports the following monitoring applications:

-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)



<a name="loio60f0977dd6b049d79e49aebc1cd0cd38__section_tdl_glg_vgc"/>

## Prerequisites

You have a subscription for SAP Automation Pilot.



<a name="loio60f0977dd6b049d79e49aebc1cd0cd38__section_tjd_klg_vgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

-   **[Configure SAP Automation Pilot for Operation Automation](configure-sap-automation-pilot-for-operation-automation-1441c68.md "")**  


