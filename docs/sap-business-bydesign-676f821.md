<!-- loio676f8214b6a8408db4eed3d41c6ec9cb -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# SAP Business ByDesign

This document provides guidance on connecting products related to SAP Business ByDesign to SAP Cloud ALM for monitoring purposes.

Currently, SAP Business ByDesign supports the following monitoring applications:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Prerequisites

You have a user with administrator authorization in SAP Business ByDesign.



## Setup in SAP Business ByDesign



### Activate the Communication System

1.  In the SAP Business ByDesign launchpad, in the navigation panel, choose *Application and User Management* \> *Input and Output Management* \> *Communication Systems*.

2.  Choose *New* to create a new communication system:

    -   *ID*: Enter, for example, the SAP Cloud ALM tenant ID.
    -   *Host Name*: Enter the host name of your SAP Cloud ALM tenant. You can find the host name in your SAP Cloud ALM URL, for example `eu10.alm.cloud.sap`.
    -   *System Access Type*: Select *Internet*.

3.  To maintain a new system instance, choose *Add Row* under *System Instances*.
    -   *System Instance ID*: Enter, for example, CRUN\_WS.
    -   *Preferred Application Protocol*: Choose *Web Service*.

4.  Save the communication system with *Save & Close*.

5.  Activate the communication system with *Actions* \> *Set to Active*.




### Create the Communication Arrangement

1.  In the SAP Business ByDesign launchpad, in the navigation panel, choose *Application and User Management* \> *Input and Output Management* \> *Communication Arrangements*.

2.  Choose *New* to create a new communication arrangement.
    1.  Select Scenario: Choose *Query Webservice Messages for Monitoring*.
    2.  Define Business Data: Select the CRUN\_WS communication system instance.
    3.  Define technical data:
        -   *Communication Method*: *Direct Connection*
        -   *Application Protocol*: *Web Service*
        -   *Authentication Method*: *Basic Authentication*
        -   *User ID*: Choose *Edit Credentials* to maintain user and password.


3.  Review and confirm.




## Setup in SAP Cloud ALM



### Create HTTP Endpoint

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Choose the service name or choose <span class="SAP-icons-V5"></span> \(Navigation\) at the end of the row.
3.  On the *Endpoints* tab, choose *Add* to create a new endpoint.
4.  Enter a description.
5.  Choose the use case, for example, *Integration Monitoring*.
6.  Choose *BASIC* authentication.
7.  Enter the user and password that you created for the communication agreement.

After creating the endpoint, activate the data collection for the monitoring use-cases in the respective monitoring applications.



### Next Steps

-   [Activate the data collection for Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/configuring-integration-monitoring)

