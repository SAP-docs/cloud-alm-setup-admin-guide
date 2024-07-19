<!-- loio5aa24f076e3b4b47839f762baa7d089a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP S/4HANA Cloud Private Edition and On-Premise Systems

By enabling the transport management for SAP S/4HANA Cloud Private Edition and SAP NetWeaver Application Server for ABAP on-premise, you can orchestrate the deployment of transport requests through your implementation landscape.

To use the `Change and Transport System (CTS)` for SAP S/4HANA Cloud Private Edition, and SAP NetWeaver Application Server for ABAP on-premise in an SAP Cloud ALM environment, you have to establish a connection between SAP Cloud ALM and the `CTS`.

You can perform this action with transaction `/sdf/ALM_SETUP` in the respective clients of your SAP S/4HANA Cloud Private Edition or On-Premise systems. For more information refer to the following documentation [Change and Transport System](https://help.sap.com/docs/SAP_NETWEAVER_740/4a368c163b08418890a406d413933ba7/48c4300fca5d581ce10000000a42189c.html?locale=de-DE).

> ### Caution:  
> Transport-related data is pushed to SAP Cloud ALM from your managed systems by setting up the integration. This includes data of the transport owner.



<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_tyl_m5p_rzb"/>

## Technical Prerequisites



### For the Transport Management System \(TMS\) Setup

If you are not familiar with the Change and Transport System in an ABAP environment, please make yourself familiar with the concepts in the following documentation [Change and Transport System](https://help.sap.com/docs/SAP_NETWEAVER_740/4a368c163b08418890a406d413933ba7/48c4300fca5d581ce10000000a42189c.html?locale=en-US).

For more information about the configuration of transport routes refer to [**Configuring Transport Routes**](https://help.sap.com/docs/SAP_NETWEAVER_740/4a368c163b08418890a406d413933ba7/44b4a1df7acc11d1899e0000e829fbbd-239.html?locale=en-US).

Currently supported landscapes:

-   Any kind of consistent Transport Management System \(TMS\) landscape. The last system in a track will always be treated as a production system.

-   Client-specific transport routes \(TMS option CTC\) are recommended.

-   TMS transport groups are supported.


> ### Caution:  
> If you want to implement landscape changes, please note the following information:
> 
> -   Adding new systems to a track is supported as long as no consolidation routes are changed. Mind that you need to adjust the transport buffers manually.
> 
> -   Refreshing a \(test\) system is supported if the system ID stays the same. This still means, the transport buffers and imports need to be adjusted manually.
> 
> -   Changing delivery routes is partly supported. This means, the transport buffers need to be adjusted manually and removed systems are still reported on in the feature traceability.
> 
> -   Deleting a system from a track is partly supported. This means, the transport buffers need to be adjusted manually and the deleted system is still reported on in the feature traceability. Also, transport requests created in the deleted systems are still available in the transport assignment.
> 
> -   Replacing or deleting the development systems isn't supported. The transports of replaced or deleted development systems are still available in the assign pop-up, feature, and *Feature Traceability* app.
> 
> -   Switching on or off client-specific transport routes isn't supported.
> 
> -   Do not perform any manual transport activities in CTS with transports managed by SAP Cloud ALM, for example imports, buffer manipulations or system copies. There is no self-healing mechanism available in these cases.
> 
> -   Virtual systems are currently not supported.

If you need to perform unsupported changes of the transport configuration in the Transport Management System \(TMS\), make sure that all open features and transports are completed and deployed to the production system. Therefore, the transport buffers should be empty.

> ### Tip:  
> We strongly recommend using always client-dependent transport routes \(TMS option CTC\) from the very beginning. By using client-dependent transport routes, you can always enhance your landscape with additional clients. Turning on client-dependent transport routes at a later point in time is a complete landscape change that isn't supported while there are still transports open.
> 
> We strongly recommend using a transport target group as a consolidation target. By using the transport target group, you can always change your consolidation systems by just changing the systems within the consolidation target group while technically the consolidation target \(which is the consolation target group\) stays stable.
> 
> ![](images/System_Landscape_22cfc8a.png)



### For the ABAP System

Before you can start enabling the transport management for SAP S/4HANA Cloud Private Edition or SAP NetWeaver Application Server for ABAP on-premise, you need to fulfill the following prerequisites:

-   Install SAP\_BASIS 7.40 SP20 or higher \(accordingly 7.50 SP04\).

-   For ST-PI 740 SP 26 and SP 27, install [3421256](https://me.sap.com/notes/3421256) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 24 and 25, install [3374186](https://me.sap.com/notes/3374186) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 23, install [3310406](https://me.sap.com/notes/3310406) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 22, install [3310406](https://me.sap.com/notes/3310406) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).

-   For ST-PI 740 SP 21, install correction [3240966](https://me.sap.com/notes/3240966) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).

-   For ST-PI 740 SP 20, install corrections [3240966](https://me.sap.com/notes/3240966) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).

-   For ST-PI 740 SP 19, install corrections [3196078](https://me.sap.com/notes/3196078) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).

-   For ST-PI 740 SP 18, install corrections [3196078](https://me.sap.com/notes/3196078) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).

    It's recommended to install the current version of collective corrections.

-   Check that the profile parameter `icm/HTTPS/client_sni_enabled` is set to `TRUE`, as described in SAP Note [510007](https://me.sap.com/notes/510007).

    > ### Note:  
    > For the profile parameter check, you can use the transaction `RZ11` in the managed system.

-   Check that the profile parameter `ssl/client_ciphersuites` is set according to section 7 of SAP Note [510007](https://me.sap.com/notes/510007).

-   Make sure that the following [certificates](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html) are imported in `STRUST` under *SSL Client \(Anonymous\)* and *SSL Client \(Standard\)*:

    -   DigiCertGlobalRootCA

    -   DigiCertGlobalRootG2

    -   DigiCertRSA4096RootG5





<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_sdm_xx4_sqb"/>

## Required Authorizations

You need to consider two users in the managed ABAP system for the setup.

Note that the authorization steps are only needed for system client 000. For other clients, these steps can't be performed.

-   To run transaction `n/SDF/ALM_SETUP`, the user needs the PFCG role `SAP_SDF_ALM_SETUP`.

    > ### Note:  
    > In this role, you need to maintain the authorization field `S_BTCH_NAM > BTCUNAME` either with '\*' or with the user name of the user that you plan to use for the data collection background job.

-   The user you specify as the background user requires the PFCG role `SAP_SDF_ALM_METRIC_PUSH_FND` and the role `SAP_BC_TRANSPORT_ADMINISTRATOR`.

    > ### Note:  
    > Don't forget to activate the role `SAP_BC_TRANSPORT_ADMINISTRATOR` before using it with the background user.

    Download the latest version of the role `SAP_SDF_ALM_METRIC_PUSH_FND` from SAP Note [3104662](https://me.sap.com/notes/3104662).




<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_pws_sst_tqb"/>

## Procedure



### Configuration Steps

It's necessary to establish a connection between the Change and Transport System \(CTS\) of the managed systems and the SAP Cloud ALM application.

The communication between the SAP Cloud ALM tenant and the CTS of your managed systems transport track is performed by the `ST_PI SW` component of your managed systems that calls the SAP Cloud ALM application through the SAP Cloud ALM API service credentials.

To set up the connection between your managed systems and the SAP Cloud ALM applications like the *Features* app, you need to retrieve your service key or service credentials of the SAP Cloud ALM API service instance and then connect your SAP systems to your SAP Cloud ALM instance.

As a first step, you need to retrieve the service credentials for your *SAP Cloud ALM API* instance.

> ### Note:  
> To perform the setup steps, you have to make yourself familiar with how to work with the SAP BTP cockpit. [Basic Platform Concepts](https://help.sap.com/docs/btp/sap-business-technology-platform/btp-basic-platform-concepts?locale=en-US).

Depending on the provisioning date of your SAP Cloud ALM tenant, the creation and configuration of your entitlements in the subaccount containing your SAP Cloud ALM subscription is generated automatically or has to be adjusted manually. See [Retrieving Service Credentials](retrieving-service-credentials-448f9f1.md).


<table>
<tr>
<th valign="top">

Provisioning Date

</th>
<th valign="top">

Actions

</th>
</tr>
<tr>
<td valign="top">

On or after October 16, 2023

</td>
<td valign="top">

The required service credentials have already been generated automatically as part of the provisioning of your SAP Cloud ALM tenant.

You can skip the steps altogether and access your credentials in the SAP BTP cockpit or in the *Landscape Management* app, as described in [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md).

</td>
</tr>
<tr>
<td valign="top">

Between June 12, 2023 and October 16, 2023

</td>
<td valign="top">

Service credentials that can be used to connect managed services to SAP Cloud ALM for operations monitoring applications was generated automatically.

You can access them in the SAP BTP cockpit or in the *Landscape Management* app, as described in [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md).

You only need to carry out the steps described in [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md) if you want to set up transport management, but you no longer have to configure your entitlements.

</td>
</tr>
<tr>
<td valign="top">

Before June 12, 2023

</td>
<td valign="top">

No service credentials have been created as part of the provisioning of your SAP Cloud ALM tenant. To create one manually, perform the steps in [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md).

</td>
</tr>
</table>

> ### Note:  
> If you want to enable the **SAP Cloud ALM API** in a Cloud Foundry environment, please refer to the following guide [Enabling SAP Cloud ALM API in Cloud Foundry](enabling-sap-cloud-alm-api-in-cloud-foundry-7d4c180.md) . Please note that this not the recommended approach anymore.

The configuration of the push data provider in your in your SAP S/4HANA Cloud Private Edition and On-Premise systems is needed to enable the processing of batch jobs. These batch jobs are then scheduled to send and receive data as well as tasks to and from SAP Cloud ALM that are needed for the processing of transport jobs.

> ### Note:  
> To perform the following steps, you need knowledge about how to work with transactions in the ABAP environment.

1.  Log on to `ABAP system client 000`.

    > ### Note:  
    > Step 1 has to be performed for each system that has to be connected.

2.  Start the transaction`/n/SDF/ALM_SETUP`.

    If you start the transaction for the first time, it looks like this:

    ![](images/O11_Screenshot_e20e8bd.png)

3.  *Target ALM Destination*

    To create a new `SAP Cloud ALM Destination`, enter a name \(for example SAP Cloud ALM\) and confirm your input with the [Enter\] key.

    To change an existing SAP Cloud ALM destination, select one from the [F4\] input help and press [Enter\].

    Press [Enter\]. The subsequent fields are filled out automatically.

4.  *Maintain HTTP Destination*

    1.  Choose *Update Destination*.

    2.  Copy the content of the JSON file \(see [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md) if you have to enable the SAP Cloud ALM API or [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md) if you already have a service key\) by choosing *Paste Service Keys* and paste it into the text field popup.

        > ### Note:  
        > In the popup, you ave to enter the following values in the respective fields:
        > 
        > -   If your system is hosted by SAP, please enter the value `proxy` in the *Proxy Host* field. \(If required by your network infrastructure\).
        > 
        >     .
        > 
        > -   If your system is hosted by SAP, please enter the value 3128 in the*Proxy Port* field \(if required by your network infrastructure\).

    3.  Choose *Continue*. The destination is now updated.

        A success message appears if the connection was established.


5.  *Enter Background*

    1.  If the *Target ALM Root URL* field isn't already prefilled, enter the target SAP Cloud ALM root URL depending on your region, for example `https://eu20.alm.cloud.sap`.

        This is the URL that is shown in the JSON file during the creation of the service key [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md). How to retrieve the information of the service key can be found in the following documentation [Managing Your Service Credentials](managing-your-service-credentials-87b7851.md). The URL is shown under *endpoints.API* or *uaa.url* respectively. The SAP Cloud ALM root URL depends on the region of the customer account was created under, for example `eu10.alm.cloud.sap` or `eu20.alm.cloud.sap`.

    2.  Enter the background user that you created to perform the data collection.

    3.  Choose *Register* to call SAP Cloud ALM and register the system.

    4.  Choose *Continue*.

        An `LMS ID` is retrieved and displayed.


    To unregister a system, choose *Unregister*.

    This stops all data collection and heartbeat measurements.

6.  Select the use cases that you want to collect and push data for. The push mechanism supports the following use cases:

    -   For development systems \(client 000\): `Transports: Read`

        Reports transport requests to SAP Cloud ALM for assignment to features.

        It's only necessary to set up on source systems: specifically DEV systems.

    -   For development systems \(working client\): Transports: Create & Export \(client-specific\):

        The use case `Transports: Create & Export (client-specific)` enables following transport-related functions:

        -   Create transports

        -   Create transport of copies

        -   Release transports

        -   Delete empty transports \(during release\)


    -   For a domain controller system \(client 000\): `Transports: Read Landscape`

        Reports the `STMS` landscape configuration to SAP Cloud ALM.

    -   All target systems \(test or production, client 000\): `Transports: Import` 

        Queries the requests that are to be imported from SAP Cloud ALM and triggers the import job.

        Only needs to be set up on consolidation and target systems for import \(that is, QA and PRD systems\).

        In case you don't find these use cases in the list, try to rule out connection issues.

        For example, your service key is outdated and has to be generated again, as described in [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md).

        More solutions for connection problems can be found in the [**Issues and Solutions**](https://help.sap.com/docs/cloud-alm/setup-administration/issues-and-solutions-on-premise?locale=en-US) guide.

    -   A typical 3-tier landscape looks like that:

        -   Transport route: `O11.100 (DEV)` –\> `O12.100 (TEST)` –\> `O13.100 (PROD)`
        -   Domain controller: `O11`


        The following table shows the different use cases per client.

        **Use Case Available per Client**


        <table>
        <tr>
        <th valign="top">

        Use Case / Client
        
        </th>
        <th valign="top">

        `O11.000`
        
        </th>
        <th valign="top">

        `O11.100`
        
        </th>
        <th valign="top">

        `O12.000`
        
        </th>
        <th valign="top">

        `O13.000`
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `Transports: Create & Export (client-specific)`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
        Active
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Transports: Import` 
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
        Active
        
        </td>
        <td valign="top">
        
        Active
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Transports: Read Landscape`
        
        </td>
        <td valign="top">
        
        Active
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Transports: Read`
        
        </td>
        <td valign="top">
        
        Active
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        </table>
        

    Commonly, authorization-checks are performed in the system where a change happens. For the *Features* app, this app takes over the authorization check for importing transports in the SAP Cloud ALM environment instead of the managed system. In the managed system, the user you specified as the background user for the data collection performs the transport actions. Since this background user has transport authorization by definition, the distinct check whether a specific end user is allowed to perform a transport operation is done in SAP Cloud ALM.

7.  Choose *Continue*.

8.  If everything is set up correctly, it looks like this:

    ![](images/Enabling_Transport_Management_Result_cc9fec4.png)




<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_amq_jvv_k5b"/>

## Configuration of Client-Dependent Use Cases



### Relevant Jobs in Managed Systems

There are important jobs to be executed in the managed systems. The jobs mentioned below should be at least released, but always check for scheduled and active jobs in case of issues.

To create and release transports as well as creating transport of copies, for example in client 100 of the development system use the following transaction:`/SDF/CALM_CDM_TR_PROC_CL_DEP-100`

> ### Note:  
> The job `/SDF/CALM_CDM_DIAGNOSTICS` pushes data about the available capabilities in the managed system `ST-PI` to SAP Cloud ALM.
> 
> This job is supposed to be released and executed once per day and client.
> 
> For the import of transports there's a job executed in each target system client `000`:`/SDF/CALM_CDM_IMPORT_TRANSPORTS`

To enable the use cases mentioned above within an SAP Cloud ALM feature, execute the following setup in each development client that you want to use:

> ### Note:  
> Before you start with the setup, please make sure that you've performed all the configuration steps in the **Technical Prerequisites for the ABAP System** section of this guide. Additionally, make sure that you've implemented the current version of the SAP Note. Currently it's [3322679](https://me.sap.com/notes/3322679).
> 
> Also make sure that setup for client 000 was already performed and that the use case **Feature Deployment: Manage Transports** was already activated.



1.  Log on to the respective ABAP system client and start the transaction `/n/SDF/ALM_SETUP`.

2.  You can reuse the SAP Cloud ALM destination from your PUSH data configuration.

    At the start of the process, the transaction looks like this:

    ![](images/Setup_Integration_1_438f734.png)

3.  Under *Maintain HTTP Destination*, choose *Update Destination* and paste the JSON file you've already created in the **Configuration Steps** section of this guide above.

4.  Under *Enter Background User and Register System*, choose *Unregister*.

5.  Enter the background user that you've created to perform the data collection.

6.  Choose *Register* to call SAP Cloud ALM and register the system. Confirm the scheduling of the respective jobs.

    ![](images/Register_System_3b7cbb0.png)

    If it’s successful, an `LMS ID` is retrieved and is displayed.

7.  Select the use case that you want to activate:

    `Transports: Create & Export (client specific)`

    -   Queries to-be-released transport requests from SAP Cloud ALM and triggers the release job.
    -   It's necessary to execute this setup on all development clients you use for customizing activities.

8.  If everything is set up correctly, it looks like this:

    ![](images/Result_Setup_a02ee52.png)




<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_z4g_lfq_d1c"/>

## Configuration of the Transport Organizer Web UI

Before you can start using the navigation to the transport organizer for CTS-managed transports by using the transport id in the *Features* app, you have to activate the Web service for transport organizer web ui.

Follow the steps in the [Activating the Web Service for Transport Organizer Web UI](https://help.sap.com/docs/SAP_NETWEAVER_700/109ce05a6c531014b4e8fe6b0570a984/45ec35a90fdc3481e10000000a1553f6.html) documentation.

> ### Note:  
> If the transport organizer web ui is throwing exceptions, check the following:
> 
> -   Make sure that you've configured the start authorization according to the following notes: [1413011](https://me.sap.com/notes/1413011) and/or [3064888](https://me.sap.com/notes/3064888) respectively.
> 
> -   Check the HTTP\_WHITELIST [0002578665](https://me.sap.com/notes/0002578665) and the UCON\_CHW allowlist [0003290787](https://me.sap.com/notes/0003290787).
> 
>     See also [**How to maintain the table HTTPURLLOC**](https://help.sap.com/docs/SUPPORT_CONTENT/abapconn/3354079499.html).
> 
> -   In case, the standard URL \(Root URL\) doesn't fit your needs \(for example, because you use the allowlist mentioned above\), you can adjust the Logon URL in *Landscape Management* for the affected system, so that it reflects your URL on the allowlist. For more information, see [**Landscape Management**](https://help.sap.com/docs/cloud-alm/applicationhelp/landscape-management?locale=en-US).



<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_zls_yfj_gvb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Create incidents for the *Features* app in [SAP for Me](https://me.sap.com/app/casecreate), under component SV-CLM-IMP-FTR .

