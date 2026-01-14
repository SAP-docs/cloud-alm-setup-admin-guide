<!-- loiof9b5f33244ca4600b911bda4e805ab0d -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Master Data Governance, cloud edition

This page explains how to connect SAP Master Data Governance, cloud edition to SAP Cloud ALM to enable monitoring.

Currently, the following monitoring applications are supported for SAP Master Data Governance, cloud edition:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loiof9b5f33244ca4600b911bda4e805ab0d__section_qp3_vtr_bhc"/>

## Prerequisites

You have a user with administrator authorizations, for example `SAP_BR_ADMINISTRATOR`, in SAP Master Data Governance, cloud edition.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loiof9b5f33244ca4600b911bda4e805ab0d__section_xhb_ztr_bhc"/>

## Setup in SAP Master Data Governance, cloud edition



### Create Communication System

1.  Log on to SAP Master Data Governance, cloud edition.
2.  Navigate to the *Communication Management* group and choose the *Communication Systems* tile.
3.  Check if there's already a communication system for this SAP Cloud ALM tenant.
    1.  In the *Search* field, search for the endpoint host, for example, `eu10.alm.cloud.sap`.
    2.  To verify that the correct SAP Cloud ALM tenant is addressed, compare the value in the *Token Endpoint* field.
    3.  If a communication system exists, you can move on to the section *Create Communication Arrangement*.

4.  Choose *New* to create a new communication system.
5.  Enter a system ID and description, then choose *Create*.
6.  Enter the following values:
    1.  *Host Name*: The host part of the SAP Cloud ALM service key parameter *Api*, for example, `eu10.alm.cloud.sap`.
    2.  *Port*: `443`
    3.  Under *OAuth 2.0 Settings*, for the *Token Endpoint*, enter the SAP Cloud ALM service key parameter `url` followed by`/oauth/token`.
    4.  Under *Users for Outbound Communication*, choose :heavy_plus_sign:to create a new user:
        1.  *Authentication Method*: *OAuth 2.0*
        2.  *OAuth 2.0 Client ID*: SAP Cloud ALM service key parameter *clientid*
        3.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*


7.  Choose *Save*.



### Create Communication Arrangement

The communication arrangement is necessary to schedule the collectors.

1.  In SAP Master Data Governance, cloud edition, navigate to *Communication Management* and choose *Communication Arrangements*.
2.  Check if there already is a communication arrangement for scenario *SAP\_COM\_0527* for this SAP Cloud ALM tenant: Enter `0527` in the *Search* field.

    If you find a communication arrangement, check if it uses the communication system for the SAP Cloud ALM tenant you want to connect.

    If a communication arrangement already exists, you can skip the next two steps.

3.  Choose *New* to create a new communication arrangement:
    1.  *Scenario*: Select *SAP\_COM\_0527 - Application Monitoring Push Integration*.
    2.  *Arrangement Name*: Enter a name.

4.  Enter the communication system for your SAP Cloud ALM tenant in the *Communication System* field.
5.  Select use-case for which you want to collect data, for example, Integration Monitoring.
6.  The *Outbound Communication* fields are automatically propagated from the communication system.
7.  Under *Outbound Services*:
    1.  *Scheduler*: Enter a slash \(/\) in the *Path* field and choose *Enter*. This triggers the propagation of the fields.
    2.  *Job Execution Details*: Schedule the job to run every minute. The job is activated after saving.

8.  Choose *Save* to save the communication arrangement.



<a name="loiof9b5f33244ca4600b911bda4e805ab0d__section_bpm_45r_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



<a name="loiof9b5f33244ca4600b911bda4e805ab0d__section_fkz_p5r_bhc"/>

## Troubleshooting

To troubleshoot any issues with the setup or the data collection for SAP BTP, ABAP environment, also refer to [Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md).

