<!-- loio481ff40cd8174f8f90b5b10f0309e432 -->

# SAP Batch Release Hub for Life Sciences

This document provides guidance on connecting SAP Batch Release Hub for Life Sciences to SAP Cloud ALM for monitoring purposes.

Currently, SAP Batch Release Hub for Life Sciences supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio481ff40cd8174f8f90b5b10f0309e432__section_xhm_fmg_vgc"/>

## Prerequisites

You have a subscription for SAP Batch Release Hub for Life Sciences.



<a name="loio481ff40cd8174f8f90b5b10f0309e432__section_ec1_hmg_vgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

More:

-   [Activate the Monitoring Data Collection for Integration and Exception Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/int-mon-setup-support.html?anchorId=section_1683886374_c)
-   [Activate the Monitoring Data Collection for Real User Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/real-user-monitoring/run-details.html)

> ### Restriction:  
> SAP Batch Release Hub for Life Sciences
> 
> The standalone **SAP Batch Release Hub Adapter for Integration Hub** is now deprecated. If you want to monitor **SAP Batch Release Hub for Life Sciences** with SAP Cloud ALM, ensure that you configure the **Integrated Batch Release Hub Adapter**.
> 
> For more information, refer to the [Administration Guide for SAP Batch Release Hub for Life Sciences](https://help.sap.com/docs/BATCH_RELEASE_HUB_LS_CLOUD/5a6fd89b06e54ea5b82bd8da0e38c9a7/0350a208129348dc830c694e3b54ab1f.html).

