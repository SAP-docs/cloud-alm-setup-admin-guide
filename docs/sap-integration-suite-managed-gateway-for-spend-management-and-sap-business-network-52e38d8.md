<!-- loio52e38d868c604bcabcd863f447b3effb -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Integration Suite, managed gateway for spend management and SAP Business Network

This document provides guidance on connecting SAP Integration Suite, managed gateway for spend management and SAP Business Network to SAP Cloud ALM for monitoring purposes.

Note that the name "SAP Integration Suite, managed gateway for spend management and SAP Business Network" replaced the name SAP Integration Suite, managed gateway, which itself replaced SAP Ariba Cloud Integration Gateway.

For simplicity, the landscape management refers to it as *Managed Gateway for Spend & Network*.

Currently, Managed Gateway for Spend&Network supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Setup in Managed Gateway for Spend & Network

Managed Gateway for Spend & Network writes its status messages in the Integration Monitoring event database. From there, you can collect it from SAP Cloud ALM, using a client application.

The event database of Integration Monitoring is accessible only by a client application created in the SAP Ariba Developer Portal for its region. For this purpose, you need to create the client application in the SAP Ariba Developer Portal.

The first step is to identify the region where your Managed Gateway for Spend & Network is activated.



### 1. Identify the Region of Managed Gateway for Spend & Network

Case 1 - for Procurement Customers:

1.  Log on to SAP Business Network for Procurement with an administrator account.
2.  Choose your profile in the upper right corner.
3.  Navigate to *Settings* \> *Electronic Order Routing*.
4.  Choose the link *Configure SAP Integration Suite, managed gateway for spend management and SAP Business Network \(non-native integration\)*.
5.  Verify that the checkbox in front of *Enable Managed Gateway for Spend & Network* is checked.
6.  The box next to *Data center* shows the region where Managed Gateway for Spend & Network is activated.

Case B - for SAP Ariba Procurement or Sourcing Customers:

1.  Log on to SAP Ariba Sourcing or Procurement with an administrator account.
2.  Navigate to *Manage* \> *Core Administration*.
3.  Go to *Integration Manager* \> *Managed Gateway for Spend & Network*.
4.  In the next screen, verify that the status is set to *Enabled*.
5.  Next to the *Data Center* label, you find the data center where Managed Gateway for Spend & Network is activated.



### 2. Create Client Application

Do you need to create a new client application for Managed Gateway for Spend & Network? Depending on your configuration for Managed Gateway for Spend & Network, you can reuse the client application you already created for your leading SAP Ariba Product, such as SAP Business Network for Procurement, SAP Ariba Sourcing, or SAP Ariba Procurement.

Please consult the following table to learn if you can reuse an existing client application. Work through the table from left to right, always choosing the option that applies to you.

If you can reuse the client application, please proceed directly to the section *Setup in SAP Cloud ALM*.


<table>
<tr>
<th valign="top">

Leading SAP Ariba Product

</th>
<th valign="top">

Location of the leading product

</th>
<th valign="top">

Managed Gateway for Spend & Network Location

</th>
<th valign="top">

Set up requirements for Managed Gateway for Spend&Network

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

SAP Ariba Procurement or SAP Ariba Sourcing

</td>
<td valign="top">

EU

</td>
<td valign="top">

EU

</td>
<td valign="top">

You need to create a client application created for [SAP Business Network for Procurement](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-network.html) in the SAP Ariba Developer Portal \(U.S.\).

</td>
</tr>
<tr>
<td valign="top">

AU or JP

</td>
<td valign="top">

EU

</td>
<td valign="top">

You need to create a client application created for [SAP Business Network for Procurement](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-network.html) in the SAP Ariba Developer Portal \(U.S.\).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

U.S., KSA, UAE, or CN

</td>
<td valign="top">

The same data center as the leading product

</td>
<td valign="top">

You can reuse the client application created for the leading SAP Ariba product \([SAP Ariba Procurement](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-procurement.html), [SAP Ariba Sourcing](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-sourcing.html)\)

</td>
</tr>
<tr>
<td valign="top">

EU

</td>
<td valign="top">

If possible, adjust the configuration for Managed Gateway for Spend&Network, so that its data center is the same as the data center of the leading SAP Ariba Product. Then you can reuse the client application that you created for the leading SAP Ariba product.

If you can't adjust the configuration for Managed Gateway for Spend&Network, you need to create a client application created for [SAP Business Network for Procurement](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-network.html) in the SAP Ariba Developer Portal \(U.S.\).

</td>
</tr>
<tr>
<td valign="top">

SAP Business Network for Procurement

</td>
<td valign="top">

U.S.

</td>
<td valign="top">

U.S. or EU

</td>
<td valign="top">

You can reuse the client application created for [SAP Business Network for Procurement](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-ariba-network.html)

</td>
</tr>
</table>

Due to the SAP Ariba Architecture, all SAP Ariba Cloud Integration Gateway information routes to the U.S. servers, even if your tenant is in the EU or other regions. You need to create the client application for the SAP Business Network for Procurement in the SAP Ariba Developer Portal \(U.S.\) data center.



### 3. Access the SAP Ariba Developer Portal \(U.S.\)

