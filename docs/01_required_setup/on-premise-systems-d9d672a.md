<!-- loiod9d672a2e8944067af5a914cf1e22d82 -->

# On-Premise Systems



On-premise systems \(that is, technical systems\) can be registered or added manually as follows:

-   System registration \(available for push-enabled on-premise systems\)

-   Manual creation \(only if required\)




<a name="loiod9d672a2e8944067af5a914cf1e22d82__section_x1n_h1p_n4b"/>

## Procedure



### System Registration \(Available for Push-Enabled On-Premise Systems\)

To register on-premise systems, run the ABAP report program `/SDF/ALM_SETUP`. For more information, see [Setup Steps in the SAP ABAP On-Premise System](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/setup-managed-services/setup-abap.html).

Once the registration in the ABAP on-premise system has been completed, the registered system is automatically displayed as technical system on the *On-Premise Systems* page. Once a technical system has been registered, a default logical system \(client\) is created and displayed on the *Technical Systems* configuration page. If you want to create a logical system for two clients, run the ABAP report program from both clients.



### Manual Creation \(Only If Required\)

If required, on-premise systems can be created manually in the SAP Cloud ALM landscape management app. Note that the system registration is the recommended way to set up on-premise systems in the SAP Cloud ALM landscape management app.

Perform the following steps:

1.  On the SAP Cloud ALM launchpad, start the *Landscape Management* app.

2.  On the *On-Premise Systems* page, choose *Add*.

3.  To add a technical system, enter the following parameters:

    -   *System ID*: Enter the system ID of the ABAP system \(three-character string\).

    -   *Description*: Optional, no entry required.

    -   *Product*: Select a product in the dropdown list.

    -   *Role*: Select a role in the dropdown list.

    -   *System Type*: Default, no entry required.

    -   *Client*: Enter the default productive client.

    -   *Virtual Host and Port*: Enter the URL to access the on-premise system \(that is, the virtual host and port of the cloud connector\).

    -   *System Number*: Enter the system number that is available in the [System Data](https://launchpad.support.sap.com/#/systemdata) application on SAP ONE Support Launchpad.

    -   *Installation Number*: Enter the installation number that is available in the [System Data](https://launchpad.support.sap.com/#/systemdata) application on SAP ONE Support Launchpad. Alternatively, you can find the installation number in the ABAP system by clicking *Status* in the system menu.

    -   *Customer Number*: Optional, no entry required.

    -   *Customer Name*: Optional, no entry required.


4.  Save the new technical system. You can now see it in the list.

5.  To add logical systems, choose the name of the new technical system.

6.  Under *Logical Systems*, choose *Add* and enter the following parameters.

    -   *Client*: Enter the ABAP client.

    -   *Description*: Optional, no entry required.

    -   *Role*: Select a role in the dropdown list.


7.  Save the new logical system. You can now see it in the list.

8.  To add endpoints, choose the client name of the new logical system.

    Please note that the endpoint configuration for SAP Focused Run and SAP Solution Manager differs.

9.  Under *Endpoints*, choose *Add* and proceed as follows:

    **For SAP Focused Run**, enter the following parameters:

    -   *Customer Network*: The data centers and logical networks, as defined and operated by the network team, shall be declared within SAP Focused Run. These network segments, named *Customer Networks*, are used by the landscape management database \(LMDB\) as namespaces, to bundle and protect system definitions and collected metrics. This is reflected, for example, in the schema with A and B in [Preparing Customer Network \(SAP Support Portal\)](https://support.sap.com/en/alm/sap-focused-run/expert-portal/managed-systems-maintenance-guide/preparing-customer-network.html#section). Such a customer network can then also be assigned to a customer \(via so called *Business Partners*\).

    -   *Admin Request Parameter*: It is also called *inbound fencing string*, which is usually the hostname of the *Reverse Proxy*. Note that it is mandatory that this same value is also manually maintained in the reverse proxy configuration file. For more information, see [Preparing Customer Network \(SAP Support Portal\)](https://support.sap.com/en/alm/sap-focused-run/expert-portal/managed-systems-maintenance-guide/preparing-customer-network.html#section).

    -   *Description*: Optional, no entry required.

    -   *Virtual Host and Port*: Enter the host of the cloud connector.

    -   *Connection Test Path*: Default, no entry required.

    -   *Authentication Type*: The default entry is ***Basic Authentication***. This parameter specifies the security protocol that is used to send your login details to the server to establish a network connection. SAP Cloud ALM supports the authentication types ***Basic Authentication*** and ***OAuth2ClientCredentials***.

    -   *User*: Enter the ID of the technical communication user.

        > ### Note:  
        > The technical communication user is a type of technical user for remote system connections for the managed ABAP system.

    -   *Password*: Enter your technical communication user password.


    **For the authentication type ***OAuth2ClientCredentials***,** the endpoint configuration under *Authentication* differs. Enter the following parameters:

    -   *Authentication Type*: Select ***OAuth2ClientCredentials***.

    -   *Client ID*: Enter the client ID. This parameter is a public identifier of the target application.

    -   *Client Secret*: Enter the client secret. This parameter is only known to the target application and the authorization server. It's sensitive data, which is stored safely by the SAP Cloud ALM landscape management app.

    -   *Token Service URL*: Enter the token service URL. This parameter is an endpoint that is used to authenticate the *Client ID* and the *Client Secret*. The authentication is performed by using an HTTP POST request with the *Client ID* and the *Client Secret*, which retrieves a JSON Web Token.

    -   *Token Service User*: Optional, no entry required.

    -   *Token Service Password*: Optional, no entry required.


    **For SAP Solution Manager**, enter the following parameters:

    -   *Endpoint Name*: default, no entry required.

    -   *Description*: Optional, no entry required.

    -   *Virtual Host and Port*: Enter the host of the cloud connector.

    -   *Connection Test Path*: Default, no entry required.

    -   *Authentication Type*: The default entry is ***Basic Authentication***. This parameter specifies the security protocol that is used to send your login details to the server to establish a network connection. SAP Cloud ALM supports the authentication types ***Basic Authentication*** and ***OAuth2ClientCredentials***.

    -   *User*: Enter the ID of the technical communication user.

        > ### Note:  
        > The technical communication user is a type of technical user for remote system connections for the managed ABAP system.

    -   *Password*: Enter your technical communication user password.


    **For the authentication type ***OAuth2ClientCredentials***,** the endpoint configuration under *Authentication* differs. Enter the following parameters:

    -   *Authentication Type*: Select ***OAuth2ClientCredentials***.

    -   *Client ID*: Enter the client ID. This parameter is a public identifier of the target application.

    -   *Client Secret*: Enter the client secret. This parameter is only known to the target application and the authorization server. It's sensitive data, which is stored safely by the SAP Cloud ALM landscape management app.

    -   *Token Service URL*: Enter the token service URL. This parameter is an endpoint that is used to authenticate the *Client ID* and the *Client Secret*. The authentication is performed by using an HTTP POST request with the *Client ID* and the *Client Secret*, which retrieves a JSON Web Token.

    -   *Token Service User*: Optional, no entry required.

    -   *Token Service Password*: Optional, no entry required.


10. Save.


Once a technical system has been added manually, a default logical system is created and displayed on the *Technical Systems* configuration page.

