<!-- loio11ca81a1d9d8425ea711e3de6e4aca1a -->

# SAP Digital Manufacturing

This page explains how to connect SAP Digital Manufacturing to SAP Cloud ALM to enable monitoring.

Currently, SAP Digital Manufacturing supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)



<a name="loio11ca81a1d9d8425ea711e3de6e4aca1a__section_yny_fjx_ygc"/>

## Prerequisites

You have a subscription for SAP Digital Manufacturing.



<a name="loio11ca81a1d9d8425ea711e3de6e4aca1a__section_otj_hjx_ygc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Job and Automation Monitoring \(SAP Help - How to Enable Job Monitoring with SAP Cloud ALM\)](https://help.sap.com/docs/job-scheduling/sap-job-scheduling-service/integration-with-sap-cloud-alm?locale=en-US)

