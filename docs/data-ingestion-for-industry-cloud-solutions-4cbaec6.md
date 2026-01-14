<!-- loio4cbaec6a6af6471daa23aebde969df56 -->

# Data ingestion for industry cloud solutions

This page explains how to connect Data ingestion for industry cloud solutions to SAP Cloud ALM to enable monitoring.

Currently, Data ingestion for industry cloud solutions supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio4cbaec6a6af6471daa23aebde969df56__section_jmf_5ps_ygc"/>

## Prerequisites

You have a user with the *Destination Administrator* authorization in the SAP BTP subaccount that holds the subscription for Data ingestion for industry cloud solutions.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loio4cbaec6a6af6471daa23aebde969df56__section_qxr_3qs_ygc"/>

## Activate monitoring data PUSH in Data ingestion for industry cloud solutions

Create the destination in SAP BTP Cockpit:

1.  Log on to SAP BTP Cockpit and navigate to the sub-account for your Data ingestion for industry cloud solutions.

2.  Under *Connectivity*, choose *Destinations*.

3.  Choose *New Destination*.

4.  Create a new destination using the *Blank Template*:

    1.  *Name*: Enter a name for the destination, such as SAP Cloud ALM.
    2.  *Type*: HTTP
    3.  *URL*: Use the SAP Cloud ALM service key parameter *Endpoints* and choose *Api*, without api. Ensure to keep the slash \(/\) at the end.
    4.  *Authentication*: Select *OAuth2ClientCredentials*.
    5.  *Client ID*: Use the SAP Cloud ALM service key parameter *clientid*.
    6.  *Client Secret*: Use the SAP Cloud ALM service key parameter *clientsecret*.
    7.  *Token Service URL*: Use the SAP Cloud ALM service key parameter *uaa* and choose *url* followed by `/oauth/token`.
    8.  Add a new property named *property systemRole* with either the value `PROD` or `TEST` to the destination.

5.  Choose *Save* to save the destination.


A job that runs hourly in Data ingestion for industry cloud solutions, recognizes that the destination SAP Cloud ALM exists and triggers the registration in SAP Cloud ALM. This means there can be a one-hour delay between the creation of the registration and the start of the monitoring.



<a name="loio4cbaec6a6af6471daa23aebde969df56__section_uq3_prs_ygc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

