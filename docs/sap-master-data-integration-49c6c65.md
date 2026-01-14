<!-- loio49c6c65ab94c43a8bd299c97b96bb453 -->

# SAP Master Data Integration

This page explains how to connect SAP Master Data Integration to SAP Cloud ALM to enable monitoring.

Currently, SAP Master Data Integration supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio49c6c65ab94c43a8bd299c97b96bb453__section_mz4_mrr_bhc"/>

## Prerequisites

You have a subscription for SAP Master Data Integration **Tenant**.

You can only activate the integration monitoring for the subscription of type *Tenant* \(`one-mds-master`\), which you need in addition to your subscription for SAP Master Data Integration \(`one-mds`\). More under [Creating Tenants](https://help.sap.com/docs/master-data-integration/sap-master-data-integration-prod/creating-tenants).



<a name="loio49c6c65ab94c43a8bd299c97b96bb453__section_rk1_yrr_bhc"/>

## Setup in SAP Cloud ALM



### Activate the Data Collection for Monitoring

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

> ### Note:  
> **Migration of an existing SAP Master Data Integration configuration**
> 
> The setup of SAP Master Data Management has changed in November 2024. If you want to to change the new configuration, proceed as follows:
> 
> 1.  Subscribe to the new SAP Master Data Integration **Tenant**
> 2.  Identify the service in the *Landscape Management* app of SAP Cloud ALM.
> 3.  Activate the configuration in Integration and Exception Monitoring



### Setup of Distribution Status Monitoring in SAP Master Data Orchestration

You can monitor the distribution status of your messages with the *Display Distribution Status* app in *SAP Master Data Orchestration* itself.

This setup step is **not** necessary to monitor SAP Master Data Integration in SAP Cloud ALM, but only if you want to use the *Display Distribution Status* app in *SAP Master Data Orchestration*.

To enable the *Display Distribution Status* app to map the log information to the correct component, you have to maintain the destination mapping as described in

[Configure Destination Mapping](https://help.sap.com/docs/SAP_MASTER_DATA_INTEGRATION/8ce78b673ef04cc1bcfeb01c93ef7885/a0a62b1be79549e681c5997f371b3095.html?locale=en-US)

