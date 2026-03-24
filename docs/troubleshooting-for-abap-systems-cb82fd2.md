<!-- loiocb82fd21c2ce4a22ac47d136794a9273 -->

# Troubleshooting for ABAP Systems

This page provides guidance for resolving issues that may occur during the monitoring setup of SAP Cloud ALM for ABAP on-premise systems.

The troubleshooting information on this page applies to the following products:

-   [SAP NetWeaver Application Server for ABAP \(7.40 and higher\), including SAP BW/4HANA](sap-netweaver-application-server-for-abap-7-40-and-higher-including-sap-bw-4hana-14001e1.md)
-   SAP S/4HANA
-   [SAP S/4HANA and SAP Business Suite 7](sap-s-4hana-and-sap-business-suite-7-87ec319.md)
-   [SAP S/4HANA Cloud Private Edition](sap-s-4hana-cloud-private-edition-20bb800.md)
-   [SAP SuccessFactors Employee Central Payroll](sap-successfactors-employee-central-payroll-ea4533a.md)



## Troubleshooting for Data Collection at Runtime

The system triggers data collection periodically using the scheduled job `CALM Scheduler <Setup name in /SDF/ALM_SETUP>`. It runs the report `/SDF/CALM_SCHEDULER` and processes tasks with asynchronous RFCs.

1.  In the report `/SDF/CALM_SCHEDULER`, verify that the scheduler runs in the correct client.
2.  Check the scheduler job logs. If resources are insufficient, some tasks may not be executed.
3.  The system stores the result of each execution in the `/SDF/CALM_SCHED` table. Instance-specific collectors are recorded in the `/SDF/CALM_INST` table.
4.  Applications can write additional logging details in the application log \(`SLG1`\) for the object `/SDF/CALM`.

The job `CALM Heartbeat <Setup name in /SDF/ALM_SETUP>` is also scheduled. It uses the report `/SDF/CALM_HEARTBEAT`.

The system schedules data collection for the *Business Process Monitoring* service using these jobs:

-   `CRBPA:DC_CONTROLLER(<Setup name in /SDF/ALM_SETUP>)` \(report `/SDF/CRBPA_DC_CONTROLLER`\)
-   `CRBPA:AUTODISCOVERY(<Setup name in /SDF/ALM_SETUP>)` \(report `/SDF/CRBPA_AUTODISCOVERY`\)



## Troubleshooting for Configuration



### Error messages during registration with SAP Cloud ALM

When users select *Register*, the system makes a synchronous call to SAP Cloud ALM. If no LMS ID appears, the registration did not succeed.

-   *Cannot create HTTP Client: Operation successfully executed*

    The setup user likely lacks sufficient authorizations or the SAP\_BASIS version is too low.

-   *Cannot create HTTP Client: Destination <RFC Destination\> not defined \(See Long Text\)*

    An issue occurred during setup, such as restricted access to the target by a firewall. See SLG1 for details.

