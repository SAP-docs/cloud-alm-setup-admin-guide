<!-- loio93ae080ec391461bb4d56579deaa0b00 -->

# Solutions for Errors in the Managed System Setup Check

**Managed System Setup Check Report**

In the list below, you find messages that can appear in the managed system during the Managed System Setup Check. This includes both confirmation information and error messages. In the second column *Message Explanation*, you can find more information about the message. In case of error messages, you can find information about how to resolve the errors.



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_j3d_qfj_31c"/>

## Batch Job Check

The batch job check that a job for the program `/SDF/CALM_SCHEDULER` is scheduled.

The `/SDF/CALM_SCHEDULER` program is the central scheduling mechanism for all active use cases. The frequency of the scheduling determines the overall interval between the use-case executions.

The batch job check that a job for the program `/SDF/CALM_CDM_DIAGNOSTICS` is scheduled and did run today.

-   This program informs SAP Cloud ALM about the capabilities of the system according to the installed ST-PI service level and certain notes \(For example: Transport creation, release, ToC, and so on\).
-   It runs once after the use-case activation and then once daily. Check transaction `/SDF/ALM_SETUP` that at least one transport-related use-case is active.

**Batch Job Check**


<table>
<tr>
<th valign="top">

Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

Job `&1` is scheduled. Next run: `&2 &3`

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

Job `&1` isn't scheduled

</td>
<td valign="top">

Procedure: Check transaction `/SDF/ALM_SETUP` whether the background user is configured, and the system is registered.

If this isn't the case, press the *Register* button again.

</td>
</tr>
<tr>
<td valign="top">

Error in configuration: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
<tr>
<td valign="top">

Job `/SDF/CALM_CDM_DIAGNOSTICS` did run today

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

Job `/SDF/CALM_CDM_DIAGNOSTICS` hasn't \(yet\) run today

</td>
<td valign="top">

-   Check that no obsolete jobs for this program exist in SM37 \(for example, after suspending all jobs\).
-   Check transaction `/SDF/ALM_SETUP` that at least one transport-related use-case is active.



</td>
</tr>
</table>

For more information about the basic setup and use cases refer to the following documentation:

