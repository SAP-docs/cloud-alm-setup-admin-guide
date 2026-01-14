<!-- loio1eb4d194293d433689ae49531add6dd9 -->

# SAP Digital Vehicle Hub

This page explains how to connect SAP Digital Vehicle Hub to SAP Cloud ALM to enable monitoring.

Currently, SAP Digital Vehicle Hub supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio1eb4d194293d433689ae49531add6dd9__section_rtm_4jx_ygc"/>

## Prerequisites

You have a subscription for SAP Digital Vehicle Hub.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio1eb4d194293d433689ae49531add6dd9__section_z2j_qjx_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate data collection for Integration Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/int-mon-setup-support.html?anchorId=section_1683886374_c).
-   [Activate data collection in Real User Monitoring](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/real-user-monitoring/run-details.html?anchorId=section_194947898_co).