If you're still reading this section \(because you can't reuse any client application\), you need to create a new client application in the [SAP Ariba Developer Portal \(U.S.\)](https://developer.ariba.com/api/). If no one in your company has access to the SAP Ariba Developer Portal \(U.S.\) yet, or your company doesn't have an organization in the SAP Ariba Developer Portal \(U.S.\), please follow the FAQ [How do I create a new organization in API Developer Portal](https://support.ariba.com/item/view/184029).



### 3. Create Client Application in SAP Ariba Developer Portal

Once you have access to the SAP Ariba Developer Portal, proceed as described here:

1.  Log on to the SAP Ariba Developer Portal. You find the correct URL for your data center in the table of section *Important URLs*.
2.  In the navigation pane, choose *Manage*.
3.  On the top of the application list, choose :heavy_plus_sign:.
4.  Enter an application name and a description.
5.  Choose *Submit*.
6.  Choose *Actions* \> *Request API Access*.
7.  Select *API Integration Event Monitoring Query API for Procurement*. This API is used for **all** SAP Ariba applications.
8.  Check the box in front of SAP Ariba application: *Procurement* if you are setting up SAP Ariba for Procurement\) or *Sourcing* if you are setting up SAP Ariba for Sourcing.
9.  Select all realms you want to assign from the drop-down box. You can use the same application for several realms:
    -   The realm is part of the URL you use to access SAP Ariba.

        Example for SAP Ariba Procurement: `https://mycompany.sourcing.ariba.com/`

        Example for SAP Ariba Sourcing: `https://mycompany.sourcing.ariba.com/`

    -   Check the entry for the SAP Ariba tenant in the *Landscape Management* app of SAP Cloud ALM. The realm for SAP Ariba Procurement is also the name of the service in *Landscape Management*.
    -   For security reasons, consider creating separate applications for your test and productive realms, or one dedicated application for each productive realm.

10. Choose *Submit*.
11. Ariba approves the API access request for your client application within 24 hours.
12. Continue with the steps under *Create OAuth Secret for Client Application* after the API access request is approved.



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



### 6. Link API Client ID to AN-ID in SAP Business Network for Procurement

For a client application for SAP Business Network for Procurement, you need to link the API Client ID \(OAuth Client ID\) to the AN-ID in SAP Business Network for Procurement.

> ### Tip:  
> **Prerequisite:** You need to be able to log on to SAP Business Network for Procurement.
> 
> Since you have a valid AN-ID, you also have access to SAP Business Network for Procurement, even if you never used it. At some point in the past, someone in your organization must have registered this AN-ID with SAP Business Network for Procurement. If possible, contact this person to log on to SAP Business Network for Procurement.
> 
> 1.  Go to [https://service.ariba.com](https://service.ariba.com).
> 2.  Select *Buyer*.
> 3.  Enter your username.
> 
>     If you forgot your username, choose *Forgot username* and enter the email address you used to register with SAP Business Network for Procurement.
> 
>     If you don't remember this email address, please open a support ticket via [https://connectsupport.ariba.com](https://connectsupport.ariba.com). They can retrieve the email and username via your AN-ID.

Once you have access to SAP Business Network for Procurement, you can proceed:

1.  After the access to the API has been approved for your client application, log on to SAP Ariba Developer Portal.
2.  Copy the value in the *Oauth Client ID* field.
3.  Log on to SAP Business Network for Procurement.
4.  Choose the *Account Settings* icon and go to *Manage Profile* \> *API Client ID Configuration*.
5.  Choose *Add*.
6.  Enter the OAuth Client ID that you copied earlier in the *Client ID* field.
7.  Save your changes.



### Important URLs

The following table contains the data centers with the respective SAP Ariba API URL and SAP Ariba OAuth URL:


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

U.S. PROD

</td>
<td valign="top">

[https://developer.ariba.com/api](https://developer.ariba.com/api)

</td>
<td valign="top">

https://openapi.ariba.com/

</td>
<td valign="top">

https://api.ariba.com/

</td>
</tr>
</table>

After finishing all steps, you should have the following information available for the next steps in SAP Cloud ALM:

-   SAP Ariba API URL
-   SAP Ariba OAuth URL
-   OAuth client ID
-   OAuth secret
-   Application key



## Setup in SAP Cloud ALM



### 1. Add the Service to the Landscape Management

Now, you can add Managed Gateway for Spend & Network to the Landscape Management app in SAP Cloud ALM.

Currently, Managed Gateway for Spend & Network can't automatically be imported to Landscape Management automatically. You need to create the cloud service manually.

1.  Open the *Landscape Management* application from the launchpad.
2.  Choose *Add* to create a new service.
    -   *Name*: Enter a name for the service.
    -   *System Number*: Enter the AN-ID, realm, or system number of the SAP Ariba tenant to that the Managed Gateway belongs, followed by `-mgsn`.
    -   *Service Type*: Select *Managed Gateway for Spend and Network*.
    -   *Role*: Select the appropriate role from the list.
    -   *Root URL*: Enter your SAP Ariba API URL.
    -   *Location*: Select the location for your Managed Gateway from the drop-down list.
    -   *External ID*: Enter the AN-ID for the SAP Ariba application for which Managed Gateway for Spend and Network was activated.

3.  Save your service.



### 2. Create HTTP Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  *Root URL*: Ensure this is the SAP Ariba API URL.
7.  Choose *OAuth authentication* and enter the OAuth credentials retrieved from the SAP Ariba Developer Portal:
    -   *Client ID*: OAuth client ID
    -   *Client Secret*: OAuth secret
    -   *Token Service URL*: Extend your SAP Ariba OAuth URL with `/v2/oauth/token`
    -   *API Key*: Enter the application key

8.  Save your endpoint.



### Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

