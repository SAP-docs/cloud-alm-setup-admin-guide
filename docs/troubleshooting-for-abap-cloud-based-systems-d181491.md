<!-- copyd1814913f4d24a92b96198efa1284de6 -->

# Troubleshooting for ABAP Cloud-Based Systems

This page gives you some hints when you run into a problem for the communication scenarios SAP\_COM\_0523 and SAP\_COM\_0527.

This information applies to the following setup scenarios:

-   SAP BTP, ABAP environment
-   SAP S/4HANA Cloud
-   SAP Marketing Cloud
-   SAP Integrated Business Planning for Supply Chain

-   **Error: Can't create HTTP Client: Error when setting oauth token**

    The value in the field *Token Endpoint* in the communication system isn't correct. It must be the SAP Cloud ALM service key parameter `url` followed by `/oauth/token`.

-   **Error: MSG\_SLIS\_NOT\_FOUND\_IN\_LMS**

    During the registration of the ABAP cloud-based system, the process checks if this system was already imported from SAP's Cloud Landscape Directory to the landscape management of SAP Cloud ALM.

    Usually, we import all cloud services of a customer automatically, shortly after SAP Cloud ALM is provisioned.

    The error message indicates that the cloud system doesn't exist in SAP Cloud ALM yet. Please check [Troubleshooting for Landscape Management](https://help.sap.com/viewer/877c96cf971648b09ee0d0a64f7f4fef/latest/en-US/9d68fc2749c84c4a8d3c9bc1b7ddfb89.html "This page helps you to analyze common errors in the Landscape Management app of SAP Cloud ALM.") :arrow_upper_right: page for details.

-   **Error: Can't create http client: destination not found**

    This can happen mainly for SAP BTP ABAP services using the destination service. One reason can be that the credentials from the SAP Cloud ALM API service key are no longer valid.

    If the service key has been downloaded from the *Landscape Management* app in SAP Cloud ALM, you should test it there, first.

    Otherwise, test it with a REST API client \(such as Postman, Insomnia, or Bruno\) as described in KBA [3469976](https://me.sap.com/notes/3469976). If the result contains an error message like *Bad credentials*, you know it's no longer valid.


