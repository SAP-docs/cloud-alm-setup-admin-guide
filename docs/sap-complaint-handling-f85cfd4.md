<!-- loiof85cfd4aed954c2ba8c5d738e4769c16 -->

# SAP Complaint Handling

This document provides guidance on connecting SAP Complaint Handling, to SAP Cloud ALM for monitoring purposes.

The following monitoring application is supported for SAP Concur:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Complaint Handling](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-comph.html).

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



## Prerequisites

You have a subscription for SAP Complaint Handling.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Complaint Handling](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-comph.html).



## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/bpmon-connecting-services#activating-the-data-collection)
-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-activating-data-collection)

