<!-- loioa9abd7d5343643a7a0577bc9f98b74f1 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP BTP, ABAP environment \(custom-built applications\)

This document provides guidance on connecting SAP BTP, ABAP environment to SAP Cloud ALM for monitoring purposes.

Currently, the following monitoring applications are supported for the SAP BTP, ABAP environment:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)



## Prerequisites

You have a user with administrator authorizations in SAP BTP, ABAP environment.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



## Setup in SAP S/4HANA Cloud Public Edition



### Create Communication System

1.  Log on to your SAP S/4HANA Cloud Public Edition.
2.  In the *Communication Management* group, the *Communication Systems* tile.
3.  Check if there already is a communication system for your SAP Cloud ALM tenant:
    1.  In the *Search* field, search for the endpoint host, for example, `eu10.alm.cloud.sap`.
    2.  To verify that the **identical** SAP Cloud ALM tenant is addressed, compare the value in the *Token Endpoint*field.
    3.  If a communication system exists, continue with *Create Communication Arrangement*, described in the next section.

4.  Choose *New* to the create a new communication system.
5.  Enter a system ID and description and choose *Create*.
6.  Enter the following values:
    -   *Host Name*: The host part of the SAP Cloud ALM service key parameter "Api", e.g., eu10.alm.cloud.sap
    -   *Port*: 443
    -   *OAuth 2.0 Settings*:

        *Token Endpoint*: SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.

    -   Under *Users for Outbound Communication*, choose :heavy_plus_sign: to create a new user:
        -   *Authentication Method*: *Choose OAuth 2.0*
        -   *OAuth 2.0 Client ID*: SAP Cloud ALM service key parameter `clientid`.
        -   *Client Secret*: SAP Cloud ALM service key parameter `clientsecret`.


7.  Save the communication system.



### Create Communication Arrangement

The communication arrangement is necessary to schedule the data collectors.

1.  Navigate to the *Communication Management* view and select *Communication Arrangements*.
2.  Check if there's already a communication arrangement for scenario *SAP\_COM\_0527* for this SAP Cloud ALM tenant:
    -   In the *Search* field, enter `0527`.
    -   If a communication arrangement already exists, check if it uses the communication system for the SAP Cloud ALM tenant that you want to connect.

        If a communication arrangement already exists, don't create a new one and move on step 5.


3.  Choose *New* to create a new communication arrangement:
    1.  *Scenario*: Select *SAP\_COM\_0527 'Application Monitoring Push Integration'*.
    2.  *Arrangement Name*: Enter a name.

4.  Under *Communication System*, enter the communication system for your SAP Cloud ALM tenant.
5.  Select each use case for that you want to collect data.
6.  The *Outbound Communication* fields are automatically propagated from the communication system.
7.  Enter the following under *Outbound Services*:
    1.  *Scheduler*: Under *Path*, enter a slash \(/\) and choose enter. This will trigger the propagation of the following fields.
    2.  *Job Execution Details*: Schedule the job to run every 1 minutes. The job is activated after saving.

8.  Choose *Save*.



## Next Steps

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).



## Troubleshooting

To troubleshoot any issues with the setup or the data collection for SAP BTP, ABAP environment, also refer to [Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md).

