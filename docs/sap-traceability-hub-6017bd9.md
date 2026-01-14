<!-- loio6017bd9b0c7b4f2f995a889f70ab71e6 -->

# SAP Traceability Hub

This page explains how to connect SAP Traceability Hub to SAP Cloud ALM to enable monitoring.

Currently, SAP Traceability Hub supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Prerequisites

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

In SAP Traceability Hub, you have access to the *Integration Monitoring with SAP Cloud ALM* app. If you don't have access to the app, contact your organization's administrator.



## Setup in SAP Traceability Hub



### Register in SAP Cloud ALM

1.  In *SAP BTP Cockpit*, choose your subscription for SAP Traceability Hub and choose *Go to Application*.
2.  Choose the *Integration Monitoring* tile.
3.  Under *Integration with SAP Cloud ALM*, enter the following:
    -   *Client ID*: SAP Cloud ALM service key parameter `<uaa>:<clientid>`
    -   *Client Secret*: SAP Cloud ALM service key parameter `uaa:clientsecret`
    -   *Endpoint*: SAP Cloud ALM service key parameter "Api" without `/api`, for example, `https://eu10.alm.cloud.sap`
    -   *OAuth URL*: SAP Cloud ALM service key parameter `<uaa>:<URL>` extended by `/oauth/token`

4.  Choose *Subscribe* in the lower right corner.



### Deregister in SAP Cloud ALM

If you want to turn off the monitoring in the SAP Traceability Hub tenant, proceed as follows:

1.  In *SAP BTP Cockpit*, choose your subscription for SAP Traceability Hub and choose *Go to Application*.
2.  Choose the *Integration Monitoring* tile.
3.  Choose *Edit* for the existing registration.
4.  Choose *Subscribed* in the lower right corner.
5.  Choose *Unsubscribe*.



## Setup in SAP Cloud ALM

After setting up the monitoring push to SAP Cloud ALM in the managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring application in SAP Cloud ALM. Find more information in the configuration pages for the relevant monitoring apps, under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

