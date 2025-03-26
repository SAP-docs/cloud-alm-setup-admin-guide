<!-- loio21e0843b2009480282487a08044f3f34 -->

# Setting Up the Managed Systems

Learn which prerequisites you have to fulfill for all systems you want to manage from SAP Cloud ALM that are part of the TMS defined transport track.



<a name="loio21e0843b2009480282487a08044f3f34__section_dpt_n3z_bcc"/>

## Context

After you've created your SAP Cloud ALM API key/binding, you have to prepare the managed systems included in the transport track.

SAP Cloud ALM doesn't directly perform actions on the ABAP system itself. Instead, actions such as create, release, and import are triggered from your feature. Such tasks are executed by TMS using the tp command to create, release, or import the TR, ToC. So, if you encounter any issues in the managed ABAP system related to the TR release or import, you should inspect this in the TMS.



<a name="loio21e0843b2009480282487a08044f3f34__section_gpk_14r_zbc"/>

## Prerequisites and Authorizations

On the [Expert Portal](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal.html), you find the prerequisites for each managed system:

-   [SAP NetWeaver Application Server for ABAP \(7.40 or higher\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap-740.html#section_406552075_co_80551802)

-   [Setup for SAP S/4HANA and SAP Business Suite 7](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap-onprem.html#section_406552075_co)

-   [Setup for SAP S/4HANA Cloud Private Edition](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap-priv-cloud.html#section_406552075_co)


Each page includes a *Prerequisites* tab which shows you the required prerequisites and authorizations:

![](images/prereqs_9f5bddf.png)

Make sure that you fulfill the *Technical Prerequisites*, *Network Prerequisites*, and *Required Authorizations*.

> ### Note:  
> For the profile parameter check, you can use transaction `RZ11` and `TU02` in the managed system.

> ### Note:  
> For SAP S/4 HANA Cloud Private Edition:
> 
> -   You can request user `CUST_TC` for client 000. This user is authorized to run the setup transaction.
> 
> -   `BATCH_USER` is always available in the managed system and doesn't expire. You can also specifiy it as background user.



## Required SAP Notes

The following list shows you the required SAP Notes. We recommend always installing the latest ST-PI version.

-   Install SAP\_BASIS 7.40 SP20 or higher \(accordingly 7.50 SP04\).

-   For ST-PI 740 SP 26 and SP 27, install [3421256](https://me.sap.com/notes/3421256) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 24 and 25, install [3374186](https://me.sap.com/notes/3374186) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 23, install [3310406](https://me.sap.com/notes/3310406) and follow SAP Note [3425282](https://me.sap.com/notes/3425282) .

-   For ST-PI 740 SP 22, install [3310406](https://me.sap.com/notes/3310406) and follow SAP Note [3425282](https://me.sap.com/notes/3425282).




<a name="loio21e0843b2009480282487a08044f3f34__section_c3v_h4r_zbc"/>

## Configuring the PUSH Data Provider

After getting the system ready at ST-PI level, continue with establishing the connection from the managed system to SAP Cloud ALM.

SAP S/4HANA Cloud Private Edition, SAP S/4HANA and SAP Business Suite 7, and SAP NetWeaver Application Server for ABAP \(7.40 or higher\) use a PUSH mechanism to push transport management data to SAP Cloud ALM.

> ### Note:  
> If you have multiple SAP Cloud ALM tenants, you need to decide which SAP Cloud ALM instance the managed system connects to.
> 
> Here's what we recommend:
> 
> -   only connect your productive environments to your productive SAP Cloud ALM instance
> 
> -   don't connect your productive environment to both SAP Cloud ALM instances
> 
> -   only connect demo and sandbox environments to your test SAP Cloud ALM instance

On the Export Portal, choose the tab *Configure the PUSH Data Provider*.

Then, follow the steps to configure the PUSH data provider.

![](images/push_e848532.png)

> ### Note:  
> The setup must always be performed in client 000 and the source system and client where the transport request is created.
> 
> For example, in landscape *DEV:100* \> *QUA:200* \> *PRD:300*, run transaction `/SDF/ALM_SETUP` in PRD:000, DEV:000, QUA:000, and DEV:100.
> 
> For the test landscape, *S4H:100* \> *S4H:200* \> *S4H:300*, run transaction `/SDF/ALM_SETUP` in S4H:000 and S4H:100.

> ### Note:  
> If your system is hosted by SAP, remember to enter the proxy host and port when maintaining your HTTP destination.
> 
> -   Proxy Host: Enter value `proxy`
> 
> -   Proxy Port: Enter value `3128`



### Generated Jobs After the Initial Registration

After you've maintained the HTTP destination, in the system where you run `n/SDF/ALM_SETUP` in client 000 you get the following messages:

-   Scheduler job for \(entry name you chose in the Target ALM description field\) has been scheduled.

-   Auto Discovery job for \(entry name you chose in the Target ALM description field\) has been triggered.


You can check jobs in client 000 by choosing *System* \> *Jobs* \> *Job Overview*.

The following jobs should have run:

-   *CALM Auto Discovery* with status: Finished.

-   *CALM Heartbeat* with status: Finished and one job in status Released with 5 min frequency.

-   *CALM Scheduler* with status: Finished and one job in status Released with 1 min frequency.


> ### Note:  
> Make sure that the *CALM Scheduler* job has the status: Finished and one job in status released with 1 min frequency. This job triggers the subsequent deployment jobs that push the transport management data to SAP Cloud ALM.

After successful registration, you get an entry in *Landscape Management* for S4H:000 with the same LMS ID.

For example:

![](images/target_634e4b1.png)



<a name="loio21e0843b2009480282487a08044f3f34__section_otj_mgq_mdc"/>

## Activating the Use Case Transports

To activate the use case *Transports* and the respective tasks, run transaction `/n/SDF/ALM_SETUP` and choose *Activate usescases*.

![](images/activate_b65b342.png)

![](images/tasks_414ac05.png)

For each system you're using, you have to activate different tasks. For example, in landscape *DEV:100* \> *QUA:200* \> *PRD:300*, domain controller PRD, you have to activate the following tasks:

*DEV*

-   client 000: activate *Transports: Read*. You only have to activate this task on source systems as this reports transport requests to SAP Cloud ALM for assignment to features.

-   client 100: activate *Transports: Create & Export \(client-specific\)*. You have to activate this task on all development clients you're using for customizing activities. If you're using an additional client, for example 200, to create transports, you also need to activate this task in this client. This triggers the release job `/SDF/CALM_CDM_TR_PROC_CL_DEP-XXX` and enables the following transport-related functions:

    -   Create transports

    -   Create transport of copies

    -   Release transports

    -   Delete empty transports \(during release\)



*QUA*

client 000: activate *Transports: Import*. You have to activate this task in all systems you want to import to as this triggers the import job`/SDF/CALM_CDM_IMPORT_TRANSPORTS`. This queries to-be-imported transports from SAP Cloud ALM and imports them.

*PRD*

client 000: activate the following tasks:

-   *Transports: Import*

-   *Transports: Read Landscape* This reports the STMS landscape configuration to SAP Cloud ALM. The following landscapes are supported:

    -   Any kind of consistent Transport Management System \(TMS\) landscape. The last system in a track is always treated as a production system

    -   Client-specific transport routes \(TMS option CTC\) are recommended

    -   TMS transport groups are supported


-   *Transports: Check* This enables the *Transport Check* functionality to check a transport set before import to evaluate the impact on your production tenant.

    To activate this task, you need to have installed at least ST-PI 740 SP 27 and implemented the latest versions of SAP Notes [3497169](https://me.sap.com/notes/3497169) and [3497168](https://me.sap.com/notes/3497168).

    For more information, see [Transport Checks](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/2ae5a1bf1b6f4d46a38b11f6c6792425.html "With the Transport Checks, you can check a CTS-managed transport set to evaluate the impact on your production tenant. Transport checks can be performed based on a feature which defines the set of CTS-managed transports.") :arrow_upper_right:.


> ### Note:  
> For your test or productive landscape, set the collection interval to 1 min for these tasks if you want a quicker reaction to your testing of creating transport request, transport of copies, and triggering the deploy in the features.

> ### Note:  
> Once you've activated any of the tasks, the diagnostic job `/SF/CALM_CDM_DIAGNOSTIC` is started. This job runs daily in the background and sends diagnostic data. It's only necessary to set up on one system per domain \(preferably the domain controller system\)

> ### Note:  
> With ST-PI 740 SP 27, the names of the tasks have been changed.
> 
> -   *Read Transport Landscape* changed to *Transports: Read Landscape*
> 
> -   *Manage Transports* changed to *Transports: Read*
> 
> -   *Import Transports* changed to *Transports: Import*
> 
> -   *Manage Transport per Client* changed to *Transports: Create & Export \(client-specific\)*

It's only necessary to set up on one system per domainIn case you don't find these use cases in the list, try to rule out connection issues. For example, your service key could be outdated and has to be generated again, as described in [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md). For more solutions about connection problems, see [Issues and Solutions](issues-and-solutions-240043a.md).

In case of issues, open the *Analyze Application Log* `SLG1`. This system log shows you details about the use cases and jobs. For example, a component version mismatch is detected. This blocks the import of all transports assigned to features if the mismatch situation is not resolved manually at TMS level. For more information, see [Analyze Application Log](solutions-for-errors-in-the-managed-system-setup-check-93ae080.md#loio93ae080ec391461bb4d56579deaa0b00__section_uns_nj3_hdc).

In case of import issues, you can have a look at the job log. Sometimes a component version mismatch is detected. This blocks the import of all transports assigned to features if the mismatch situation is not resolved manually at TMS level.

In case several features are deployed together, all assigned transports are imported as import subset. If one transport request of the subset leads to a component mismatch situation, the import of all transports is blocked.



<a name="loio21e0843b2009480282487a08044f3f34__section_z4g_lfq_d1c"/>

## Configuration of the Transport Organizer Web UI

Before you can start navigating to the transport organizer for CTS-managed transports by using the transport ID in the *Features* app, you have to activate the Web service for transport organizer web UI.

For this, follow the steps in the [Activating the Web Service for Transport Organizer Web UI](https://help.sap.com/docs/SAP_NETWEAVER_700/109ce05a6c531014b4e8fe6b0570a984/45ec35a90fdc3481e10000000a1553f6.html).

> ### Note:  
> If the transport organizer web UI shows exceptions, check the following:
> 
> -   Make sure that you've configured the start authorization according to the following SAP notes: [1413011](https://me.sap.com/notes/1413011) and/or [3064888](https://me.sap.com/notes/3064888) respectively.
> 
> -   Check the HTTP\_WHITELIST [0002578665](https://me.sap.com/notes/0002578665) and the UCON\_CHW allowlist [0003290787](https://me.sap.com/notes/0003290787).
> 
>     See also [**How to maintain the table HTTPURLLOC**](https://help.sap.com/docs/SUPPORT_CONTENT/abapconn/3354079499.html).
> 
> -   In case the standard URL \(Root URL\) doesn't fit your needs \(for example, because you use the allowlist mentioned above\), you can adjust the Logon URL in *Landscape Management* for the affected system, so that it reflects your URL on the allowlist. For more information, see [**Landscape Management**](https://help.sap.com/docs/cloud-alm/applicationhelp/landscape-management?locale=en-US).

