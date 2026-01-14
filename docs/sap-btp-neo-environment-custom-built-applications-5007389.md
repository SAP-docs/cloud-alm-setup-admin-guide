<!-- loio500738907448487796d810919f8149af -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP BTP, Neo environment \(custom-built applications\)

This document provides guidance on connecting custom-built applications in the SAP BTP, Neo environment to SAP Cloud ALM for monitoring purposes.

Currently, **custom-built applications** for SAP BTP, Neo environment supports the following monitoring applications:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio500738907448487796d810919f8149af__section_fvf_4kt_wgc"/>

## Prerequisites

The application you want to monitor is a custom Java application deployed on the SAP BTP, Neo environment. You can find this application in your SAP BTP Neo subaccount under *Applications* \> *Java Applications*.

You have a user with administrator authorizations in the subaccount of SAP BTP, Neo environment, where the custom Java application is deployed.



## Setup in SAP BTP, Neo environment



### Determine the Root URL

The API root URL for SAP BTP depends on the data center where your account is hosted.

1.  Find the region of your subaccount:
    -   In SAP BTP Cockpit, you find it either on the subaccount card on your global account page in the field *Region*.
    -   In the *Landscape Management* app in SAP Cloud ALM, in the service property *BTP Landscape ID*.

2.  Find your region here: *SAP Business Technology Platform \(SAP BTP\)* \> *SAP Business Technology Platform, Neo Environment* \> *Regions in the Neo Environment* \> *Regions and Hosts Available for the Neo Environment*.

    More under [Regions and Hosts Available for the Neo Environment](https://help.sap.com/docs/btp/sap-btp-neo-environment/regions-and-hosts-available-for-neo-environment?version=Cloud).

3.  Note down the host for your region.
4.  Build your root URLs. For example, if your host is `us1.hana.ondemand.com`:
    -   The root URL for Exception Monitoring and Real User Monitoring is `https://publicapingplog.us1.hana.ondemand.com`.
    -   The root URL for Health Monitoring is `https://api.us1.hana.ondemand.com`.




### Create API Client for Java Application Monitoring

To connect to SAP BTP to collect Java application monitoring data, you need to create the correct API client in the subaccount.

1.  Log on to SAP BTP Cockpit and navigate to the subaccount with the Java application that you want to collect logs for.
2.  Navigate to *Security* \> *OAuth*.
3.  Go to the *Platform API* tab.
4.  Choose *Create API Client*.
5.  Add the following authorizations to the client:
    -   Under *Exception and Tracing API*: add *Read Exception Logs* and *Read End-to-End Traces*.
    -   Under *Monitoring Service*: add *Read Monitoring Data*.
    -   Under *Lifecycle Management*: add Read Applications.

6.  Choose *Save*.
7.  Note down the client ID and the client secret for later use.



### Switch on Performance Data Collection for SAP Cloud Portal Service

If you want to collect monitoring data for Real User Monitoring, activate the performance data collection for SAP Fiori Launchpad.

1.  In SAP BTP Cockpit, navigate to the subaccount with the Java application for that you want to collect performance data.
2.  Go to *Services*.
3.  Search for the *Cloud Portal Service*.
4.  Choose the tile.
5.  Under *Take Action*, choose *Go to Service*.
6.  In the new application, go to *Site Directory*.
7.  Choose *Edit* in the SAP Fiori Launchpad Portal \(FLP\) page for that you want to activate Real User Monitoring, for example `defaultsite`.
8.  In the *SAP Fiori Configuration Cockpit*, select *Settings* from the side navigation menu.
9.  Choose *Edit* at the bottom-right side of the screen.
10. Under *System Settings*, under *Collect Performance Data*, switch it to *YES*.
11. Save your changes.



### Write Java Errors into Default Trace

This preparation step starts during the development of the SAP BTP application. To collect application errors, these errors must exist in the default trace for the SAP BTP Java application. Developers must write meaningful errors in this trace. The quality of the monitored exceptions depends on the quality of the exceptions written by the developer.

See this [blog](https://community.sap.com/t5/technology-blog-posts-by-members/java-logging-for-hana-cloud-platform/ba-p/13185271) for more information on logging for SAP BTP Java applications.



<a name="loio500738907448487796d810919f8149af__section_xtg_bpt_wgc"/>

## Setup in SAP Cloud ALM



### Create Endpoint for Exception Monitoring

1.  In SAP Cloud ALM, open the *Landscape Management* app.
2.  Select your SAP BTP, Neo environment service.
3.  Choose :heavy_plus_sign: at the end of the line.
4.  On the *Endpoints* tab, choose *Add*.
5.  Enter a description.
6.  *Use Case*: Choose *Exception Monitoring*.
7.  *Root URL*: `https://publicapingplog.<host of your region>`.
8.  *Authentication Type*: `OAuth2ClientCredentials`. All fields are mandatory:

    -   *Client ID*: Client ID of the API client.
    -   *Client Secret*: Client secret of the API client.
    -   *Token Service URL*: `https://api.<host for your region>/oauth2/apitoken/v1`.
    -   *Token Service User* \*: Client ID of the API client.
    -   *Token Service Password* \*: Client secret of the API client.

    \* Note that the API client ID and password must be added also to the Token Service user and password for the Exception Monitoring endpoint.

9.  Save the endpoint.



### Create Endpoint for Real User Monitoring

1.  Open the *Landscape Management* app.
2.  Select your SAP BTP, Neo environment service.
3.  Choose :heavy_plus_sign: at the end of the line.
4.  On the *Endpoints* tab, choose *Add*.
5.  Enter a description.
6.  *Use Case*: Choose *Real User Monitoring*.
7.  *Root URL*: `https://publicapingplog.<host of your region>`.
8.  *Authentication Type*: `OAuth2ClientCredentials`.
    -   *Client ID*: Client ID of the API client.
    -   *Client Secret*: Client secret of the API client.
    -   *Token Service URL*: `https://api.<host for your region>/oauth2/apitoken/v1`.

9.  Save the endpoint.



### Create Endpoint for Health Monitoring

1.  Open the *Landscape Management* app.
2.  Select your SAP BTP, Neo environment service.
3.  Choose :heavy_plus_sign: at the end of the line.
4.  On the *Endpoints* tab, choose *Add*.
5.  Enter a description.
6.  *Use Case*: Choose *Health Monitoring*.
7.  *Root URL*: `https://api.<host of your region>`.
8.  *Authentication Type*: `OAuth2ClientCredentials`.
    -   *Client ID*: Client ID of the API client.
    -   *Client Secret*: Client secret of the API client.
    -   *Token Service URL*: `https://api.<host for your region>/oauth2/apitoken/v1`.

9.  Save the endpoint.



### Activate the Monitoring Data Collection

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use-cases:

-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)
-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   [Activate data collection for Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-health-monitoring)

