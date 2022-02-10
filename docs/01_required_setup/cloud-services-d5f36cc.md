<!-- loiod5f36cc72b4443f6abfa95f6e1a17782 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Cloud Services



Cloud service information is imported or created as follows:

-   Automatic import by SAP \(preferred option\)

-   Automatic creation by means of the service registration \(available for push-enabled cloud services\)

-   Manual creation \(only if required\)




<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_x25_tz4_n4b"/>

## Procedure



### Automatic Import by SAP

Cloud services are imported automatically on a daily basis. To display the current status, click the first icon after *Status of My Subscribed SAP Services* in the page *Cloud Services*.

If you don't want to wait for the daily import, you can import your cloud services on demand in the *Status of Imports* popover by choosing *Import My Subscribed SAP Services*.

As a global ultimate customer \(i.e. a customer managing SAP cloud products that are subscribed under multiple customer accounts, e.g. after an acquisition\) you need to enter the S-user that has the authorizations for all other S-users to ensure that the landscape management app has access to the data. Perform the following steps:

1.  Choose <span style="font-size:16px;"><span class="SAP-icons"></span></span> \(Configuration\) at the top-right corner on the *Cloud Services* page.

2.  Add the S-user that has the required authorizations to access the data of all other S-users by choosing <span class="SAP-icons"></span> \(Add S-User\).

3.  Enter the S-user ID and the password.

4.  Save your entry.




### Automatic Creation by Means of the Service Registration

There are push-enabled cloud services that register themselves in SAP Cloud ALM \(for example, SAP SuccessFactors and SAP S/4HANA Cloud\). These cloud services are created automatically in the SAP Cloud ALM landscape management app as part of the communication arrangement or registration. If the cloud services already exist in the app, the technical details are updated automatically.



### Manual Creation \(Only If Required\)

If required, the service information can be created manually by choosing *Add* on the *Cloud Services* page in the SAP Cloud ALM landscape management app.

This applies to the cloud service type `Unspecific Cloud Service (HTTP)`.

1.  Enter the following parameters:

    -   *Name*: Enter a name for the new cloud service.

    -   *Description*: Optional, no entry required.

    -   *Tenant ID*: Enter the system number that is available in the [System Data](https://launchpad.support.sap.com/#/systemdata) application on SAP ONE Support Launchpad. The tenant ID is a unique identifier or alias for the tenant and is based on the tenant name.

    -   *Cloud Service Type*: Select a cloud service type in the dropdown list.

    -   *Tenant Type*: Select a tenant type in the dropdown list.

    -   *Root URL*: Enter the URL that needs to be used to access the API.

    -   *External ID*: Optional, no entry required.

    -   *Customer Number*: Optional, no entry required.

    -   *Customer Name*: Optional, no entry required.


2.  Save the new cloud service. You can now see it in the list.


> ### Note:  
> The automatic import by SAP is the preferred way to import service information for cloud services. However, you can also manually add any additional cloud services that you're using if required \(for example, cloud services of the type `Unspecific Cloud Service (HTTP)`\).



<a name="loiod5f36cc72b4443f6abfa95f6e1a17782__section_b4p_rvs_1pb"/>

## Endpoint Creation

An endpoint creation in the landscape management app is only required for specific cloud service types, which cannot pull data from the cloud service by default. If cloud service data is already pushed from the cloud service to the landscape management app, an endpoint creation is not required but optional. For more information about which cloud service types require an endpoint creation and respective endpoint instructions, refer to the cloud service types in the *Setup* section on [Integration & Exception Monitoring – Details \(SAP Cloud ALM for Operations – Expert Portal\)](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/int-mon-setup-support.html).

To add an endpoint for a cloud service, proceed as follows:

1.  On the *Cloud Services* page, choose the name of a cloud service.

2.  Under *Endpoints*, choose *Add* and enter the following parameters:

    -   *Endpoint Name*: Default, no entry required.

    -   *Description*: Optional, no entry required.

    -   *Use Case*: Select ***Landscape Management***.

    -   *Root URL*: Default, no entry required.

    -   *Connection Test Path*: Default, no entry required.

    -   *Authentication Type*: The default entry is ***Basic Authentication***. This parameter specifies the security protocol that is used to send your login details to the server to establish a network connection. SAP Cloud ALM supports the authentication types ***Basic Authentication*** and ***OAuth2ClientCredentials***.

    -   *User*: Enter the ID of the technical communication user.

        > ### Note:  
        > Technical communication users are different from S-users. The technical communication user is a type of technical user for remote system connections for the managed cloud service.

    -   *Password*: Enter your technical communication user password.


    **For the authentication type ***OAuth2ClientCredentials***,** the endpoint configuration under *Authentication* differs. Enter the following parameters:

    -   *Authentication Type*: Select ***OAuth2ClientCredentials***.

    -   *Client ID*: Enter the client ID. This parameter is a public identifier of the target application.

    -   *Client Secret*: Enter the client secret. This parameter is only known to the target application and the authorization server. It's sensitive data, which is stored safely by the SAP Cloud ALM landscape management app.

    -   *Token Service URL*: Enter the token service URL. This parameter is an endpoint that is used to authenticate the *Client ID* and the *Client Secret*. The authentication is performed by using an HTTP POST request with the *Client ID* and the *Client Secret*, which retrieves a JSON Web Token.

    -   *Token Service User*: Optional, no entry required.

    -   *Token Service Password*: Optional, no entry required.


    **For the cloud service types Ariba Network, SAP Ariba Procurement, and SAP Ariba Sourcing,** the additional parameter *API Key* is required:

    -   *API Key*: Enter the API key. This parameter is a code that is provided by computer applications. The program or application calls the API or application programming interface to identify its user, developer, or calling program to a service.


3.  Choose *Check Connection* to verify if the entered user and password are correct.

    If the connection fails, please double-check if the user and password have been entered correctly.

4.  Save.

    To differentiate between parts of your company, you may need several technical communication users for your customer numbers. If several technical communication users are required, create an endpoint for each communication user.


