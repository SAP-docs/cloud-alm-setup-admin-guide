<!-- loio0b3356d4f4194ae88eff663f2b1bc223 -->

# Business Process Monitoring and Exception Monitoring

This page explains how to connect SAP SuccessFactors HCM to SAP Cloud ALM to enable [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring) and [Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/monitoring-exceptions) in SAP Cloud ALM.

The following video demonstrates the setup steps for SAP SuccessFactors. A textual step-by-step description of all setup steps is provided after the video on this site.





<a name="loio0b3356d4f4194ae88eff663f2b1bc223__section_thk_xh4_chc"/>

## Prerequisites

-   You can obtain the SAP Cloud ALM service key to connect to the SAP Cloud ALM system. More under [Managing Your Service Credentials](https://help.sap.com/docs/cloud-alm/setup-administration/service-key).

-   In SAP SuccessFactors, create a technical user as described in [SAP SuccessFactors Technical User](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/sf-sfapi-user.html).

    To use the technical user, SAP SuccessFactors must enable the API for your company instance. This is usually done during the initial implementation. If this wasn't done, contact your SAP SuccessFactors support representative to enable the API for your instance.

-   In SAP SuccessFactors, your personal user needs the following permissions:
    -   *Manage Integration Tools* \> *Access to Integration Service Registration Center UI*
    -   *Admin Center* \> *Manage Permission Roles* \> *Access to X.509 Certificate Mapping*

-   In SAP Cloud ALM, your personal user needs one of the following roles:
    -   *Landscape Management Security Administrator* \(to create and download a certificate\)
    -   or *Landscape Management Security Viewer* \(to download an existing certificate\)


Specific setup information for Integration & Exception Monitoring: [SAP SuccessFactors HCM](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-sf.html).



## Setup in SAP SuccessFactors



### Create an HTTP Endpoint

Map the SAP Cloud ALM certificate in SAP SuccessFactors.

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
    4.  *Login Name*: Enter the previously created technical user.




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
2.  Check the value for the *System ID* field in the properties, for example DC33STD or DC57PREV.
3.  Open [List of SAP SuccessFactors API Servers](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/93f95815070049ebaaff042d8322d518/af2b8d5437494b12be88fe374eba75b6.html?locale=en-US) for different data centers.

    If the *System ID* value ends with *STD*, use the API Server for the *Production* environment.

    If the *System ID* value ends with *PREV*, use the API Server for the *Preview* environment.




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




### Activate the Data Collection

When you've created the endpoint in SAP Cloud ALM, activate the data collection for the monitoring use-cases:

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)
-   Specific setup information for Integration & Exception Monitoring: [SAP SuccessFactors HCM](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/integration-monitoring/calm-sf.html).

-   Business Process Monitoring: The data collection is activated automatically.



## Troubleshooting



### HTTP/1.1 401 Unauthorized Error during Endpoint Check

**Symptom**: The endpoint check fails with the error *Server returned unexpected status code: HTTP/1.1 401 Unauthorized*, despite entering the correct password. You can log on to SAP SuccessFactors with this user and password. Also, you're using an Identity Authentication Service \(IAS\) for the authentication.

**Reason**: The SAP SuccessFactors API URL doesn't use the IAS for authentication. The password that the API URL expects is the password that was set for the user in SAP SuccessFactors itself. You can verify this as follows:

1.  Try to log on to the OData endpoint for the API URL for your data center, for example `https://apisalesdemo8.successfactors.com/odata/v2`.
2.  Enter the `username@<Company ID>` and the password that you want to use.
3.  You get the following error: *\[LGN0015\]Authentication failed. You've entered an incorrect username or password \(status code = 4\).*

**Solution**: Ensure that the correct password is defined in SAP SuccessFactors:

1.  In SAP SuccessFactors, go to *Admin Center* \> *Tools* \> *Reset User Passwords*.
2.  Find the technical user that you want to use.
3.  Reset the password to the password that you want to use.
4.  Choose *Reset User Password*.
5.  Try again to log on to the API URL.
6.  You should now get an XML file as response.

