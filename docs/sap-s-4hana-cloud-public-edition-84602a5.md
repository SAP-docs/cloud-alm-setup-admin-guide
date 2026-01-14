<!-- loio84602a521c5946f88a409b39587dd70e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP S/4HANA Cloud Public Edition

This page explains how to connect SAP S/4HANA Cloud Public Edition to SAP Cloud ALM to enable monitoring.

Currently, SAP S/4HANA Cloud Public Edition supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)
-   [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)

The following video demonstrates the setup steps for integration and business process monitoring for SAP S/4HANA Cloud Public Edition. A textual step-by-step description of all setup steps is provided after the video on this site.







<a name="loio84602a521c5946f88a409b39587dd70e__section_i2g_yh5_bhc"/>

## Prerequisites

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

You have a user with administrator authorization \(for example, *SAP\_BR\_ADMINISTRATOR*\) in your SAP S/4HANA Cloud Public Edition tenant.



<a name="loio84602a521c5946f88a409b39587dd70e__section_vyt_335_bhc"/>

## Setup in SAP S/4HANA Cloud Public Edition



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



### Create Communication Arrangement for Business Process Monitoring

> ### Note:  
> Before you can create this communication arrangement, you must have created the SAP\_COM\_0527 communication arrangement that's described in the previous section. This is necessary even if you don't want to use any of the use cases in SAP\_COM\_0527. Create the SAP\_COM\_0527 communication arrangement anyway and deselect all use cases.

1.  In your service tenant, navigate to *Communication Management* and choose *Communication Arrangements*.
2.  Choose *New* to create a new communication arrangement:
    1.  *Scenario*: Select *SAP\_COM\_0523 - Business Process Monitoring Push Integration*.
    2.  *Arrangement Name*: Enter a name.
    3.  Choose *Create*.

3.  On the *Communication Arrangements* tab, in the *Communication System* field, choose the communication system you've created before.
4.  In the *Outbound Services* section, enter the path and service URL for each of the outbound services:
    1.  *SAP Cloud ALM - BPMon Configuration*:

        *Scheduler*: Enter in the *Path* field choose enter. This triggers the propagation of the following fields.

        *Job Execution Details*: Run every hour

    2.  *SAP Cloud ALM - BPMon Data*

        *Scheduler*: Enter in the *Path* field choose enter. This triggers the propagation of the following fields.

        *Job Execution Details*: Run every minute


5.  Choose *Save* to save the communication arrangement.
6.  After the successful activation, the data collection starts, and the tenant for SAP S/4HANA Cloud Public Edition appears in the configuration pane in the *Business Process Monitoring* app of SAP Cloud ALM.



<a name="loio84602a521c5946f88a409b39587dd70e__section_mzk_yn5_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



<a name="loio84602a521c5946f88a409b39587dd70e__section_xlw_145_bhc"/>

## Troubleshooting

To troubleshoot any issues with the setup or the data collection for SAP BTP, ABAP environment, also refer to [Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md).

