<!-- loio63621904edcf4362967cf0dfc4383956 -->

# SAP Data Intelligence

This page explains how to connect SAP Data Intelligence to SAP Cloud ALM to enable monitoring.

Currently, SAP Data Intelligence supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio63621904edcf4362967cf0dfc4383956__section_vxv_ldx_ygc"/>

## Prerequisites

You can obtain the [SAP Cloud ALM Service Key](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-connect.html) to connect to the SAP Cloud ALM tenant.



<a name="loio63621904edcf4362967cf0dfc4383956__section_od3_4dx_ygc"/>

## Setup Monitoring Push in SAP Data Intelligence

Follow the instructions under [Integration Monitoring in SAP Cloud Application Lifecycle Management](https://help.sap.com/docs/data-intelligence-cloud/sap-data-intelligence-administration/integration-monitoring-in-sap-cloud-application-lifecycle-management?version=Cloud).

The setup basically contains of the following steps:

1.  Creating the technical user `sap-cloud-alm-technical-user` and assigning the relevant policies to the user.
2.  Creating and uploading a configuration to create a connection to SAP Cloud ALM.



<a name="loio63621904edcf4362967cf0dfc4383956__section_c1b_f2x_ygc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

