<!-- loio7f913374869247abae5a3ce78f70a3d5 -->

# SAP SuccessFactors

This page explains how to connect SAP SuccessFactors to SAP Cloud ALM to enable monitoring.

Currently, SAP SuccessFactors supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration & Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)

The following video demonstrates the setup steps for Integration and Exception Monitoring for SAP SuccessFactors. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loio7f913374869247abae5a3ce78f70a3d5__section_thk_xh4_chc"/>

## Prerequisites

-   You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

-   In SAP SuccessFactors, you've got an SFAPI user as described in [SAP SuccessFactors SFAPI User](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/sf-sfapi-user.html).

    To use the SFAPI, SAP SuccessFactors must enable the API for your company instance. This is usually done during the initial implementation. If this wasn't done, contact your SAP SuccessFactors support representative to enable the SFAPI for your instance.

-   In SAP SuccessFactors, your personal user needs the following permissions:
    -   *Manage Integration Tools* \> *Access to Integration Service Registration Center UI*
    -   *Admin Center* \> *Manage Permission Roles* \> *Access to X.509 Certificate Mapping*

-   In SAP Cloud ALM, your personal user needs one of the following roles:
    -   *Landscape Management Security Administrator* \(to create and download a certificate\)
    -   or *Landscape Management Security Viewer* \(to download an existing certificate\)




## Setup in SAP SuccessFactors



### Enable the Monitoring Data PUSH to SAP Cloud ALM

This step is only needed if you use integrations for which messages can be collected. You find supported scenarios in the table under [Available Monitoring Content](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-sf.html).

1.  Go to the *Admin Center*.
2.  Under *Tools Search*, search for *Integration Service Registration Center*.
3.  Select SAP Cloud ALM.
4.  Enter the following values:
    1.  *System Type*: Enter the role of the SAP SuccessFactors system: `DEV`, `TEST`, or `PROD`. Use these specific values instead of other free-form role types.
    2.  *Description*: Enter a description, such as `SAP SuccessFactors tenant XXX`.
    3.  *Endpoint*: SAP Cloud ALM service key parameter `Api` without `/api`.
    4.  *OAuth URL*: SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.
    5.  *Client ID*: SAP Cloud ALM service key parameter `clientid`.
    6.  *Client Secret*: SAP Cloud ALM service key parameter `clientsecret`.

5.  Choose *Register*.
6.  Choose *OK*.

    Note: To deactivate your instance again, you can choose *Deregister*.


The registration creates an entry for your SAP SuccessFactors instance in the *Landscape Management* app of SAP Cloud ALM, if it doesn't exist already.



### Create an HTTP Endpoint

Map theSAP Cloud ALM certificate in SAP SuccessFactors.

To use X.509 certificate-based authentication for incoming calls to SAP SuccessFactors, you first have to map the public certificate of SAP Cloud ALM in SAP SuccessFactors.

1.  In SAP Cloud ALM, open the *Landscape Management* app.
2.  Open the *Configuration*.
3.  In the *Certificates* section, choose *Download* to download the SAP Cloud ALM public certificate.

    If no certificate exists, choose *Generate*:

    1.  Enter a password for the certificate. You need it later, for the endpoint creation.
    2.  Choose *Generate Certificate*.

    To generate a certificate, you need the role *Landscape Management Security Admin*.


Now, upload the certificate needs to SAP SuccessFactors:

1.  In SAP SuccessFactors, go to *Security Center* \> *X.509 Public Certificate Mapping*.
2.  Choose *Add*.
3.  Enter the following values:
    1.  *Configuration Name*: for example, `Cloud ALM Certificate Mapping`.
    2.  *Integration Name*: `Business Technology Platform`.
    3.  *Certificate File*: Upload the certificate `.pem` file that you downloaded from SAP Cloud ALM.
    4.  *Login Name*: Enter the previously created user for the SFAPI.




## Setup in SAP Cloud ALM



### Create the Endpoint for Exception Monitoring

The endpoint is only needed to support the PULL data collection for exceptions.

> ### Note:  
> the PUSH monitoring setup creates an additional cloud service in the *Landscape Management* app.
> 
> -   If you activated the PUSH data collection in the previous step, create the endpoint for this cloud service \(SAP SuccessFactors\).
> -   If you didn't activate the PUSH data collection, create the endpoint for the **SAP SuccessFactors HCM** tenant that was synchronized automatically with the *Landscape Management*.

