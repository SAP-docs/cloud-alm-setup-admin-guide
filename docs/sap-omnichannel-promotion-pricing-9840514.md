<!-- loio9840514de2194708902e9dbe07b36a84 -->

# SAP Omnichannel Promotion Pricing

This page explains how to connect SAP Omnichannel Promotion Pricing to SAP Cloud ALM to enable monitoring.

Currently, SAP Omnichannel Promotion Pricing supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio9840514de2194708902e9dbe07b36a84__section_llm_dqs_bhc"/>

## Prerequisites

You have a user with the **Destination Administrator** authorizations in the SAP BTP sub-account for your subscription of SAP Omnichannel Promotion Pricing.

You have *Space Developer* access to a space in the sub-account for SAP Omnichannel Promotion Pricing.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loio9840514de2194708902e9dbe07b36a84__section_zrp_4qs_bhc"/>

## Setup in the SAP BTP Cockpit



### **Create Destination in SAP BTP Cockpit**

1.  Log on to the SAP BTP cockpit and navigate to the sub-account for your SAP Omnichannel Promotion Pricing.
2.  Go to *Connectivity* \> *Destinations*.
3.  Choose *New Destination*.
4.  Create a new destination using *Blank Template*.
    1.  *Name*: `CALM_OPPS`
    2.  *Type*: *HTTP*
    3.  *URL*: SAP Cloud ALM service key parameter `Api` without `/api`.
    4.  *Authentication*: Select *OAuth2ClientCredentials*.
    5.  *Client ID*: SAP Cloud ALM service key parameter *clientid*.
    6.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*.
    7.  *Token Service URL*: SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.

5.  Choose *Save* to save the destination.



### Download the Service Key

To successfully call the registration URL in SAP Omnichannel Promotion Pricing, to register with SAP Cloud ALM, download the service key for the instance for SAP Omnichannel Promotion Pricing:

1.  Log on to the SAP BTP cockpit and navigate to the sub-account for your SAP Omnichannel Promotion Pricing.
2.  In the navigation panel, choose *Services* \> *Instances and Subscriptions*.

3.  Under *Instances*, select the instance of the *Administration service*
4.  In the section that opens, choose *Service Keys*.

    You see your service key in JSON format. The key includes the application URL, service URL, client ID, and client secret.

5.  Download this service key and save it for later



<a name="loio9840514de2194708902e9dbe07b36a84__section_qzf_qrs_bhc"/>

## Setup in SAP Omnichannel Promotion Pricing



### Get JSON Web Token \(JWT\) with Client ID and Client Secret

To call the SAP Cloud ALM registration API, you first need to acquire a JWT from your SAP Omnichannel Promotion Pricing tenant.

1.  The service key used for this step is the *Administration service* key
2.  Follow the process to acquire the JWT in [Accessing SAP Omnichannel Promotion Pricing APIs](https://help.sap.com/docs/omnichannel-promotion-pricing/administration-guide/accessing-sap-omnichannel-promotion-pricing-apis?version=Cloud).

    You'll get the JWT in the response to your call.

3.  Copy the content of the *access\_token* field without the quotation marks.



### Register SAP Omnichannel Promotion Pricing

Now, you use the JWT that you acquired in the previous step to call the registration URL in SAP Omnichannel Promotion Pricing.

This is in detail described in step 5 of the documentation provided in [Integration Monitoring in SAP Cloud ALM](https://help.sap.com/docs/omnichannel-promotion-pricing/service-guide/integration-monitoring-in-sap-cloud-alm?version=Cloud).

After sending the POST request, you get an HTTP return code 200 and a message saying that you have successfully triggered the service registration.

After registering SAP Omnichannel Promotion Pricing, cloud service appears in the *Landscape Management* of SAP Cloud ALM with the ID *OPPS\_Data\_Upload* or *OPPS\_Data\_Upload\_<optional suffix you defined during registration\>*.

The registration activates the PUSH data collection and automatically sends monitoring data to SAP Cloud ALM.



<a name="loio9840514de2194708902e9dbe07b36a84__section_lk2_vrs_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

**Unregistering from SAP Cloud ALM**

You can stop the monitoring data transfer and to unregister your SAP Omnichannel Promotion Pricing tenant from SAP Cloud ALM:

1.  Get a JWT as described above
2.  Perform an API call as described in the [Offboarding](https://help.sap.com/docs/omnichannel-promotion-pricing/service-guide/integration-monitoring-in-sap-cloud-alm?version=Cloud#offboarding) section in [Integration Monitoring in SAP Cloud ALM](https://help.sap.com/docs/omnichannel-promotion-pricing/service-guide/integration-monitoring-in-sap-cloud-alm?version=Cloud).

