<!-- loiof785e26e5361494985f3e6d0233f388e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Integration Suite \(API Management\)

This page explains how to connect SAP Integration Suite \(API Management\) to SAP Cloud ALM to enable monitoring.

Currently, SAP Integration Suite \(API Management\) supports the following monitoring applications:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)

With Health Monitoring in SAP Cloud ALM, you can monitor the health of custom domains for virtual host certificates in API management.



## Prerequisites

You only receive monitoring data if you've requested a custom domain for the virtual host as described here.

You have access to the SAP BTP cockpit and an entitlement for the service *API Management, API portal* for the plan *apiportal-apiaccess*. You can check this in the SAP BTP cockpit under *Subaccount for Integration Suite* \> *Entitlements*.

Your user in the SAP BTP cockpit is a member with the space role *Space Developer*, for the space where you want to create the service instance.



## Setup in SAP Integration Suite \(API Management\)

To enable OAuth authentication between SAP Cloud ALM and SAP Integration Suite \(API Management\), create an instance with a service key for the API Management service with the necessary authorizations.



### Create Service Instance

1.  Go to the SAP BTP cockpit and access the sub-account used for SAP Cloud Integration.
2.  Go to *Instances and Subscriptions*.
3.  Choose *Create* to create a new instance.
4.  Basic Info:
    1.  *Service*: *API Management, API portal \(apimanagement-apiportal\)*
    2.  *Plan*: *apiportal-apiaccess*
    3.  *Runtime Environment*: *Cloud Foundry*
    4.  *Space*: Select the appropriate space, depending on your company.
    5.  *Instance Name*: Enter an instance name.
    6.  Choose *Next*

5.  Under *Parameters*, enter the following JSON string: `{ "role": "APIPortal.Administrator" }`.
6.  Choose *Create* to create the instance.



### Create Service Key

1.  Select the row of the instance.
2.  Go to the *Service Keys* tab.
3.  Choose *Create*.
4.  Enter a name for the service key.
5.  Choose *Create*.

Download the service key file. You need it when you create the endpoint in SAP Cloud ALM.



## Setup in SAP Cloud ALM



### Create HTTP Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Select your service SAP Integration Suite \(API Management\).

    Do not choose the service with the service type *SAP BTP Cloud Foundry environment* even if the cloud service name contains *API Management*.

3.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
4.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
5.  Enter a description.
6.  Choose the use-cases you want to use in SAP Cloud ALM, for example *Health Monitoring*.
7.  Overwrite the value in the *Root URL* field with the value of the *url* parameter in the service key.
8.  Choose *OAuth2ClientCredentials*: Enter the following values from the SAP Integration Suite service key:
    1.  *Client ID*: *clientid*
    2.  *Client Secret*: *clientsecret*
    3.  *Token Service URL*: *tokenurl*

9.  Save your endpoint.



### Activate the Service in the Monitoring App

After creating the endpoint in SAP Cloud ALM, activate the data collection:

-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)

