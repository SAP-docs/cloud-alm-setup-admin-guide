<!-- loio730ae36cc6ca419aae747012015cc686 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP Cloud Transport Management Service

By enabling the transport management for the SAP Cloud Transport Management service, you can orchestrate the deployment of transport requests through your implementation landscape.

SAP Cloud Transport Management is automatically subscribed in your SAP Cloud ALM BTP subaccount. Only this subscription can be used for the integration with SAP Cloud ALM.

To use the transport capabilities of SAP Cloud ALM in conjunction with the SAP Cloud Transport Management service, you first have to establish a connection between them.

> ### Note:  
> SAP Cloud ALM supports the parallel delivery of several nodes at once.
> 
> Before you can use the deployment functionality in SAP Cloud ALM, you have to configure the nodes in the SAP Cloud Transport Management service.



<a name="loio730ae36cc6ca419aae747012015cc686__section_rgk_qjh_nsb"/>

## Prerequisites

-   You've set up the product \(for example, SAP Integration Suite\) with which you want to integrate the SAP Cloud Transport Management service for SAP Cloud ALM.

    For more information about the general setup, refer to [Initial Setup of SAP Cloud Integration in the Cloud Foundry Environment](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/302b47b11e1749c3aa9478f4123fc216.html).

-   You've familiarized yourself with how to use the [SAP Business Technology Platform \(SAP BTP\)](https://help.sap.com/viewer/product/BTP/Cloud/en-US?task=discover_task) cockpit, in particular [Account Administration](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/5d62ec89de39442f8f31d527855cbced.html) concepts.

-   You're subscribed to the SAP Cloud Transport Management service and your user has the required transport management roles *Transport Management Viewer* and *Transport Management Operator*.




<a name="loio730ae36cc6ca419aae747012015cc686__section_i5k_rjh_nsb"/>

## Procedure

1.  **Set Up the Product**

    Set up the specific use case according to the respective documentation, for example [Enabling Content Transport, Cloud Foundry Environment](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/452c677debfc4fda904310560ab03743.html?version=Cloud).

2.  **Set Up an SAP Cloud ALM API Instance**

    Set up the SAP Cloud ALM API instance and the Change and Deployment display and the scope management by performing the steps described in [Enabling SAP Cloud ALM API](enabling-sap-cloud-alm-api-704b5dc.md).

3.  **Set Up HTTP Destinations and Transport Routes with SAP Cloud ALM Pass-Through**

    > ### Note:  
    > The following steps apply only to the SAP Integration Suite. For other integrations, refer to the relevant documentation.

    The product requires a destination to the SAP Cloud Transport Management service. In the SAP BTP subaccount where your source product tenant is hosted, create a destination targeted at the SAP Cloud Transport Management service.

    In the *Destination Configuration* section, enter the values in the respective fields based on the description that is provided in the following table:

    **Destination Configuration Values**


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    `TransportManagementService` \(this value is case-sensitive\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description \(optional\)
    
    </td>
    <td valign="top">
    
    You can provide a description for your reference.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    Enter the URL \(“Api”\) of the service key of your SAP Cloud ALM API instance and append `/imp-cdm-transport-management-api/v1`. That follows a pattern like this: https://eu10.alm.cloud.sap/api/imp-cdm-transport-management-api/v1
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    `OAuth2ClientCredentials` 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    `clientid` from the service key of your SAP Cloud ALM API instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    `clientsecret` from the service key of your SAP Cloud ALM API instance.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Enter the value of the url \(uaa section\) from the service key of your SAP Cloud ALM API instance. Append /oauth/token at the end of URL fetched from the service key.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Additional Properties
    
    </td>
    <td valign="top">
    
    Choose New Property.

    Enter `sourceSystemId` \(this value is case-sensitive\) as the key and provide a value of your choice. Reuse the same value as the name of the source transport node in a later step.
    
    </td>
    </tr>
    </table>
    
    Additional information about how to set up the HTTP destination, please have a look at the following information: [Creating HTTP Destinations and Transport Route](https://help.sap.com/docs/CLOUD_INTEGRATION/368c481cd6954bdfa5d0435479fd4eaf/270f353a5b69472696617d91ceb58c93.html) Go to the *Cloud Transport Management* tab.

    In the URL section for the endpoint, enter the URL of your SAP Cloud ALM API instance that follows the pattern `https://<tenant name>.<region>.alm.cloud.sap/api/imp-cdm-transport-management-api/v1`. The first part of the URL until `/api` depends on your company account and is variable.

    ![](images/HTTP_BTP_V3_da83c89.png)




<a name="loio730ae36cc6ca419aae747012015cc686__section_q2l_2lk_lzb"/>

## Reporting Incidents

If you encounter issues while using this app, open <span class="SAP-icons"></span> \(Built-In Support\) to find helpful resources and context-sensitive information, and to chat with SAP experts. You can also book a live session with the [Schedule an Expert](https://me.sap.com/app/sae) function in SAP for Me.

Create incidents for the *Features* app in [SAP for Me](https://me.sap.com/app/casecreate), under component `SV-CLM-IMP-FTR` .

