<!-- loio961dfa68df414b338c588e5e9659505e -->

# SAP Build Process Automation

This document provides guidance on connecting custom-built applications in the SAP BTP, Neo environment to SAP Cloud ALM for monitoring purposes.

The following monitoring applications are supported for SAP Cloud ALM:

-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)



## Prerequisites

-   You have a user with the *Destination Administrator* authorizations in the SAP BTP subaccount for your SAP Build Process Automation subscription.
-   You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).




## Setup in SAP BTP Cockpit



### Create Destination in BTP Cockpit

1.  Log on to SAP BTP Cockpit and navigate to the subaccount for your SAP Build Process Automation.
2.  Go to the *Connectivity* tab and choose *Destinations*.
3.  Choose *New Destination*.
4.  Create a new destination using the *Blank Template* view.
5.  *Name*: Enter a name for the destination, such as `sap_process_automation_cloud_alm`.
6.  *Type*: HTTP
7.  *URL*: Use the SAP Cloud ALM service key parameter *Endpoints*\>*Api*, without *api*. Ensure to keep the slash \(/\) at the end.
8.  *Authentication*: Select *OAuth2ClientCredentials*.
9.  *Client ID*: Use the SAP Cloud ALM service key parameter *clientid*.
10. *Client Secret*: Use the SAP Cloud ALM service key parameter *clientsecret*.
11. *Token Service URL*: Use the SAP Cloud ALM service key parameter *uaa*\>*url*+ `/oauth/token`.
12. Choose *Save*.



## Setup in SAP Build Process Automation



### Activate Monitoring Use-Cases

1.  Log on to SAP Build Process Automation.
2.  Choose the drop-down icon next to *Backend Configuration* and select SAP Cloud ALM.
3.  Enter a service name, for example, the tenant ID of your SAP Build Process Automation.
4.  Choose *Save*.
5.  The *Register* button is now active. Choose *Register*.
6.  Activate the monitoring data collection for the monitoring use cases as described in [Using SAP Cloud ALM](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/c9866b1053cd4cec82b90ed97bcd1239.html?locale=en-US).

If you already performed the registration and the monitoring setup earlier, follow the section [Existing Configuration](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/1d16bf5153b949f6b9700dad6fdec08d.html?version=Cloud#existing-configuration).



## Next Steps

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

-   **[Configure SAP Build Process Automation for Operations Automation](configure-sap-build-process-automation-for-operations-automation-3380ff6.md "")**  


