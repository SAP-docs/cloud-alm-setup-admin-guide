<!-- loiof32dc37d10fa475f84819f46b2720095 -->

# Issues and Solutions



<a name="loiof32dc37d10fa475f84819f46b2720095__section_svw_sxj_d1c"/>

## Issues and Solutions

In this document, you can find answers to some of the most common questions and issues that may arise during the setup of the transport management of SAP S/4HANA on-premise, SAP S/4HANA Cloud Private Edition, and SAP Business Suite or SAP NetWeaver Application Server for ABAP on-premise.

****


<table>
<tr>
<th valign="top">

Issue

</th>
<th valign="top">

Solution

</th>
</tr>
<tr>
<td valign="top">

I can't create transports

</td>
<td valign="top">

Go to the managed system:

1.  Check if the service key is missing the following auth scopes.

    -   `imp-cdm-feature-manage-ui`
    -   `imp-cdm-feature-display-ui`

    If it's missing, please follow the steps from step 4 \(Maintain HTTP Destination\) on in the *Procedure* section of the [SAP S/4HANA Cloud Private Edition and On-Premise Systems](https://help.sap.com/docs/cloud-alm/setup-administration/change-transport-system#procedure) guide.

2.  Check if the use case Transports: Create & Export \(client-specific\) is active in the source tenant \(working client shouldn't be 000\).

3.  Check if the job `/SDF/CALM_CDM_TR_PROC_CL_DEP-100` is released and is running frequently in the source tenant.

4.  Check if the job` /SDF/CALM_CDM_DIAGNOSTICS` is running in development system client 000.


In SAP Cloud ALM check the following:

Source tenant is in the system group and is assigned to the project through the deployment plan.

</td>
</tr>
<tr>
<td valign="top">

I can't release transports

</td>
<td valign="top">

Go to the managed system:

1.  Check if the service key is missing the auth scopes.

2.  Check if the use case Transports: Create & Export \(client-specific\) is active in the source tenant \(working client shouldn't be 000\).

3.  Check if the job `/SDF/CALM_CDM_TR_PROC_CL_DEP-100` is released and is running frequently in the source tenant.

4.  Check if the job `/SDF/CALM_CDM_DIAGNOSTICS` is running in development system client 000.




</td>
</tr>
<tr>
<td valign="top">

I can't create Transport of Copies

</td>
<td valign="top">

Go to the managed system:

1.  Check if the service key is missing auth scopes.

2.  Check if the use case Transports: Create & Export \(client-specific\) is active in the source tenant\(working client shouldn't be 000\).

3.  Check if the job `/SDF/CALM_CDM_TR_PROC_CL_DEP-100` is released / and is running frequently in the source tenant.

4.  Check if the job `/SDF/CALM_CDM_DIAGNOSTICS` is running in development system client 000.




</td>
</tr>
<tr>
<td valign="top">

I can't deploy features

</td>
<td valign="top">

Go to the managed system:

1.  Check if the service key is missing auth scopes.

2.  Check if the use case Transports: Import Transports

    is active in target system client 000.

3.  Check if the job `/SDF/CALM_CDM_IMPORT_TRANSPORTS` is released and running in `client 000`.




</td>
</tr>
<tr>
<td valign="top">

I can't assign transports

</td>
<td valign="top">

Go to the managed system:

1.  Check if the service key is missing auth scopes.

2.  Check if the use case Transports: Read Transports is active in development client 000.




</td>
</tr>
<tr>
<td valign="top">

My import jobs are stuck

</td>
<td valign="top">

Go to the managed system:

1.  The job `/SDF/CALM_CDM_IMPORT_TRANSPORTS` is released and running.

2.  The job log of `/SDF/CALM_CDM_IMPORT_TRANSPORTS` shows a component version mismatch. This job is only running when there is a request to deploy a transport from a feature. In case several features are deployed together, all the transports assigned are imported as an import subset. If one transport request of the subset leads to a component mismatch situation, the import of all transports is blocked.


To resolve the mismatch issue see SAP Note [1688610](https://me.sap.com/notes/1688610).

</td>
</tr>
</table>

