<!-- loio25dd0b7013a144b98f9c7e8181c7c43b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Integrated Business Planning for Supply Chain \(SAP IBP\)

This page explains how to connect SAP Integrated Business Planning for Supply Chain \(SAP IBP\) SAP HANA database to SAP Cloud ALM to enable monitoring.

Currently, the following monitoring applications are supported for SAP Integrated Business Planning for Supply Chain \(SAP IBP\):

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)
-   [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)

The following video demonstrates the setup steps to configure application monitoring for SAP Integrated Business Planning for Supply Chain. A textual step-by-step description for all setup steps is provided in the sections below the video.





<a name="loio25dd0b7013a144b98f9c7e8181c7c43b__section_sjt_chr_1hc"/>

## Prerequisites

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

You have a user with the role *SAP\_BR\_ADMINISTRATOR* in the SAP IBP tenant.



## Setup in SAP Integrated Business Planning for Supply Chain \(SAP IBP\)



### Create Communication System

1.  Log on to your service.
2.  Navigate to the *Communication Management* group and choose the *Communication Systems* tile.
3.  Check if there is already a communication system for this SAP Cloud ALM tenant.
    1.  In the *Search* field, search for the endpoint host, for example, `eu10.alm.cloud.sap`.
    2.  To verify that the correct SAP Cloud ALM tenant is addressed, compare the value in the *Token Endpoint* field.
    3.  If a communication system exists, you can move on to the section *Create Communication Arrangement*.

4.  Choose *New* to create a new communication system.
5.  Enter a system ID and description, then choose *Create*.
6.  Enter the following values:
    1.  *Host Name*: The host part of the SAP Cloud ALM service key parameter "Api", for example, `eu10.alm.cloud.sap`.
    2.  *Port*: `443`
    3.  Under *OAuth 2.0 Settings*, for the *Token Endpoint*, enter the SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.
    4.  Under *Users for Outbound Communication*, choose :heavy_plus_sign:to create a new user:
        1.  *Authentication Method*: *OAuth 2.0*
        2.  *OAuth 2.0 Client ID*: SAP Cloud ALM service key parameter *clientid*
        3.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*


7.  Choose *Save*.



### Create Communication Arrangement for Application Monitoring

The communication arrangement is necessary to schedule the collectors.

1.  In SAP Integrated Business Planning for Supply Chain \(SAP IBP\), navigate to *Communication Management* and choose *Communication Arrangements*.
2.  Check if there already is a communication arrangement for scenario *SAP\_COM\_0527* for this SAP Cloud ALM tenant: Enter `0527` in the *Search* field.

    If you find a communication arrangement, check if it uses the communication system for the SAP Cloud ALM tenant you want to connect.

    If a communication arrangement already exists, you can skip the next two steps.

3.  Choose *New* to create a new communication arrangement:
    1.  *Scenario*: Select *SAP\_COM\_0527 - Application Monitoring Push Integration*.
    2.  *Arrangement Name*: Enter a name.

4.  Enter the communication system for your SAP Cloud ALM tenant in the *Communication System* field.
5.  Select each use-case for which you want to collect data.
6.  The *Outbound Communication* fields are automatically propagated from the communication system.
7.  Under *Outbound Services*:
    1.  *Scheduler*: Enter a slash \(/\) in the *Path* field and choose *Enter*. This triggers the propagation of the fields.
    2.  *Job Execution Details*: Schedule the job to run every minute. The job is activated after saving.

8.  Choose *Save* to save the communication arrangement.



<a name="loio25dd0b7013a144b98f9c7e8181c7c43b__section_ud1_tkr_1hc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



<a name="loio25dd0b7013a144b98f9c7e8181c7c43b__section_lp2_dlr_1hc"/>

## Troubleshooting

To troubleshoot any issues with the setup or the data collection for SAP BTP, ABAP environment, also refer to [Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md).