[**SAP S/4HANA Cloud Private Edition and On-Premise Systems Setup Procedure**](https://help.sap.com/docs/cloud-alm/setup-administration/change-transport-system?locale=en-US#procedure).



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_k3d_qfj_31c"/>

## Background Work Processes \(BTC\) Workers

Free batch processes are necessary to start use-case processing. If all worker processes are blocked by other tasks no information from Cloud ALM is transferred and no Cloud ALM tasks processed.

**Background Work Processes \(BTC\) Workers**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

There are currently no free batch processes

</td>
<td valign="top">

Follow the instructions in [39412](https://me.sap.com/notes/39412).

</td>
</tr>
<tr>
<td valign="top">

There's only one free batch process

</td>
<td valign="top">

Follow the instructions in [39412](https://me.sap.com/notes/39412).

</td>
</tr>
<tr>
<td valign="top">

There are currently `&1` free batch processes

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

Error reading batch process data: `&1`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_l3d_qfj_31c"/>

## Certificate Check

For the connection to SAP Cloud ALM, the certificates must be installed into the system. See [Setup S-Trust](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html).

**Certificate Check**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

Certificate exists: `&1`

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

Certificate missing: `&1`

</td>
<td valign="top">

Follow the instructions in [**Setup STRUST**.](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html)

</td>
</tr>
<tr>
<td valign="top">

Certificate recommended: `&1`

</td>
<td valign="top">

Follow the instructions in [**Setup STRUST**.](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap/setup-strust.html)

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_m3d_qfj_31c"/>

## Connection Check

In case of connection issues check if you followed all the steps from the [**SAP S/4HANA Cloud Private Edition and On-Premise Systems**](https://help.sap.com/docs/cloud-alm/setup-administration/change-transport-system?locale=en-US) guide.

Common connection problems that occur are for example `HTTP Code 403`:

-   Cloud API Key or Binding wasn't set up with the necessary scopes. For more information, see [Token Scopes Check](https://help.sap.com/docs/cloud-alm/setup-administration/solutions-setup-check?locale=en-US#token-scopes-check) 
-   Necessary certificates are missing. For more information, see [Certificate Check](https://help.sap.com/docs/cloud-alm/setup-administration/solutions-setup-check?locale=en-US#certificate-check).

**Connection Check**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

Connection successful

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

Connection failed: `&1`

</td>
<td valign="top">

See common connection problems above the table.

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_n3d_qfj_31c"/>

## Lock Check \(SM12\)

Certain locks might prevent use-case processing. For example, a lock is still present even though use-case execution is paused.

For more information, see [43614](https://me.sap.com/notes/43614).

**Lock Check \(SM12\)**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

No locks are blocking use-case execution

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

At least one `SM12` lock found for `/SDF/CALM_SCHED`

</td>
<td valign="top">

For more information, see [43614](https://me.sap.com/notes/43614).

</td>
</tr>
<tr>
<td valign="top">

At least one `SM12` lock for `/SDF/CALM_SCHED` older than 10 minutes found

</td>
<td valign="top">

For more information, see [43614](https://me.sap.com/notes/43614).

</td>
</tr>
<tr>
<td valign="top">

Error during lock retrieval: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_o3d_qfj_31c"/>

## Note Implementation

Check the latest version of the SAP Cloud ALM CDM master note [3425282](https://me.sap.com/notes/3425282) is implemented.

**Note Implementation**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

Error during note download: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
<tr>
<td valign="top">

The latest version of SAP Note [3322679](https://me.sap.com/notes/3322679) is implemented

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

An older note version is implemented: `&1`

</td>
<td valign="top">

It's recommended to update the master note and/or ST-PI regularly to receive new functions and bugfixes.

</td>
</tr>
<tr>
<td valign="top">

Error during note check: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_p3d_qfj_31c"/>

## Token Scopes Check

The Cloud API Key or binding wasn't set up with the necessary scopes. If you're unsure about if you performed these steps correctly, create a new dedicated API instance according to the documentation you can find in [**Enabling SAP Cloud ALM API**](https://help.sap.com/docs/cloud-alm/setup-administration/enabling-sap-cloud-alm-api?locale=en-US).

After you've performed the setup correctly, repeat the setup with the new API key. If this doesn't work either, please consult

**Token Scopes Check**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

Token Connection failed: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
<tr>
<td valign="top">

Token scope `imp-cdm-feature-display-ui` missing

</td>
<td valign="top">

Check if you followed the steps in [**Enabling SAP Cloud ALM API**](https://help.sap.com/docs/cloud-alm/setup-administration/enabling-sap-cloud-alm-api?locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

Token scope `imp-cdm-feature-manage-ui` missing

</td>
<td valign="top">

Check if you followed the steps in [**Enabling SAP Cloud ALM API**](https://help.sap.com/docs/cloud-alm/setup-administration/enabling-sap-cloud-alm-api?locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

Token scopes valid

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_q3d_qfj_31c"/>

## Solution Tools Plug-In \(ST-PI\)

We recommend to regularly install a recent version of the ST-PI plugin instead of various master page notes. See also [539977](https://me.sap.com/notes/539977). Also, refer to the following guide [**Technical Prerequisites**.](https://help.sap.com/docs/cloud-alm/setup-administration/change-transport-system?locale=en-US#technical-prerequisites)

**Solution Tools Plug-In \(ST-PI\)**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

A recent version of ST-PI is implemented: `&1`

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

An older version of ST-PI is implemented: `&1`

</td>
<td valign="top">

Upgrade your ST-PI version to a more recent version.

</td>
</tr>
<tr>
<td valign="top">

The installed version of ST-PI is outdated: `&1`

</td>
<td valign="top">

It's highly recommended to update the ST-PI version.

</td>
</tr>
<tr>
<td valign="top">

Error during component check: `&1&2&3&4`

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_r3d_qfj_31c"/>

## Web Dynpro Check

This check whether the new `S_START` check is active for the `CTS_ORGANIZER` *Web Dynpro* app.

To display transports `S_TRANSPRT` display authorization must be assigned to the users.

**Web Dynpro Check**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

`S_START` check is active for CTS\_ORGANIZER

</td>
<td valign="top">

Information message. For background information, see SAP Note [1413011](https://me.sap.com/notes/1413011).

</td>
</tr>
<tr>
<td valign="top">

`S_START` authorization is assigned to current user

</td>
<td valign="top">

Information message. For background information, see SAP Note [1413011](https://me.sap.com/notes/1413011) .

</td>
</tr>
<tr>
<td valign="top">

`S_START` authorization missing for `CTS_ORGANIZER` for current user

</td>
<td valign="top">

Ensure that every user who wants to navigate from CALM to a transport request has the necessary authorization in the respective client of the managed system. Usually, this is not necessary for client 000, as it is not recommended to create transports in this client.

For more information, see SAP Note [1413011](https://me.sap.com/notes/1413011).

</td>
</tr>
<tr>
<td valign="top">

`S_START` check is inactive for `CTS_ORGANIZER`

</td>
<td valign="top">

Information message. For background information, see SAP Note [1413011](https://me.sap.com/notes/1413011).

</td>
</tr>
<tr>
<td valign="top">

`S_TRANSPRT` display authorization is assigned to current user

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

`S_TRANSPRT` display authorization missing for current user

</td>
<td valign="top">

Follow the information in [**Authorizations for Transport Organizer Web UI \(CTS\_ORGANIZER\)**](https://help.sap.com/doc/saphelp_nw73ehp1/7.31.19/en-US/0d/fc42c2a8ef499b8f8bc74bbd2df01a/content.htm?no_cache=true) to resolve the issue.

</td>
</tr>
</table>



<a name="loio93ae080ec391461bb4d56579deaa0b00__section_s3d_qfj_31c"/>

## Change and Transport System \(CTS\) Check

We check the Change and Transport System for basic functionality. For more detailed information, refer to transaction `STMS`. We recommend enabling `CTC`.

**Change and Transport System \(CTS\) System Check**


<table>
<tr>
<th valign="top">

Error Message

</th>
<th valign="top">

Message Explanation

</th>
</tr>
<tr>
<td valign="top">

`&1`: CTC is enabled

</td>
<td valign="top">

Confirmation message. No action is needed.

</td>
</tr>
<tr>
<td valign="top">

`&1`: CTC is disabled

</td>
<td valign="top">

It's recommended to enable CTC. Follow the instructions in [**Extended Transport Control**](https://help.sap.com/docs/ABAP_PLATFORM_NEW/4a368c163b08418890a406d413933ba7/1b9dc2d6e59911d184810000e8a57770.html?locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

`&1`: &2&3

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
<tr>
<td valign="top">

`&1`: System Profile couldn't be read

</td>
<td valign="top">

No immediate solution is available. Search for similar issues with the SAP4Me help search or open a ticket at [SAP For Me](https://me.sap.com/getassistance/overview).

</td>
</tr>
</table>

