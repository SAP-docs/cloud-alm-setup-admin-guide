<!-- loio1edae0696eeb47339d671f1c93783c47 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Business Network for Procurement \(old: SAP Ariba Network\)

This document provides guidance on connecting SAP Business Network for Procurement to SAP Cloud ALM for monitoring purposes.

Note that the name SAP Business Network for Procurement replaced the name SAP Ariba Network.

Currently, SAP Business Network for Procurement supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Setup for SAP Business Network for Procurement



### 1. Note the Data Center Location

Unlike other SAP Ariba applications, SAP Business Network for Procurement **always** sends its events to the Integration Monitoring event database located in the U.S. data center.

Therefore, you always need to use the [SAP Ariba Developer Portal \(United States\)](https://developer.ariba.com/api/) for your setup.



### 2. Access SAP Ariba Developer Portal

As an SAP Ariba customer, you probably have at least one person in your organization with access to the SAP Ariba Developer Portal. If no one in your company has access, or your company does not yet have an organization in the SAP Ariba Developer Portal, please follow the FAQ [How do I create a new organization in API Developer Portal](https://support.ariba.com/item/view/184029).

After the organization is created, your realms will be loaded automatically.



### 3. Create Client Application in SAP Ariba Developer Portal

1.  Log on to the [SAP Ariba Developer Portal \(United States\)](https://developer.ariba.com/api/).
2.  In the navigation pane, choose *Manage*.
3.  On the top of the application list, choose :heavy_plus_sign:.
4.  Enter an application name and a description.
5.  Choose *Submit*.
6.  Choose *Actions* \> *Request API Access*.
7.  Select *API Integration Event Monitoring Query API for Procurement*. This API is used for **all** SAP Ariba applications.
8.  Check the box in front of *Ariba Network*.

    For security reasons, consider creating separate applications for your test and production realms. You can also create a dedicated application for each production realm.

9.  Choose *Submit*.
10. SAP Ariba approves the API access request for your client application within 24 hours.
11. Continue with the steps under *Create OAuth Secret for Client Application* after the API access request is approved.



### 4. Create OAuth Secret for Client Application

After the API access for the application is approved, go back to the SAP Ariba Developer Portal and generate an OAuth secret for your application:

1.  Log on to the SAP Ariba Developer Portal with a user that has the Organization Admin role.
2.  Choose *Manage* in the left-hand menu.
3.  Find your application for Integration Monitoring under *My Applications* and select it.
4.  The application should now only have the open step *Your admin needs to generate the OAuth Secret for your application*.
5.  Choose *Actions* \> *Generate OAuth Secret*.

    > ### Caution:  
    > Generating a new OAuth secret invalidates any old OAuth secrets.

6.  Choose *Submit*.
7.  Download the file. It contains the Application Key, the OAuth Client ID, and the OAuth Secret.
8.  Find your SAP Ariba API URL and the SAP Ariba OAuth URL in the table under *Important URLs* and save them for later use.



### Link API Client ID to AN-ID in SAP Business Network for Procurement

Link the API Client ID \(OAuth Client ID\) to the AN-ID in SAP Business Network for Procurement.

1.  Log on to the SAP Ariba Developer Portal after the API access is approved for your client application.
2.  Copy the value in the field *Oauth Client ID*.
3.  Log on to SAP Business Network for Procurement.
4.  Choose the *Account Settings* icon and select *Manage Profile* \> *API Client ID Configuration*.
5.  Choose *Add*.
6.  Enter the OAuth Client ID you copied earlier in the *Client ID* field.
7.  Save your changes.



### Important URLs

The following table lists the data centers with the respective SAP Ariba API URL and SAP Ariba OAuth URL:


<table>
<tr>
<th valign="top">

Data Center

</th>
<th valign="top">

SAP Ariba Developer Portal URL

</th>
<th valign="top">

SAP Ariba API URL

</th>
<th valign="top">

SAP Ariba OAuth URL

</th>
</tr>
<tr>
<td valign="top">

US PROD

</td>
<td valign="top">

[https://developer.ariba.com/api/\(opens in new tab\)](https://developer.ariba.com/api/)

</td>
<td valign="top">

https://openapi.ariba.com/

</td>
<td valign="top">

https://api.ariba.com/

</td>
</tr>
</table>

After you complete all steps, you should have the following information available for the next steps in SAP Cloud ALM:

-   SAP Ariba API URL
-   SAP Ariba OAuth URL
-   OAuth client ID
-   OAuth secret
-   Application key



<a name="loio1edae0696eeb47339d671f1c93783c47__section_xjd_r45_5gc"/>

## Setup in SAP Cloud ALM



### Create HTTP Endpoint

Create the endpoint in your SAP Cloud ALM tenant to enable data collection.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  1.  *Root URL*: Replace the automatically filled value with the SAP Ariba API URL.
2.  Choose *OAuth authentication* and enter the OAuth credentials you retrieved from the SAP Ariba Developer Portal:
    -   *Client ID*: OAuth client ID
    -   *Client Secret*: OAuth secret
    -   *Token Service URL*: Extend your SAP Ariba OAuth URL with `/v2/oauth/token`
    -   *API Key*: Enter the application key


7.  Save your endpoint.



## Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

