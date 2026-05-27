<!-- loio167323519921439991e8d7026c8dde62 -->

# SAP Order Management foundation

This page explains how to connect SAP Order Management foundation to SAP Cloud ALM to enable monitoring.

Currently, SAP Order Management foundation supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

    Specific setup information for Integration & Exception Monitoring: [SAP Order Management foundation](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-cen-ord.html).




<a name="loio167323519921439991e8d7026c8dde62__section_v4j_q3t_bhc"/>

## Prerequisites

You have a user with the **Destination Administrator** authorizations in the SAP BTP sub-account for your SAP Order Management foundation subscription.

You have *Space Developer* access to a space in the sub-account of SAP Order Management foundation.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

Specific prerequisites for the setup of Integration & Exception Monitoring under [SAP Order Management foundation](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-cen-ord.html).



<a name="loio167323519921439991e8d7026c8dde62__section_l2h_v3t_bhc"/>

## Setup for SAP Order Management foundation

Follow the [Setup](https://help.sap.com/docs/SAP_Order_Management_Foundation/95fb0d8e21b9460b8e4690ebbc667d92/9abf72b25d7f449e8cccb2095a507aa4.html?version=LATEST&locale=en-US) documentation from SAP Order Management foundation for SAP Cloud ALM.



<a name="loio167323519921439991e8d7026c8dde62__section_aj3_3mt_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



### Unregistering from SAP Cloud ALM

You can stop the monitoring data transfer and unregister your [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations) tenant from SAP Cloud ALM:

1.  Get a JWT as described in the previous section.
2.  Perform an API call as described under [Offboarding](https://help.sap.com/docs/SAP_Order_Management_Foundation/95fb0d8e21b9460b8e4690ebbc667d92/efe53dae889e42adbd3bd0722336b995.html?version=Cloud).

