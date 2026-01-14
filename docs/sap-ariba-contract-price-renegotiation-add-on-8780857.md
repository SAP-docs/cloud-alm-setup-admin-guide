<!-- loio8780857e1a1847d884d5412e0bccd5ab -->

# SAP Ariba contract price renegotiation add-on

This document provides guidance on connecting SAP Ariba contract price renegotiation add-on add-on to SAP Cloud ALM, for monitoring purposes.

Currently, SAP Ariba contract price renegotiation add-on supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio8780857e1a1847d884d5412e0bccd5ab__section_j5b_x25_sgc"/>

## Prerequisites

You have a subscription for the SAP Ariba contract price renegotiation add-on.

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loio8780857e1a1847d884d5412e0bccd5ab__section_sjw_cf5_sgc"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

