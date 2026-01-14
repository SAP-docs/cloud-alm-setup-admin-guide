<!-- loio1d0bd4335bd749f4aff17b7eeb7666e6 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Ariba Sourcing

This document provides guidance on connecting SAP Ariba Sourcing to SAP Cloud ALM for monitoring purposes.

Currently, SAP Ariba Sourcing supports the following monitoring applications:

-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



<a name="loio1d0bd4335bd749f4aff17b7eeb7666e6__section_crb_4p4_tgc"/>

## Setup in SAP Ariba



### 1. Identify the Region of Your Tenant for SAP Ariba Sourcing

To collect messages from SAP Ariba, you need to be onboarded to the SAP Ariba Developer Portal. In this portal, a client application is created, allowing you to collect information on SAP Ariba messages.

The event database of Integration Monitoring in SAP Cloud ALM can only be accessed by a client application that has been created in the SAP Ariba Developer Portal for its region.

To check in which region your SAP Ariba Sourcing and SAP Ariba Procurement tenants are hosted, perform the following steps:

1.  In SAP Cloud ALM, go to *Administration* \> *Landscape Management*.
2.  Find your cloud service you want to set up.
3.  Choose the service name.
4.  Go to the *Properties* tab.
5.  Find the value for *Data Center Location*.



### 2. Access SAP Ariba Developer Portal

As an SAP Ariba customer, you probably have at least one person in your organization with access to the SAP Ariba Developer Portal. If no one in your company has access, or your company does not yet have an organization in the SAP Ariba Developer Portal, please follow the FAQ [How do I create a new organization in API Developer Portal](https://support.ariba.com/item/view/184029).

After the organization is created, your realms will be loaded automatically.



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



### Important URLs

The following table contains the data centers with the respective SAP Ariba API URLs and SAP Ariba OAuth URLs:


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
<tr>
<td valign="top">

EU PROD

</td>
<td valign="top">

[https://eu.developer.ariba.com/api/\(opens in new tab\)](https://eu.developer.ariba.com/api/)

</td>
<td valign="top">

https://eu.openapi.ariba.com/

</td>
<td valign="top">

https://api-eu.ariba.com/

</td>
</tr>
<tr>
<td valign="top">

CN PROD

</td>
<td valign="top">

[https://developer.sapariba.cn/api/\(opens in new tab\)](https://developer.sapariba.cn/api/)

</td>
<td valign="top">

https://openapi.sapariba.cn/

</td>
<td valign="top">

https://api.sapariba.cn/

</td>
</tr>
<tr>
<td valign="top">

UAE PROD

</td>
<td valign="top">

[https://mn1.developer.ariba.com/api/\(opens in new tab\)](https://mn1.developer.ariba.com/api/)

</td>
<td valign="top">

https://mn1.openapi.ariba.com/

</td>
<td valign="top">

https://api.mn1.ariba.com/

</td>
</tr>
<tr>
<td valign="top">

KSA PROD

</td>
<td valign="top">

[https://mn2.developer.ariba.com/api/](https://mn2.developer.ariba.com/api/)

</td>
<td valign="top">

https://mn2.openapi.ariba.com/

</td>
<td valign="top">

https://api.mn2.ariba.com/

</td>
</tr>
<tr>
<td valign="top">

AU PROD

</td>
<td valign="top">

[https://developer.au.cloud.ariba.com/api/](https://developer.au.cloud.ariba.com/api/)

</td>
<td valign="top">

https://openapi.au.cloud.ariba.com/

</td>
<td valign="top">

https://api.au.cloud.ariba.com/

</td>
</tr>
<tr>
<td valign="top">

JP PROD

</td>
<td valign="top">

[https://developer.jp.cloud.ariba.com/api/\(opens in new tab\)](https://developer.jp.cloud.ariba.com/api/)

</td>
<td valign="top">

https://openapi.jp.cloud.ariba.com/

</td>
<td valign="top">

https://api.jp.cloud.ariba.com/

</td>
</tr>
</table>

After finishing all steps, you should have the following information available for the next steps in SAP Cloud ALM:

-   SAP Ariba API URL
-   SAP Ariba OAuth URL
-   OAuth client ID
-   OAuth secret
-   Application key



<a name="loio1d0bd4335bd749f4aff17b7eeb7666e6__section_tpp_bw4_tgc"/>

## Setup in SAP Cloud ALM

Now you need to create the endpoint in SAP Cloud ALM, tenant, to enable data collection.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  *Root URL*: Replace the automatically filled value with the SAP Ariba API URL.
7.  Choose *OAuth authentication* and enter the OAuth credentials retrieved from the SAP Ariba Developer Portal:
    -   *Client ID*: OAuth client ID
    -   *Client Secret*: OAuth secret
    -   *Token Service URL*: Extend your SAP Ariba OAuth URL with `/v2/oauth/token`

8.  Choose *OAuth authentication* and enter the OAuth credentials retrieved from the SAP Ariba Developer Portal:
    -   *Client ID*: OAuth client ID
    -   *Client Secret*: OAuth secret
    -   *Token Service URL*: Extend your SAP Ariba OAuth URL with `/v2/oauth/token`
    -   *API Key*: Enter the application key

9.  Save your endpoint.



### Next Steps

After creating the endpoint in SAP Cloud ALM, perform the following steps to activate the monitoring use cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

