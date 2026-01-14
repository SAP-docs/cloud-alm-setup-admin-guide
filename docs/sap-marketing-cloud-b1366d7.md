<!-- loiob1366d7ef92c4ead9fbd7d4534859112 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Marketing Cloud

This page explains how to connect SAP Marketing Cloud to SAP Cloud ALM to enable monitoring.

Currently, SAP Marketing Cloud supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)

The following video demonstrates the setup for application monitoring for SAP Integration Suite \(Cloud Integration\) on Neo. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loiob1366d7ef92c4ead9fbd7d4534859112__section_ety_v3m_bhc"/>

## Prerequisites

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

In SAP Marketing Cloud, you have a user with administrator authorization.



<a name="loiob1366d7ef92c4ead9fbd7d4534859112__section_c4g_r4r_bhc"/>

## Setup in SAP Marketing Cloud



### Create Communication System

1.  Log on to SAP Marketing Cloud.
2.  Navigate to the *Communication Management* group and choose the *Communication Systems* tile.
3.  Check if there's already a communication system for this SAP Cloud ALM tenant.
    1.  In the *Search* field, search for the endpoint host, for example, `eu10.alm.cloud.sap`.
    2.  To verify that the correct SAP Cloud ALM tenant is addressed, compare the value in the *Token Endpoint* field.
    3.  If a communication system already exists, you can move on to the section *Create Communication Arrangement*.

4.  Choose *New* to create a new communication system.
5.  Enter a system ID and description, then choose *Create*.
6.  Enter the following values:
    1.  *Host Name*: The host part of the SAP Cloud ALM service key parameter *Api*, for example, `eu10.alm.cloud.sap`.
    2.  *Port*: `443`
    3.  Under *OAuth 2.0 Settings*, enter the *Token Endpoint*: SAP Cloud ALM service key parameter *url* followed by `/oauth/token`.
    4.  Under *Users for Outbound Communication*, choose :heavy_plus_sign: to create a new user.
        1.  *Authentication Method*: *OAuth 2.0*
        2.  *OAuth 2.0 Client ID*: SAP Cloud ALM service key parameter *clientid*
        3.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*


7.  Save the communication system.



### Create Communication Arrangement

The communication arrangement is necessary to schedule the collectors.

1.  In SAP Marketing Cloud, navigate back to *Communication Management* and choose *Communication Arrangements*.
2.  Check if there's already a communication arrangement for scenario *SAP\_COM\_0527* for the SAP Cloud ALM tenant you want to connect.
    1.  In the *Search* field, enter `0527` .
    2.  If you find a communication arrangement, check if it uses the communication system for the SAP Cloud ALM tenant you want to connect.
    3.  If a communication arrangement already exists, move on to the use case selection \(step 5\).

3.  Choose *New* to create a communication arrangement.
    1.  *Scenario*: Select *SAP\_COM\_0527 - Application Monitoring Push Integration*.
    2.  *Arrangement Name*: Enter a name.

4.  Enter the communication system for your SAP Cloud ALM tenant in the *Communication System* field.
5.  Select each use-case for which you want to collect data.
6.  The *Outbound Communication* fields are automatically propagated from the communication system.
7.  Under *Outbound Services*:
    1.  *Scheduler*: Enter a slash \(/\) in the *Path* field and choose enter. This triggers the propagation of the fields below.
    2.  *Job Execution Details*: Schedule the job to run every minute. The job is active after saving.

8.  Save the communication arrangement.



## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

