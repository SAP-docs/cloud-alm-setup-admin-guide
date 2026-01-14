<!-- loio612dedf184324af0a8d4801db8097ae2 -->

# SAP Digital Currency Hub

This page explains how to connect SAP Digital Currency Hub to SAP Cloud ALM to enable monitoring.

Currently, SAP Digital Currency Hub supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio612dedf184324af0a8d4801db8097ae2__section_gs2_q3x_ygc"/>

## Prerequisites

You have a subscription for SAP Digital Currency Hub.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio612dedf184324af0a8d4801db8097ae2__section_gcj_y3x_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

[Activate data collection in Real User Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/real-user-monitoring/run-details.html?anchorId=section_194947898_co).

