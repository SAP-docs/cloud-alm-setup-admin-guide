<!-- loio461d15f409044343ba65ddaed031fac4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP HANA Cloud, SAP HANA Database

This page explains how to connect SAP HANA Cloud SAP HANA database to SAP Cloud ALM to enable monitoring.

Currently, SAP HANA Cloud database supports the following monitoring applications:

-   [Configuration and Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)



## Prerequisites

For Configuration and Security Analysis

-   You have a subscription for SAP HANA Cloud.
-   The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.


For Health Monitoring:

-   You have access to the SAP BTP Cockpit.
-   Your user in SAP BTP Cockpit needs to be a member with the space role *Space Developer* for the space where you want to create the SAP HANA Cloud database instance.



<a name="loio461d15f409044343ba65ddaed031fac4__section_fhj_wg2_dhc"/>

## Setup in SAP HANA Cloud

To set up Health Monitoring for SAP HANA Cloud, you need to create a service key. This isn't required to set up Configuration and Security Analysis.

To enable OAuth authentication between SAP Cloud ALM and *SAP HANA Cloud*, create a service key for the SAP HANA Cloud instance. If there's already an existing service key, you can use this service key for the connection with SAP Cloud ALM.

1.  In the *SAP BTP Cockpit*, access the sub-account used for SAP HANA Cloud.
2.  Choose *Instances and Subscriptions*.
3.  Find the instance with the service SAP HANA Cloud and choose *hana* for the database instance that you want to connect. Select the row of the instance.
4.  Go to the *Service Keys* tab.
5.  Choose *Create*.
6.  Enter a name for the service key.
7.  Choose *Create*.



<a name="loio461d15f409044343ba65ddaed031fac4__section_ctp_hbw_zgc"/>

## Setup in SAP Cloud ALM

For **Configuration and Security Analysis**, there's no additional setup needed in SAP HANA Cloud.

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

To set up Health Monitoring, you need to create an endpoint in SAP Cloud ALM.



### For Health Monitoring: Create an HTTP Endpoint

Before starting the setup, ensure that the information for your SAP HANA Cloud database has been imported from the System Landscape Information Service \(SLIS\) into the *Landscape Management* of SAP Cloud ALM.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use-case you want to use in SAP Cloud ALM, for example *Health Monitoring*.
6.  Overwrite the value in the field *Root URL* as follows:

    Find the parameter *host* in the service key.

    Replace the part *<hostname\>.hana* with `api.gateway.orchestration`.

    Example: *Host* `1ab123a4-1234-12b3-a123-1d234e567890.hana.trial-us10.hanacloud.ondemand.com` is changed to *Root URL* `https://api.gateway.orchestration.trial-us10.hanacloud.ondemand.com`.

7.  Choose *OAuth2ClientCredentials*. Enter the following values from the SAP HANA Cloud service key. You can also copy the entire service key to the clipboard and use the *Paste Service Key* function.
    1.  *Client ID*: *clientid*
    2.  *Client Secret*: *clientsecret*
    3.  *Token Service URL*: *tokenurl* extended by `/oauth/token`

8.  Save your endpoint.



### Activate the Service in the Monitoring Apps

For Configuration and Security Analysis:

-   [Activate the data collection for Configuration & Security Analysis](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-setup.html)

For Health Monitoring:

-   After creating the endpoint in SAP Cloud ALM, go to the *Health Monitoring* app and include SAP HANA Cloud in the scope.