-   *Cannot save HTTP Destination: Password Too long*.

    The client credentials exceed 64 characters and the system displays this error when saving the destination. Apply SAP\_BASIS 7.40 SP24 \(7.50 SP19\) or [909503](https://me.sap.com/notes/909503) - *Use max Password length Destination API Type G*.

-   *Direct connect to ... failed NIECONN\_REFUSED\(-10\)*

    The system can't reach the target directly and requires a proxy. See [3106170](https://me.sap.com/notes/3106170) for guidance.

-   *IcmConnInitClientSSL: Proxy connection to https://....:443 via proxy:3128 failed \(proxy returned 403 Forbidden\)*

    If a proxy is required to reach the target, it must be permitted in the proxy for the ECS environment.

-   *IcmConnInitClientSSL: Proxy connection to https://....:443 via proxy:3128 failed \(proxy returned 407 Proxy Authentication Required\)*

    If the proxy requires authentication, check in SM59 for the destinations `ZSDF_<your_name>` and `ZSDE_<your_name>`. Ensure the proxy credentials are available. If not, delete the destination from `/SDF/ALM_SETUP` and create a new destination.

-   *ERROR =\> SSL handshake with ..hana.ondemand.com:443 failed: SSSLERR\_ALERT\_PROTOCOL\_VERSION ... Server aborted TLS handshake with fatal TLS*

    Check `dev_icm` in transaction `SMICM` for details. This usually indicates incorrect configuration of `ssl/client_ciphersuites`. See [51007](https://me.sap.com/notes/51007), section 7, for more information.

-   *ERROR during secussl\_read\(\) from SSL\_read\(\)==SSL\_ERROR\_SSL... secussl\_read: SSL\_read\(\) failed =\> "Failed to verify peer certificate. Peer not trusted."*

    The [DigiCert Global Root CA](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html) is likely not installed. Review this setup step in [STRUST](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html).

-   *'Oauth access\_token not found from Destination' 401*

    The password length for the service key has recently increased. Apply the latest ST-PI support package or [3240966](https://me.sap.com/notes/3240966).

    You can't use the already created destination. Delete it, then re-enter the API service key or update the client secret. If you connect other clients of this system to SAP Cloud ALM, the underlying HTTP destination remains when deleting the destination from `/SDF/ALM_SETUP`. Check if a destination `ZSDF_<your_name>` still exists. You can update the client ID and secret in SM59. Then the connection check returns status code 400.

-   *SSL handshake with <subdomain\>.authentication.<datacenter\>.hana.ondemand.com:443 failed:SSSLERR\_EWOULDBLOCK \(-71\)\#\(no error\) non-blocking network read/write could not complete\#\#\#* 

    See point two of [2728600](https://me.sap.com/notes/2728600) - *SSSLERR\_ when accessing HCI/\(S\)CPI/NEO/CF servers under \*.hana.ondemand.com*.

-   *SSL handshake with XXX:443 failed: SSSLRC\_CONN\_CLOSED \(-10\)*

    A firewall is likely preventing the request from the server to SAP Cloud ALM.

-   *No LMS ID retrieved. Scheduling jobs is skipped. Check SLG1 /SDF/CALM*

    In SLG1, you can find the URL \(`https://<DC>.alm.cloud.sap/api/landscape-management/v1/Registration`\) and the response code \(`400`\).

    Make sure the profile parameter `SAPDBHOST` is defined and the system contains a valid system number in transaction `SLICENSE`.

-   *SSL handshake with .....alm.cloud.sap:443 failed: SSSLERR\_ALERT\_HANDSHAKE\_FAILURE \(-122\)*

    With all parameters set correctly, this error or the message *received a fatal TLS handshake failure alert message from the peer* in `dev_icm` trace, indicates a TLS-intercepting network middlebox is present. You can confirm this by using `curl -S -v -k https://us10.alm.cloud.sap/ 2>&1` \(replace `us10` with your data center\).

    The output should include the following examples:

    `* Server certificate:`

    `* subject: C=DE; ST=Baden-W#rttemberg; L=Walldorf; O=SAP SE; CN=*.us10.alm.cloud.sap`

    ...

    `* issuer: C=..; O=DigiCert Inc; CN=DigiCert Global G2 TLS RSA SHA256 2020 CA1`

    If a suspicious issuer appears, such as `* issuer: CN=E....MS.cnp.int`, contact your network administrator.

-   *SSL handshake with us10.alm.cloud.sap:443 failed: SSSLERR\_PEER\_CERT\_UNTRUSTED \(-102\)*

    See [3724989](https://me.sap.com/notes/3724989) - *On-premise managed system connected to SAP Cloud ALM using DigiCert Global Root G2 encounters various errors*.




### FAQ for registration with SAP Cloud ALM

-   **What security level Root Certificate Authority do I need when connecting SAP NetWeaver 7 and SAP S/4HANA on-premise systems to SAP Cloud ALM?**

    See the blog post [SAP BTP Cloud Foundry: switching to higher security level Root Certificate Authority](https://community.sap.com/t5/technology-blog-posts-by-sap/sap-btp-cloud-foundry-switching-to-higher-security-level-root-certificate/ba-p/14061965).

-   **Which RFC destinations does the system create during connection setup?**

    When users run `/SDF/ALM_SETUP`, the system creates at least one HTTP destination. You can view the destinations in SM59 \(type G\) with the prefix `ZSDF_`. When proxy access with authentication is needed, the system creates a second destination `ZSDE_`. Don't change the path prefix in SM59. When mTLS is activated, an additional destination with the name `ZSDC<CLIENT><hash>` is created for the client activated in mTLS.

-   **My connection check result in SM59 returns HTTP 400.**

    A connection check in transaction SM59 that returns HTTP status code 400 is normal. Other codes, such as 401 \(incorrect credentials\), 403 \(forbidden\), and 500 \(error\) indicate issues.

-   **My use case can't be activated in /SDF/ALM\_SETUP.**

    Choose *Activate Usecases* and select a use case. However, saving the selection doesn't persist the changes.

    During initial setup, users can specify in each client which data to collect. SAP Cloud ALM serves as the leading instance. If the use case is deactivated after initial activation in SAP Cloud ALM or in `/SDF/ALM_SETUP`, users can only reactivate the use case in SAP Cloud ALM.

    Users can always deactivate data collection from the ABAP system.

-   Can I change the collection interval?

    The collection interval can't be changed for all tasks. Some use cases, such as Business Process Monitoring, have a dedicated scheduler and aren't triggered by the job `CALM SCHEDULER`.

    In general, changing the collection interval is not recommended. For some use cases, this affects both the quantity of data collected and persisted and may also impact event reaction.

    Certain use cases automatically adjust the collection interval if consecutive errors occur during data transmission. In these cases, the interval may reach approximately 700 minutes \(about 12 hours\). The system tries twice to collect and send data. If this is successful, it uses the default collection interval again.

-   **Can users use the Cloud Connector to send data from their on-premise system to SAP Cloud ALM?**

    The Cloud Connector from SAP can't establish the connection between SAP ABAP on-premise systems and SAP Cloud ALM.

    The Cloud Connector acts as a reverse invoke proxy between the on-premise network and SAP BTP. After connecting the subaccount to the Cloud Connector, the tunnel between SAP BTP and the on-premise landscape is activated by the BTP destination service in the connected subaccount. The Cloud Connector isn't designed to operate in the opposite direction.

    Connectivity from on-premise to cloud is only available for ABAP cloud systems, SAP HANA cloud databases, and certain SAP BTP services, such as Kubernetes clusters. It isn't available for SAP BTP services like SAP Cloud ALM.

    For more details, see [Cloud Connector FAQ](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/cloud-connector-faq) *Features* \> *Can I use the Cloud Connector from on-premise to cloud for any protocol?*.


