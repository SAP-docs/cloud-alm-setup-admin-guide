<!-- loio178b783bff564a209c54b78d8ea4b155 -->

# SAP Entitlement Management

This page explains how to connect SAP Entitlement Management to SAP Cloud ALM to enable monitoring.

Currently, SAP Entitlement Management supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Prerequisites

You have a user with *Destination Administrator* authorization in the SAP BTP subaccount that belongs to your subscription forSAP Entitlement Management.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



## For Business Process Monitoring: Setup in SAP BTP Cockpit

You only have to perform these steps if you want to set up Business Process Monitoring in SAP Cloud ALM.

To create a destination in SAP BTP Cockpit, proceed as follows:

1.  Log on to SAP BTP Cockpit and navigate to the sub-account for your SAP Entitlement Management.
2.  Go to *Connectivity* \> *Destinations*.
3.  Choose *New Destination*.
4.  Create a new destination using *Blank Template*.
    1.  *Name*: Enter a name for the destination starting with `CALM_`, for example, `CALM_BPMON`.
    2.  *Type*: *HTTP*
    3.  *Proxy Type*: *Internet*
    4.  *URL*: SAP Cloud ALM service key parameter *Endpoints* \> `Api` without `api`. Ensure to keep the slash \(/\) at the end.
    5.  *Authentication*: Select *OAuth2ClientCredentials*.
    6.  *Client ID*: SAP Cloud ALM service key parameter *clientid*.
    7.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*.
    8.  *Token Service URL Type*: *Dedicated*
    9.  *Token Service URL*: SAP Cloud ALM service key parameter `uaa` \> `url` followed by `/oauth/token`.

5.  Choose *Save* to save the destination.



## Setup in SAP Entitlement Management

These steps for the setup of both Business Process Monitoring and Integration and Exception Monitoring in SAP Cloud ALM.

1.  Log on to SAP Entitlement Management.
2.  Navigate to *System Administration* \> *Maintain System Settings*.
3.  In the navigation panel on the left, go to *SAP Cloud ALM Integration*.
4.  Choose *Edit*.
5.  Select *Enable Integration Monitoring* or *Enable Business Process Monitoring*.

    *Destination Name*: Select the destination that you created previously.

6.  Choose *Save*.



## Setup in SAP Cloud ALM



### For Integration and Exception Monitoring

SAP Entitlement Management uses the new data collection infrastructure to report monitoring data to Integration and Exception Monitoring in SAP Cloud ALM.

You only have to activate the monitoring in Integration and Exception Monitoring in SAP Cloud ALM to receive monitoring data from SAP Entitlement Management.

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)



### For Business Process Monitoring

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

