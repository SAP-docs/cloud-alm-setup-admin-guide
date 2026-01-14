<!-- loiof61f448785c54eb3b10a67841bd57007 -->

# SAP Business Network for Logistics, shipper

This document provides guidance on connecting SAP Business Network for Logistics, to SAP Cloud ALM for monitoring purposes.

The following monitoring application is supported for SAP Business Network for Logistics, shipper:

-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)



## Prerequisites

You can obtain the SAP Cloud ALM service key to connect the SAP Cloud ALM system.

Your user in SAP Business Network for Logistics, shipper, has a role collection that contains the following roles:

-   SystemConnectionsReadOnlyTemplate

-   SystemConnectionsProcessTemplate




## Setup Monitoring Push to SAP Cloud ALM in SAP BTP



### Register in SAP Cloud ALM

1.  In SAP BTP Cockpit, select your subscription for SAP Business Network for Logistics, shipper, and choose *Go to Application*.
2.  Choose the *System Connections* tile in the *Manage Network* group.
3.  Choose *Add* to add a new connection.
    1.  *Connection Type*: *SAP Cloud ALM*
    2.  *Connection ID*: Enter a name for your connection.
    3.  Choose *Create*.

4.  Select your new connection in the list.
5.  Choose *Maintain Authentication Details*.
6.  Choose *Add* to add new authentication details:
    1.  *Name*: SAP Cloud ALM OAuth
    2.  *Type*: OAuth
    3.  *Grant Type*: Client Credentials
    4.  *Authentication URL*: SAP Cloud ALM service key parameter `<uaa>:<URL>`, extended by `/oauth/token`. Example???
    5.  *Client ID*: SAP Cloud ALM service key parameter `<uaa>:<clientID>`. Example ???
    6.  *Client Secret*: SAP Cloud ALM service key parameter `<uaa>:<clientsecret>`. Example ???
    7.  *Client Authentication*: Send as *Body Parameter*.
    8.  Choose *Create*.

7.  Maintain the connection details:
    1.  *System URL*: Enter the SAP Cloud ALM service key parameter api without `/api`, for example, `https://eu10.alm.cloud.sap`.
    2.  *Authentication Alias*: Select SAP Cloud ALM OAuth.
    3.  Save your changes.

8.  Choose *Activate Connection*.



### Deactivate Registration in SAP Cloud ALM

If you want to turn off the monitoring in the tenant for of SAP Business Network for Logistics, shipper, proceed as follows:

1.  In the SAP BTP cockpit, select your subscription for SAP Business Network for Logistics, shipper, and choose *Go to Application*.
2.  Choose the *System Connections* tile in the *Manage Network* group.
3.  Select your connection to SAP Cloud ALM.
4.  Choose *Deactivate*.
5.  Delete the connection.



## Next Steps

When you have set up the monitoring push to SAP Cloud ALM in SAP BTP cockpit for your managed service, the data collection is active, with default monitoring configurations.

You can adjust the monitoring setup within the monitoring app in SAP Cloud ALM. Find more information on the configuration for the apps under [SAP Cloud ALM for Operations](https://help.sap.com/docs/cloud-alm/applicationhelp/operations).

