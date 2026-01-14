<!-- loio20bb800b4c6841a28298a4c914bee749 -->

# SAP S/4HANA Cloud Private Edition

This page explains how to connect SAP S/4HANA Cloud Private Edition to SAP Cloud ALM to enable monitoring.

Currently, SAP S/4HANA Cloud Private Edition supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)
-   [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)
-   [Configuration & Security Analysis](https://help.sap.com/docs/cloud-alm/applicationhelp/configuration-security-analysis)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)
-   [Transport Management \(feature deployment in the Implementation area\)](https://help.sap.com/docs/cloud-alm/applicationhelp/working-with-transports)

The following video demonstrates the setup steps for Integration and Exception Monitoring for SAP S/4HANA Cloud Private Edition. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loio20bb800b4c6841a28298a4c914bee749__section_yvh_mg5_bhc"/>

## Prerequisites

You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).



### Technical Prerequisites

Set up your ABAP system in transaction */SDF/ALM\_SETUP*, with the following requirements:

-   SAP\_BASIS release:
    -   7.40 SP16 or higher \(accordingly 7.50 SP05\)
    -   Or 7.40 SP09 - SP15 \(7.50 SP00 - 7.50 SP04\) with SAP Note [2283880](https://me.sap.com/notes/2283880) - Logon Username not used in RFC API

-   SAP\_UI version: SAP\_UI 740 SP15 or higher
-   Implement ST-PI 7.40 support packages and keep them up to date, including the collective corrections suited for your ST-PI support package from the required SAP Notes listed after this.

    Operate your ABAP managed system with at least the latest or second latest support package that's available on the SAP Support Portal.

-   For Business Process Monitoring in SAP S/4HANA and SAP Business Suite 7, at least ST-A/PI version higher that 01U\_731 must be available. Always keep it up to date.

    If using ST-A/PI version 01W, implement the latest versions of SAP Notes listed here.

-   The profile parameter *icm/HTTPS/client\_sni\_enabled* is set to TRUE. See also SAP Note [510007](https://me.sap.com/notes/510007) \(Additional considerations for setting up SSL on Application Server ABAP\).
-   Profile parameter *ssl/client\_ciphersuites* is defined as described in section 7 of SAP Note [510007](https://me.sap.com/notes/510007).
-   [DigiCert Global Root G2](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html) has been imported in *STRUST* under *SSL Client \(Anonymous\)* and *SSL Client \(Standard\)*.
-   [DigiCert TLS RSA4096 Root G5](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html) has been imported in *STRUST* under *SSL Client \(Anonymous\)* and *SSL Client \(Standard\)*.
-   You've installed the latest version of the following SAP Notes for ST-PI:

    -   SAP Note [3639977](https://me.sap.com/notes/3639977) – Collective corrections as of ST-PI 7.40 **SP32** for SAP Cloud ALM
    -   SAP Note [3575903](https://me.sap.com/notes/3575903) – Collective corrections as of ST-PI 7.40 **SP30** for SAP Cloud ALM \(including SP31\)
    -   SAP Note [3502641](https://me.sap.com/notes/3502641) – Collective corrections as of ST-PI 7.40 **SP28** for SAP Cloud ALM \(including SP29\)
    -   SAP Note [3421256](https://me.sap.com/notes/3421256) – Collective corrections as of ST-PI 7.40 **SP26** for SAP Cloud ALM \(including SP27\)
    -   SAP Note [3374186](https://me.sap.com/notes/3374186) – Collective corrections as of ST-PI 7.40 **SP24** for SAP Cloud ALM \(including SP25\)
    -   SAP Note [3312428](https://me.sap.com/notes/3312428) – Collective corrections for Integration & Exception Monitoring in SAP Cloud ALM
    -   SAP Note [3281776](https://me.sap.com/notes/3281776) – Job & Automation Monitoring: ST-PI 740 SP21+ fixes for on-premise jobs \(ABAP jobs and BW process chains\)




### Network Prerequisites

The communication between your ABAP system and SAP Cloud ALM happens from the ABAP system towards SAP Cloud ALM. You don't need to install an SAP Cloud Connector if you only want to set up monitoring or transport management in SAP Cloud ALM.

You only need an SAP Cloud Connector if your use case requires an endpoint to be created from SAP Cloud ALM towards the ABAP system. Currently, this is only the case for ABAP systems of the type SAP Focused Run and SAP Solution Manager or if you want to use the use SAP Business Transformation Center.

To establish the connection from the ABAP system to SAP Cloud ALM:

-   You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

-   Ensure the following URLs can be reached:
    -   The SAP Cloud ALM API URL, service key `endpoints:Api`, without `/api`.
    -   The SAP Cloud ALM OAuth URL, service key `uaa:url` followed by `/oauth/token`.
    -   If you want to activate mTLS-based authentication, you also need the SAP Cloud ALM OAuth cert URL, service key `uaa:certurl` extended by `/oauth/token`. You find this URL in the X.509-enabled service key, which is created after the mTLS-based authentication has been activated in the next section, where the PUSH Data Provider is configured.

-   If you use a proxy in your network, ensure it's configured to allow calls to these URLs. For more information, check the [Region-Specific IP Address Ranges](https://help.sap.com/docs/cloud-alm/setup-administration/region-specific-ip-address-ranges?locale=en-US&version=LATEST).
-   If your SAP ABAP system is hosted with SAP Enterprise Cloud Services \(ECS\), create a service request with SAP ECS to add the following URLs to the allowlist for your environment. This does not apply for SAP SuccessFactors Employee Central Payroll.
    -   Root URL: SAP Cloud ALM service key parameter `endpoints:api` without `/api`.
    -   OAuth URL: SAP Cloud ALM service key parameter `uaa:URL`.
    -   If you want to activate mTLS-based authentication, you also need the OAuth Cert URL: SAP Cloud ALM service key parameter `uaa:certurl`. You find this URL in the X.509-enabled service key, which is created in the next section, where the PUSH Data Provider is configured.




### Required Authorizations

For the setup, consider two users in the managed ABAP system:

-   The user performing the setup: To run transaction */SDF/ALM\_SETUP*, your personal user needs the PFCG role *SAP\_SDF\_ALM\_SETUP*.

    **Note**: In this role, maintain the authorization field *S\_BTCH\_NAM \> BTCUNAME* either with an asterisk \(\*\) or with the user name of the user that you plan to use for the background job for the data collection.

-   The user to run the background job for the data collection: Assign the roles as described in the following table:


    <table>
    <tr>
    <th valign="top">

    ST-PI Release
    
    </th>
    <th valign="top">

    Required Authorizations
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 SP31 for DVM
    
    </td>
    <td valign="top">
    
    The Data Volume Efficiency \(also known as Data Volume Management\) KPIs featured on the RISE with SAP Methodology dashboard require data collection through the data collector available from **ST-PI 7.40 SP31**.

    To ensure data collection runs without errors, assign the following role to the existing batch user: `SAP_SDF_ALM_METRIC_PUSH_DVM`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 SP29 for certificate-based authentication
    
    </td>
    <td valign="top">
    
    If you want to use certificate-based authentication, you can either create a dedicated user for the certificate rotation or assign the following role to the existing background user:

    SAP\_SDF\_ALM\_MTLS. For systems with SAP\_BASIS below 7.51, you can ignore S\_PSE\_ADM.

    **Note**: With ST-PI 7.40 SP29, Exception Monitoring is no longer a standalone use case. Therefore, the PFCG role SAP\_SDF\_ALM\_METRIC\_PUSH\_EXMON has been removed and the Exception Monitoring permissions are now included in the respective PCFG roles for Integration Monitoring and Job and Automation Monitoring.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 **SP25 and higher**
    
    </td>
    <td valign="top">
    
    In addition to the authorizations for **ST-PI 7.40 SP24**, you need:

    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_CSA
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_CSA\_S. This role allows the detection of special users \(such as SAP\*\) that use default passwords.

    In versions below ST-PI 7.40 SP25, you can either use the existing SAP Focused Run roles for Configuration and Security Analysis or the roles that are delivered with SAP Note [3372078](https://me.sap.com/notes/3372078) \(recommended\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 SP18 and higher
    
    </td>
    <td valign="top">
    
    In addition to the authorizations for **ST-PI 7.40 SP16**, you need:

    -   SAP\_FRN\_SDAGENT\_CSA\_MS. This role contains authorization objects that are delivered by SAP without an authorization. To use *Configuration and Security Analysis* in SAP Cloud ALM, maintain the following authorization objects:
        -   S\_RFC\_ADM: ICF\_VALUE = '\*'
        -   S\_DATASET: FILENAME = '\*', PROGRAM = '\*'
        -   S\_LOG\_COM: HOST = '\*', OPSYSTEM = '\*'

    -   SAP\_FRN\_SDAGENT\_CSA\_SEC\_MS. This role allows the detection of special users \(such as SAP\*\) that use default passwords.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 SP16 and higher
    
    </td>
    <td valign="top">
    
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_FND\*

    Assign the following authorizations depending on the SAP Cloud ALM use cases that you plan to activate:

    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_BPMON
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_EXMON \*
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_HEALTH \*
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_INTMON
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_JOBMON
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_PERF
    -   SAP\_BC\_TRANSPORT\_ADMINISTRATOR \(in client 000 and in the client of your development system where the target is created\)

    \* Download the latest version of the roles from SAP Note [3372078](https://me.sap.com/notes/3372078).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST-PI 7.40 SP15
    
    </td>
    <td valign="top">
    
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_FND \*
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_BPMON \*
    -   SAP\_SDF\_ALM\_METRIC\_PUSH\_EXMON \*

    \* Download the latest version of the roles from SAP Note [3054258](https://me.sap.com/notes/3054258).
    
    </td>
    </tr>
    </table>
    



<a name="loio20bb800b4c6841a28298a4c914bee749__section_rn1_yd5_bhc"/>

## Configuration of PUSH Data Provider

The monitoring for SAP NetWeaver Application Server for ABAP \(7.40 and higher\) uses a PUSH mechanism to push monitoring data to SAP Cloud ALM.

> ### Note:  
> **Use of Cloud Connector**
> 
> You cannot use the Cloud Connector from SAP to establish a connection between your SAP ABAP on-premise system and SAP Cloud ALM. The Cloud Connector acts as a reverse invoke proxy between the on-premise network and SAP BTP. After connecting the subaccount to the Cloud Connector, the tunnel between SAP BTP and the on-premise landscape is triggered by the BTP destination service in the connected subaccount. The Cloud Connector isn't designed to function in the opposite direction.
> 
> Connectivity from on-premise to cloud is only possible for ABAP cloud systems, SAP HANA Cloud databases, and specific SAP BTP services like K8s clusters. It can't be used for SAP BTP services like SAP Cloud ALM. For more information, see the *Features* section under [Cloud Connector FAQ](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector-faq?locale=en-US): *Can I use the Cloud Connector from on-premise to cloud for any protocol?*
> 
> You can use other proxy solutions between your ABAP on-premise system and SAP Cloud ALM. If you do this, ensure that you add the relevant URLs to the allowlist for the proxy as described in the *Prerequisites* under *Network Prerequisites*.

1.  Log on to the relevant client
    -   For transport management with SAP Cloud ALM : Perform the setup in client 000.
    -   For all other use cases in SAP Cloud ALM: Perform the setup in the client for which you want to collect monitoring data, such as the production client. You can perform the setup in more than one client.

2.  Start transaction */n/SDF/ALM\_SETUP*.
3.  Enter *Target ALM Description*.

    -   To create a **new** ALM destination, enter a name, such as SAP Cloud ALM, and choose *Enter*.
    -   To change an **existing** ALM destination, select one from the F4 input help and choose enter.

    The subsequent fields are filled.

4.  Maintain the HTTP destination:
    -   Choose *Update destination*.
    -   You can copy and paste the content from the JSON file created during the enablement of the SAP Cloud ALM APIs by choosing *Paste Service Keys*. \(More information under [Enabling SAP Cloud ALM API](https://help.sap.com/docs/cloud-alm/setup-administration/enabling-sap-cloud-alm-api).\)

        Or you can fill the required fields manually:

        1.  *Token Endpoint*: SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.
        2.  *Client ID*: SAP Cloud ALM service key parameter `clientid`.
        3.  *Client Secret*: SAP Cloud ALM service key parameter `clientsecret`.
        4.  *Proxy User*: if required by your network infrastructure.
        5.  *Proxy Password*: if required by your network infrastructure.
        6.  *Proxy Host*: if required by your network infrastructure.

            If your system is hosted by SAP, enter the value `proxy`.

        7.  *Proxy Port*: if required by your network infrastructure.

            If your system is hosted by SAP, enter the value `3128`.

        8.  *Root URL*: Enter the SAP Cloud ALM service key parameter `Api` without `/api`, for example `https://eu10.alm.cloud.sap`.

    -   Choose *Ok* to close the pop-up window.
    -   To delete a destination, choose *Delete destination*.

5.  Enter the background user and register the system:
    -   Enter the background user that you've created to perform the data collection.

        Ensure that it has the authorizations as described under *Prerequisites*.

    -   Choose *Register* to call SAP Cloud ALM and register the system. If the call is successful, an LMS ID from the *Landscape Management* is retrieved and displayed.
    -   To unregister a system, choose *Unregister*. Caution: This stops all data collection and heartbeat measurements.

6.  Optional: Activate the mTLS OAuth authentication with certificate rotation:
    1.  Starting with ST-PI 7.40 SP29, you can use certificate-based authentication instead of authentication based on the client ID and secret.
    2.  To activate certificate-based authentication, ensure that all points under *Prerequisites* are fulfilled.
    3.  Enter the background user for rotation.
    4.  Choose *Activate*.
    5.  The certificate and the respective service key are generated in a backbone procedure and provided to SAP Cloud ALM and the ABAP system. This process can take several minutes.
    6.  If you want to rotate the certificate on demand or deactivate the mTLS OAuth authentication, you can do this by choosing *Expert Configuration*.

7.  Select the use cases that you want to collect and for that you want to push data.



<a name="loio20bb800b4c6841a28298a4c914bee749__section_j4f_gkz_3hc"/>

## **Additional Health Monitoring Metrics for SAP HANA**

If you are using *Health Monitoring* and the SAP HANA database host is not running directly on the application host, you can add metrics as described in [Additional SAP HANA Database Health Monitoring Metrics for SAP S/4HANA](additional-sap-hana-database-health-monitoring-metrics-for-sap-s-4hana-03b2e1f.md).



<a name="loio20bb800b4c6841a28298a4c914bee749__section_gpj_pg5_bhc"/>

## Setup in SAP Cloud ALM

After the successful setup that's described in the previous section, the SAP S/4HANA Cloud Private Edition system appears as a registered service in the *Landscape Management* app of SAP Cloud ALM.

> ### Tip:  
> The data collection for the selected use cases is automatically active now.
> 
> We recommend using the standard collection interval. Only for specific requirements, change the *Collection interval* for the different use cases. *Business Process Monitoring* uses a separate scheduler, therefore this specific value can't be changed.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

For SAP Health Monitoring, also refer to [Additional SAP HANA Database Health Monitoring Metrics for SAP S/4HANA](additional-sap-hana-database-health-monitoring-metrics-for-sap-s-4hana-03b2e1f.md).



<a name="loio20bb800b4c6841a28298a4c914bee749__section_ak4_zd5_bhc"/>

## Housekeeping



### System Refresh

After you connected your SAP ABAP system to SAP Cloud ALM, the ABAP system keeps sending data to the monitoring applications.

To which ABAP system the monitoring data is assigned in the *Landscape Management* app, is determined by the LMS ID. If you perform a system refresh of your ABAP system by overwriting it with a copy from another ABAP system, this assignment breaks.

To avoid that the metrics are assigned to the source of the copy instead of the actual ABAP system, you need to save and restore the tables that contain monitoring setup information for SAP Cloud ALM.

The SAP Cloud ALM configuration is integrated in the [post-copy automation \(PCA\)](https://help.sap.com/docs/ABAP_POST-COPY_AUTOMATION/38b28084beaa4247959c1d36c3a68b6b/568bf834ff734ab88991d8015ffb6509.html).

Prerequisites are ST-PI 7.40 SP 27 \(and correction note\) and SAP Note [3501074](https://me.sap.com/notes/3501074) \(System Copy: ST-PI CALM configuration\).

If PCA isn't used, two reports support your system copy and system refresh:

-   **/SDF/CALM\_SYS\_COPY**

    After a system has been copied to create a new system based on an already configured system, you can use the report /SDF/CALM\_SYS\_COPY to delete the configuration in SAP Cloud ALM. Execute the connection to SAP Cloud ALM with /SDF/ALM\_SETUP.

-   **/SDF/CALM\_SYS\_REFRESH**

    To prepare a system refresh, you can execute this report. It creates a Transport of Copies \(ToC\) with the table content of the SAP Cloud ALM configuration. Export this request and save it. After the system refresh, you can import this transport request again.




### Configuration Tables in SAP Cloud ALM

Save and restore the following tables:

-   /SDF/DCOBQHDR
-   /SDF/DCRUNNING
-   /SDF/DCCCONFIG
-   /SDF/DCCLOGDET
-   /SDF/DCCLOGHDR
-   /SDF/DCKPICFG
-   /SDF/DCOBQDATA
-   /SDF/DCPARAMCFG
-   /SDF/AJM\_JOBS
-   /SDF/AJM\_SCHEDUL
-   /SDF/AJM\_SYNC\_PT
-   /SDF/AJM\_JOBS\_P
-   /SDF/AJM\_GRP\_JOB
-   /SDF/AJMF\_JOBS
-   /SDF/AJMF\_GR\_JOB
-   /SDF/AJMF\_JOBS\_P
-   /SDF/AJMF\_SCHEDU
-   /SDF/AJM\_PJOBS
-   /SDF/KPICINTRVL
-   /SDF/CALM\_CDMI
-   /SDF/CDM\_IMPORTS
-   /SDF/CDM\_CRT\_TR
-   /SDF/CALM\_SCHED
-   /SDF/CATEGORY
-   /SDF/IM\_PUSH\_ERR
-   /SDF/CALM\_ID
-   /SDF/CALM\_CONFIG
-   /SDF/CALM\_INST
-   /SDF/CALM\_QGROUP
-   /SDF/EXM\_EXT\_IDS



<a name="loio20bb800b4c6841a28298a4c914bee749__section_u1j_dh5_bhc"/>

## Troubleshooting

To troubleshoot any issues with the setup or the data collection for SAP S/4HANA or SAP Business Suite 7, refer to [Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md).

-   **[Additional SAP HANA Database Health Monitoring Metrics for SAP S/4HANA](additional-sap-hana-database-health-monitoring-metrics-for-sap-s-4hana-e42c544.md "Learn how to get additional metrics for the health monitoring metrics of SAP
		HANA.")**  
Learn how to get additional metrics for the health monitoring metrics of SAP HANA.
-   **[Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-20701a2.md "This page gives you some hints when you run into a problem for the communication
		scenarios SAP_COM_0523 and SAP_COM_0527.")**  
This page gives you some hints when you run into a problem for the communication scenarios SAP\_COM\_0523 and SAP\_COM\_0527.