1.  In SAP Cloud ALM, open the *Landscape Management* app.
2.  Select your SAP SuccessFactors service with the service type *SAP SuccessFactors HCM*.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use-case *Exception Monitoring*.
6.  The root URL is automatically adjusted.
7.  Choose *ClientCertificateAuthentication* and enter:
    -   *Certificate Key Store Location*: Choose the certificate that you uploaded to SAP SuccessFactors.
    -   *Certificate Key Store Password*: Enter the password that you provided when you generated the certificate.

8.  Choose *Connection Check*.
9.  Choose *Save*.

If the endpoint *Root URL* field isn't filled automatically or if you want to still use BASIC authentication, find the correct API URL:

1.  Select your SAP SuccessFactors service with the service type *SAP SuccessFactors HCM*.
2.  Check the value for the field *System ID* in the properties, for example DC33STD or DC57PREV.
3.  Open [List of SAP SuccessFactors API Servers](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/93f95815070049ebaaff042d8322d518/af2b8d5437494b12be88fe374eba75b6.html?locale=en-US) for different data centers.

    If the *System ID* value ends with *STD*, use the API Server for the *Production* environment.

    If the "*System ID* value ends with *PREV*, use the API Server for the *Preview* environment.




### Create the Endpoint for Business Process Monitoring

1.  In SAP Cloud ALM, open the *Landscape Management* app.
2.  Select your SAP SuccessFactors service with the service type *SAP SuccessFactors HCM*.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use-case *Business Process Monitoring*.
6.  The root URL is automatically adjusted.
7.  Choose *ClientCertificateAuthentication* and enter:
    -   *Certificate Key Store Location*: Choose the certificate that you uploaded in SAP SuccessFactors.
    -   *Certificate Key Store Password*: Enter the password that you provided when you generated the certificate.

8.  Choose *Connection Check*.
9.  Choose *Save*.
10. After the successful activation, the data collection starts, and the SAP SuccessFactors tenant becomes available in the *Configuration* pane in the *Business Process Monitoring* app of SAP Cloud ALM.

If the endpoint *Root URL* field isn't filled automatically or if you want to still use BASIC authentication, find the correct API URL:

1.  Select your SAP SuccessFactors service with the service type *SAP SuccessFactors HCM*.
2.  Check the value for the field *System ID* in the properties, for example DC33STD or DC57PREV.
3.  Open [List of SAP SuccessFactors API Servers](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/93f95815070049ebaaff042d8322d518/af2b8d5437494b12be88fe374eba75b6.html?locale=en-US) for different data centers.

    If the *System ID* value ends with *STD*, use the API Server for the *Production* environment.

    If the "*System ID* value ends with *PREV*, use the API Server for the *Preview* environment.




### Activate the Data Colloection

When you've created the endpoint in SAP Cloud ALM, activate the data collection for the monitoring use-cases:

-   Integration and Exception Monitoring: The data collection for SAP SuccessFactors messages is activated automatically, but you need to activate the data collection for SAP SuccessFactors exceptions:
-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   Business Process Monitoring: The data collection is activated automatically.



## Troubleshooting



### HTTP/1.1 401 Unauthorized Error during Endpoint Check

**Symptom**: The endpoint check fails with the error *Server returned unexpected status code: HTTP/1.1 401 Unauthorized*, despite entering the correct password. You can log on to SAP SuccessFactors with this user and password. Also, you're using an Identity Authentication Service \(IAS\) for the authentication.

**Reason**: The SAP SuccessFactors API URL doesn't use the IAS for authentication. The password that the API URL expects is the password that was set for the user in SAP SuccessFactors itself. You can verify this as follows:

1.  Try to log on to the OData endpoint for the API URL for your data center, for example `https://apisalesdemo8.successfactors.com/odata/v2`.
2.  Enter the `username@<Company ID>` and the password that you want to use.
3.  You get the following error: *\[LGN0015\]Authentication failed. You've entered an incorrect username or password \(status code = 4\).*

**Solution**:

Ensure that the correct password is defined in SAP SuccessFactors:

1.  In SAP SuccessFactors, go to *Admin Center* \> *Tools* \> *Reset User Passwords*.
2.  Find the SFAPI user that you want to use.
3.  Reset the password to the password that you want to use.
4.  Choose *Reset User Password*.
5.  Try again to log on to the API URL.
6.  You should now get an XML file as response.

