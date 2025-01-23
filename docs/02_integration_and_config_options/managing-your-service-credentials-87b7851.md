<!-- loio87b78510c8cd4d4781249f0973ebaf17 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Your Service Credentials

If you requested SAP Cloud ALM on or after June 14, 2023, automatically generated SAP Cloud ALM service credentials were uploaded to the *Landscape Management* app for you. These credentials can be used to connect managed services to push monitoring data using OAuth 2.0.



<a name="loio87b78510c8cd4d4781249f0973ebaf17__section_fhc_m3b_nxb"/>

## Prerequisites

To access and upload your service credentials, you need the role *Landscape Management Security Administrator*.



<a name="loio87b78510c8cd4d4781249f0973ebaf17__section_gq4_htz_lxb"/>

## Accessing Your Service Credentials

You can access the service credentials in the *Landscape Management* app by opening the configuration \(:gear:\) and expanding the section *SAP Cloud ALM Service Key*.

Here, you can manage your service credentials as follows:

-   :eyeglasses:: Display the content of the uploaded service key.

-   <span class="SAP-icons-V5"></span> \(Download Service Key\): Download the service key as a TXT file. The content will be in JSON format.

-   :wastebasket:: Delete a service key from landscape management.

-   <span class="SAP-icons-V5"></span> \(Test Service Key\): Check if this key can be used to sign in to the SAP Cloud ALM API.




<a name="loio87b78510c8cd4d4781249f0973ebaf17__section_qpg_2tz_lxb"/>

## Uploading Service Credentials

If no service credentials have been uploaded yet, you can add it as follows:

1.  Open the [SAP BTP cockpit](https://cockpit.btp.cloud.sap/).

2.  Select the global account that contains your SAP Cloud ALM entitlement and then open the subaccount that contains your SAP Cloud ALM subscription.

3.  Choose *Services* \> *Instances and Subscriptions*.

4.  Under *Instances*, find the instance that contains your service key or service binding.

5.  Under *Credentials*, open your credentials and choose *Download*.

6.  In the SAP Cloud ALM launchpad, open the *Administration* page.

7.  Open the *Landscape Management* app.

8.  Open the configuration \(:gear:\) and expand the section *SAP Cloud ALM Service Key*.

9.  Choose :heavy_plus_sign:.

10. Upload the TXT file containing the service credentials.

    Make sure that the file has the following characteristics:

    -   The service key in the TXT file is in valid JSON format.

    -   The service key belongs to the SAP Cloud ALM tenant you're working in. Verify the field `uaa.identityzone`.

    -   The service key contains the fields `uaa.clientid` and `uaa.clientsecret`.

    -   The value for the field `uaa.credential-type` is `instance-secret`.


    > ### Note:  
    > -   You can only upload one service key or binding for this SAP Cloud ALM tenant.
    > 
    > -   We recommend that you upload the service credentials to landscape management that is used regularly to connect managed services and systems to SAP Cloud ALM, for example, for monitoring setup or transport management.
    > 
    > -   You can use the same service credentials for all managed services and systems to connect them for the same purpose, such as monitoring.
    > 
    > -   If you use a different "one-use" service key for each managed service, don't upload this key to landscape management. This functionality is intended for regularly used credentials only.
    > 
    > -   Don't upload service keys for API calls, such as the SAP Cloud ALM Analytics API, to landscape management.

11. Choose *Upload*.

    A format check is performed before uploading the service credentials to verify its validity.




> ### Caution:  
> If you delete your service credentials or an SAP Cloud ALM API service instance in the BTP cockpit, the service credentials in the *Landscape Management* app will not be deleted automatically. Please make sure to also delete it from landscape management, as it can no longer be used for authentication.

