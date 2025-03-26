<!-- loio5aa24f076e3b4b47839f762baa7d089a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP S/4HANA Cloud Private Edition and On-Premise Systems

Learn how to configure your SAP Cloud ALM deployment scenario for CTS integration.

When you enable the transport management for SAP S/4HANA Cloud Private Edition and SAP NetWeaver Application Server for ABAP on-premise, you can orchestrate the deployment of transport requests through your implementation landscape.

SAP NetWeaver Application Server for ABAP \(7.40 or higher\) can be an SAP S/4HANA on-premise system, an SAP S/4HANA Cloud Private Edition, and an ECC system, where SAP Cloud ALM integrates with the Change and Transport System \(CTS\).

To use the Change and Transport System \(CTS\) for SAP S/4HANA Cloud Private Edition and SAP NetWeaver Application Server for ABAP on-premise in an SAP Cloud ALM environment, you have to establish a connection between SAP Cloud ALM and the CTS.

> ### Note:  
> Transport-related data is pushed to SAP Cloud ALM from your managed systems by setting up the integration. This includes data of the transport owner. For more information, see SAP Note [3429058](https://me.sap.com/notes/3429058).

Currently any kind of consistent Transport Management System \(TMS\) landscape is supported. The last system in a track is always treated as a production system.

> ### Note:  
> CTS+ is not supported.

> ### Note:  
> Client-specific transport routes \(TMS option CTC\) are recommended.
> 
> TMS transport groups are supported.

> ### Caution:  
> If you want to implement landscape changes, please note the following:
> 
> -   Identical SIDs are not supported.
> 
> -   TMS domains with the same domain name are not supported.
> 
> -   Adding new systems to a track is supported as long as no consolidation routes are changed. Mind that you need to adjust the transport buffers manually.
> 
> -   Refreshing a \(test\) system is supported if the system ID stays the same. This still means, the transport buffers and imports need to be adjusted manually. For more information, see [System Refresh](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap-740.html?anchorId=section_copy_copy_co#section_copy).
> 
> -   Changing delivery routes is partly supported. This means, the transport buffers need to be adjusted manually and removed systems are still reported on in the feature traceability.
> 
> -   Deleting a system from a track is partly supported. This means, the transport buffers need to be adjusted manually and the deleted system is still reported on in the *Feature Traceability* app. Also, transport requests created in the deleted systems are still available in the transport assignment.
> 
> -   Replacing or deleting the development systems isn't supported. The transports of replaced or deleted development systems are still available in the assign pop-up, feature, *Transport Analysis* app, and *Feature Traceability* app.
> 
> -   Manually deleted transports in the managed system are still available in the assign pop-up, feature, *Transport Analysis* app, and *Feature Traceability* app.
> 
> -   Switching on or off client-specific transport routes isn't supported.
> 
> -   We recommend avoiding manual import activities in CTS with transports managed by SAP Cloud ALM.
> 
> -   Do not perform buffer manipulations in CTS with transports managed by SAP Cloud ALM. There is no self-healing mechanism available.
> 
> -   Virtual systems are currently not supported.
> 
> -   We don't support client copies in the *Features* app. If you're creating a client copy, we suggest you first create a new client. Then, you should wait until you connect the newly created client using TMS transport routes, making it available in SAP Cloud ALM. Once you have completed the distribution into the production system of transport requests released before the client copy, you can activate the transport routes to make the new client available in SAP Cloud ALM. Mind that you need to adjust the transport buffers manually.

The following steps show you how to create a test landscape to try out the SAP Cloud ALM Deployment Management scenario without interfering with the productive TMS landscapes. You can also follow the steps to create your productive landscape. For this, you just have to use your systems instead of the described test systems.

1.  [Configuring your Transport Management System \(TMS\) on the Managed Systems](configuring-your-transport-management-system-tms-on-the-managed-systems-a9ae2e3.md).

2.  [Binding Credentials of the SAP Cloud ALM API Service Instance](binding-credentials-of-the-sap-cloud-alm-api-service-instance-6c734bd.md).

3.  [Setting Up the Managed Systems](setting-up-the-managed-systems-21e0843.md).


When you finished the steps above, you can start with the setup in the SAP Cloud ALM apps. First, you have to create a project in the *Projects and Setup* app, for this see [Projects and Setup](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/6dd14269bc6e48ec81875f38d920ea6e.html "In the Projects and Setup app, you can manage your projects in SAP Cloud ALM.") :arrow_upper_right:. Then, you can create a feature in the *Features* app to document changes and manage the deployment to your system. For more information, see [Features](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/1a6c29ffb3f74f0789d4bb76081eb834.html "The Features app allows you to deploy transports assigned to a feature across your system landscape. It also helps you document changes for audit purposes.") :arrow_upper_right:.

For in-depth information on the workflow of implementation in SAP Cloud ALM, see [SAP Cloud ALM for Implementation](https://support.sap.com/en/alm/sap-cloud-alm/implementation/sap-cloud-alm-implementation-expert-portal.html).



<a name="loio5aa24f076e3b4b47839f762baa7d089a__section_zls_yfj_gvb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons-V5"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Create incidents for the *Features* app in [SAP for Me](https://me.sap.com/app/casecreate), under component SV-CLM-IMP-FTR .

-   **[Configuring your Transport Management System \(TMS\) on the Managed Systems](configuring-your-transport-management-system-tms-on-the-managed-systems-a9ae2e3.md "Learn how to configure your Transport Management System (TMS) on the Managed System. ")**  
Learn how to configure your Transport Management System \(TMS\) on the Managed System.
-   **[Binding Credentials of the SAP Cloud ALM API Service Instance](binding-credentials-of-the-sap-cloud-alm-api-service-instance-6c734bd.md "Learn how to get your binding credentials for the connection between the Change and
		Transport System (CTS) of your managed systems and the SAP Cloud ALM
		application.")**  
Learn how to get your binding credentials for the connection between the Change and Transport System \(CTS\) of your managed systems and the SAP Cloud ALM application.
-   **[Setting Up the Managed Systems](setting-up-the-managed-systems-21e0843.md "Learn which prerequisites you have to fulfill for all systems you want to manage from
		SAP Cloud ALM that are part of the TMS defined transport track.")**  
Learn which prerequisites you have to fulfill for all systems you want to manage from SAP Cloud ALM that are part of the TMS defined transport track.

