<!-- loio568d9b62ec904b41ba314216d0ac5875 -->

# SAP Intelligent Robotic Process Automation \(SAP Intelligent RPA\)

This page explains how to connect SAP Intelligent Robotic Process Automation \(SAP Intelligent RPA\) to SAP Cloud ALM to enable monitoring.

Currently, SAP Intelligent RPA supports the following monitoring applications:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)

SAP Intelligent RPA is also an automation engine for SAP Cloud ALM. This means you can trigger automations in SAP Intelligent RPA from SAP Cloud ALM, for example, as a reaction to an event.

More under [Setup SAP Intelligent RPA as Operations Automation engine](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/operation-automation/irpa.html).



<a name="loio568d9b62ec904b41ba314216d0ac5875__section_jbt_rgf_bhc"/>

## Prerequisites

You have a user with the **Destination Administrator** authorizations in the SAP BTP sub-account for your SAP Intelligent RPA subscription.

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



<a name="loio568d9b62ec904b41ba314216d0ac5875__section_t2t_vhf_bhc"/>

## Setup for SAP Intelligent RPA



### **Create Destination in the SAP BTP Cockpit**

1.  Log on to the SAP BTP cockpit and navigate to the sub-account for your SAP Intelligent RPA.
2.  Go to *Connectivity* \> *Destinations*.
3.  Choose *New Destination*.
4.  Create a new destination using *Blank Template*.
    1.  *Name*: Enter a name for the destination, for example, `sap_process_automation_cloud_alm`.
    2.  *Type*: *HTTP*
    3.  *URL*: SAP Cloud ALM service key parameter *Endpoints* \> `Api` without `api`. Ensure to keep the slash \(/\) at the end.
    4.  *Authentication*: Select *OAuth2ClientCredentials*.
    5.  *Client ID*: SAP Cloud ALM service key parameter *clientid*.
    6.  *Client Secret*: SAP Cloud ALM service key parameter *clientsecret*.
    7.  *Token Service URL*: SAP Cloud ALM service key parameter `uaa` \> `url` followed by `/oauth/token`.
    8.  Add a new property named `sap.processautomation.enabled` with the value *true* for the destination.

5.  Choose *Save* to save the destination.



### Add Destination in SAP Intelligent RPA

1.  Log on to your SAP Intelligent RPA tenant.
2.  Open the drop-down list next to *Configuration* and select *Destinations*.
3.  Choose *Add New Destination*.
    1.  Find the destination that you created for SAP Cloud ALM in the previous section and select the checkbox.
    2.  Choose *Next*.
    3.  From the drop-down list, select the environment in which you want to add the destination. You can also add it to all environments, which includes all existing environments, and any new environment created later.
    4.  Choose *Add*.

4.  Save.



### Activate Monitoring Use-Cases

1.  Open the drop-down list next to *Configuration* and select SAP Cloud ALM.
2.  Enter a service name, such as your tenant ID for SAP Intelligent RPA.
3.  Save.
4.  Choose *Register*.
5.  Activate the monitoring data collection for the monitoring use-cases as described in [Using SAP Cloud ALM](https://help.sap.com/docs/IRPA/c836fab4182e45548b6c6c6d0d0a9146/bf52ab4eeeb34226b337da9503a4fb8a.html).

If you already performed the registration and the monitoring setup at an earlier point in time, follow the section [Existing Configuration](https://help.sap.com/docs/IRPA/c836fab4182e45548b6c6c6d0d0a9146/ba24c82fda0b4d97945ee7b88d135c1f.html).



<a name="loio568d9b62ec904b41ba314216d0ac5875__section_bjh_5kf_bhc"/>

## Setup in SAP Cloud ALM

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

