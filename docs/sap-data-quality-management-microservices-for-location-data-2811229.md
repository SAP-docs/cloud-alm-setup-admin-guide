<!-- loio2811229d5b54470aa5ca48fc61872031 -->

# SAP Data Quality Management, microservices for location data

This page explains how to connect SAP Data Quality Management, microservices for location data to SAP Cloud ALM to enable monitoring.

Currently, SAP Data Quality Management, microservices for location data supports the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio2811229d5b54470aa5ca48fc61872031__section_zp3_w2x_ygc"/>

## Prerequisites

You have a user with administrator authorizations in SAP Data Quality Management, microservices for location data.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loio2811229d5b54470aa5ca48fc61872031__section_pls_zfx_ygc"/>

## Activate Monitoring Data PUSH in SAP Data Quality Management, microservices for location data

1.  Log on to your tenant of SAP Data Quality Management, microservices for location data.
2.  Open *Cloud ALM Integration*.
3.  Enter the following values or use the *Copy JSON* function in the upper right corner:
    1.  *Instance URL*: SAP Cloud ALM service key parameter `Endpoints` \> `Api`
    2.  *Token URL*: SAP Cloud ALM service key parameter `uaa` \> `url` followed by `/oauth/token`
    3.  *Client ID*: SAP Cloud ALM service key parameter `clientid`
    4.  *Client Secret*: SAP Cloud ALM service key parameter `clientsecret`

4.  Choose *Save* to perform the registration



<a name="loio2811229d5b54470aa5ca48fc61872031__section_b5t_pgx_ygc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

