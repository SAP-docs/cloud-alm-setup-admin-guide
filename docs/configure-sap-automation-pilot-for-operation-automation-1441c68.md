<!-- loio1441c68e18a7463a810598e99d6e0760 -->

# Configure SAP Automation Pilot for Operation Automation



## Prerequisites

To monitor SAP Automation Pilot with the *Operations Automation* app in SAP Cloud ALM , ensure the following:

-   You've subscribed to the SAP Automation Pilot service.
-   You want to trigger either your own or predefined SAP Automation Pilot commands from SAP BTP Event in SAP Cloud ALM.
-   You've created a service user in the SAP Automation Pilot service with read and execute permissions as explained under [Service Account](https://help.sap.com/docs/automation-pilot/automation-pilot/service-account).
-   You know the SAP Automation Pilot API Base URL, visible in SAP Automation Pilot under *API*.
-   You know the SAP Automation Pilot tenant ID and tenant URL. They're visible in SAP Automation Pilot under *User*.



## Configuration



### Define an endpoint to the SAP Automation Pilot tenant

You need an endpoint in the *Landscape Management* app SAP Cloud ALM, which points to the SAP Automation Pilot tenant. It's required to request the list of commands, trigger new executions, and check the status of executions.

**Define an SAP Automation Pilot cloud service in SAP Cloud ALM:**

If the SAP Automation Pilot service is already known in the *Landscape Management* app, skip these steps and proceed directly with the endpoint creation.

1.  Open the *Landscape Management* app in SAP Cloud ALM.
2.  Choose *Add*.
3.  Enter the SAP Automation Pilot tenant name and tenant ID.
4.  Choose *User* in the left pane.
5.  Enter a description.
6.  Choose the *Cloud Service Type* as SAP Automation Pilot.
7.  Choose the correct tenant type. like production, test, or development.
8.  Enter the tenant URL in the *Root URL* field. Choose *User* in the left pane.
9.  Choose *Save*.

**Add an endpoint:**

1.  Open the *Landscape Management* app in SAP Cloud ALM.
2.  Select the SAP Automation Pilot cloud service.
3.  On the *Endpoints* tab, choose *Add*.
4.  Enter the following data:
    -   *Use Case*: *Operations Automation*
    -   *Root URL*: Enter the SAP Automation Pilot API base URL. Overwrite the existing Root URL if required.

        Choose *API* in the left pane.

    -   *Connection Test Path*: Enter */api/v1/executions*.
    -   *Authentication Type*: Select basic authentication.
    -   Enter the service user name including account prefix \(`T...`\) and the password.

5.  Choose *Save*.



### Register Operation Flow Definitions

The registration step is required to make the SAP Automation Pilot commands known to SAP Cloud ALM for operations as operation flows.

For each SAP Automation Pilot command that should be triggered automatically from SAP Cloud ALM for operations, do the following:

1.  In SAP Cloud ALM, open *Operations Automation*.
2.  Choose *Register Operation Flow* \> *Automation Pilot*.
3.  Choose the command ID that should be triggered.
4.  Assign the *Health Monitoring* use case.
5.  If the command execution requires an additional input reference, choose the correct input reference.
6.  Choose *Ok*.

As a result, the new SAP Automation Pilot command appears in the list of registered operation flows.



### Input Mapping and Definition of Input References

The SAP Automation Pilot command that is triggered from SAP Cloud ALM can require a set of input values. A SAP BTP event triggers the transfer of the following input values to the SAP Automation Pilot command:

-   region
-   resourceName
-   subAccount
-   resourceGroup
-   resourceInstance
-   resourceType
-   subject
-   eventTimestamp
-   body

If the SAP Automation Pilot command requires additional input values, define an input in the SAP Automation Pilot that contains the required pairs of name and value and register the command together with the correct input in SAP Cloud ALM.

