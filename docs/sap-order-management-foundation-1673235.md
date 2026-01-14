<!-- loio167323519921439991e8d7026c8dde62 -->

# SAP Order Management foundation

This page explains how to connect SAP Order Management foundation to SAP Cloud ALM to enable monitoring.

Currently, SAP Order Management foundation supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio167323519921439991e8d7026c8dde62__section_v4j_q3t_bhc"/>

## Prerequisites

You have a user with the **Destination Administrator** authorizations in the SAP BTP sub-account for your SAP Order Management foundation subscription.

You have *Space Developer* access to a space in the sub-account of SAP Order Management foundation.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loio167323519921439991e8d7026c8dde62__section_l2h_v3t_bhc"/>

## Setup for SAP Order Management foundation



### **Create Destination in the SAP BTP Cockpit**

1.  Log on to the SAP BTP cockpit and navigate to the sub-account for your SAP Order Management foundation.
2.  Go to *Connectivity* \> *Destinations*.
3.  Choose *New Destination*.
4.  Create a new destination using *Blank Template*.
    1.  *Name*: `CloudALM`.
    2.  *Type*: *HTTP*
    3.  *URL*: SAP Cloud ALM service key parameter `Api`
    4.  *Authentication*: *OAuth2ClientCredentials*.
    5.  *Client ID*: SAP Cloud ALM service key parameter *clientid*.
    6.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*.
    7.  *Token Service URL*: SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.

5.  Choose *Save* to save the destination.



### Download the Service Key

You need the credentials for your service to register it in SAP Cloud ALM.

1.  In the *SAP BTP cockpit*, access the sub-account for SAP Intelligent Asset Management our service
2.  Choose *Instances and Subscriptions*.
3.  Under *Instances*, select your service instance.
4.  Find the *Service Keys*.
5.  Download the service key file.



### Get JSON Web Token \(JWT\) with Client ID and Client Secret

To call the SAP Cloud ALM registration API, you first need to acquire a JWT from your SAP SAP Order Management foundation tenant.

Follow the process to acquire the JWT described [**Development**](https://help.sap.com/viewer/d91676a7fa624c31b7b1c526d7787e2f/LATEST/en-US/8d62e6742e9f4afbb492ff976d05fdc9.html).

1.  The service key used for this step is the SAP Order Management foundation service key.
2.  Enter the *Scope* for the call as `{XSA app name}.IntegrationMonitoring`.
3.  You get the JWT in the response to your call.

4.  Copy the content of the *access\_token* field without the quotation marks.



### Register SAP Order Management foundation

Now, use the JWT that you acquired in the previous section to call the registration URL in SAP Order Management foundation.

This is in detail described in step 4 of the documentation provided in [Integration Monitoring in SAP Cloud ALM](https://help.sap.com/viewer/95fb0d8e21b9460b8e4690ebbc667d92/LATEST/en-US/c6ed967bbc004e55abcc0e1ee7867c62.html).

In the response to your API call, you get a message that the registration for Integration Monitoring was successful.

The SAP Order Management foundation cloud service now appears in the *Landscape Management* app of SAP Cloud ALM, with the ID `CO_<environment>_<tenant ID>`.

The registration activates the PUSH data collection and automatically sends monitoring data to SAP Cloud ALM.



<a name="loio167323519921439991e8d7026c8dde62__section_aj3_3mt_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



### Unregistering from SAP Cloud ALM

You can stop the monitoring data transfer and unregister your [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations) tenant from SAP Cloud ALM:

1.  Get a JWT as described in the previous section.
2.  Perform an API call as described under [Offboarding](https://help.sap.com/docs/SAP_Order_Management_Foundation/95fb0d8e21b9460b8e4690ebbc667d92/efe53dae889e42adbd3bd0722336b995.html?version=Cloud).

