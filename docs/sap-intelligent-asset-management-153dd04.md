<!-- loio153dd04e2985432daf4b1189ba9b987b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Intelligent Asset Management

This page explains how to connect SAP Intelligent Asset Management to SAP Cloud ALM to enable monitoring.

Currently, SAP Intelligent Asset Management database supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/86f2d8ccf28e44b39fa66b6fc7898bc0.html "The Integration & Exception Monitoring app provides insight into the data exchange processes between managed components.") :arrow_upper_right:
-   [Real User Monitoring](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/ebcd19104a714cc48ecccb15b177ebe1.html "The Real User Monitoring app permanently measures all real user requests from your managed SAP solutions. The monitored services and systems send monitoring data to SAP Cloud ALM covering performance, as well as utilization aspects. The Real User Monitoring app also offers drilldown possibilities from the global use of selected request types to single executions and execution details.") :arrow_upper_right:

Monitoring is supported for the following solutions in SAP Intelligent Asset Management:

-   SAP Business Network for Asset Management
-   SAP Asset Strategy and Performance Management
-   SAP Predictive Asset Insights

> ### Note:  
> If you've subscribed to more than one of the solutions above within the **same** sub-account, we recommend activating the monitoring only for one of the solutions to avoid duplicate data collection.

Integration Monitoring is **not** supported for SAP Intelligent Asset Management accounts running in Neo, AliCloud, or Azure.



<a name="loio153dd04e2985432daf4b1189ba9b987b__section_nwv_kk2_bhc"/>

## Prerequisites

You have access to the sub-account for SAP Intelligent Asset Management.

Your user in the SAP BTP cockpit is a member with the space role *Space Developer*.



<a name="loio153dd04e2985432daf4b1189ba9b987b__section_g1t_xk2_bhc"/>

## Setup for SAP Intelligent Asset Management



### Download the Service Key

You need the credentials for your service to register it in SAP Cloud ALM.

1.  In the *SAP BTP cockpit*, access the sub-account for SAP Intelligent Asset Management our service
2.  Choose *Instances and Subscriptions*.
3.  Under *Instances*, select your service instance.
4.  Find the *Service Keys*.
5.  Download the service key file.



<a name="loio153dd04e2985432daf4b1189ba9b987b__section_o2w_tm2_bhc"/>

## Setup in SAP Cloud ALM



### Create an HTTP Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use-case you want to use in SAP Cloud ALM.
6.  *Root URL*: Enter the following values, depending on your data center of SAP Cloud ALM.
    -   EU10: https://ain-live.cfapps.eu10.hana.ondemand.com
    -   US10: https://ain-live.cfapps.us10.hana.ondemand.com
    -   AP10: https://ain-live.cfapps.ap10.hana.ondemand.com
    -   EU20, US20: The monitoring API isn't yet supported for the Azure landscape.
    -   CN40: The monitoring API isn't yet supported for the AliCloud landscape.

7.  Choose *OAuth2ClientCredentials*as authentication type. Enter the following values from the SAP Intelligent Asset Management service key:
    1.  *Client ID*: the service key parameter *uaa.clientid*
    2.  *Client Secret*: the service key parameter *uaa.clientsecret*
    3.  *Token Service URL*: the service key parameter `uaa.url` extended by `/oauth/token`

8.  Save your endpoint.



### Activate the Data Collection in the Monitoring App

After creating the endpoint in SAP Cloud ALM, activate the data collection:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

