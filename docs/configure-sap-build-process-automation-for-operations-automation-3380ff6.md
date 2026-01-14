<!-- loio3380ff6240194cefa579c0b03f9743da -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configure SAP Build Process Automation for Operations Automation



## Prerequisites

To use the *Operations Automation* app in SAP Cloud ALM for SAP Build Process Automation, ensure the following:

-   You've subscribed to an SAP BTP account with activated SAP Build Process Automation in one of the subaccounts.
-   You're developing workflows or automations in your SAP Build Process Automation management account that either resolve error situations and alerts detected by SAP Cloud ALM or you orchestrate and automate regular operational tasks.

    These workflows or automations are automatically or manually triggered from SAP Cloud ALM for operations as a follow-up action to a monitoring event or an alert.




## Configuration

**Obtain the Service Key**

1.  Log on to the SAP BTP cockpit.
2.  Navigate to the subaccount where SAP Build Process Automation is subscribed.
3.  Choose *Instances and Subscriptions*.
4.  Select the service instance for SAP Build Process Automation.
5.  Go to the *Service Keys* tab.
6.  Choose *Actions* and then *Download*.

**Create the API Key**

1.  Log on to SAP Build Process Automation.
2.  Select *Control Tower*.
3.  Create an API key with the scopes *trigger\_read* and *trigger\_execute* for the environments that you want to use.
4.  Copy the generated API key.

**If necessary: Define a SAP Build Process Automation Cloud Service in Landscape Management**

If the SAP Build Process Automation service belongs to the same customer number as your SAP Cloud ALM, the service is already registered in the Landscape Management of SAP Cloud ALM as a cloud service of type SAP Build Process Automation. In this case, skip the service creation and proceed directly with the endpoint creation.

Only if the SAP Build Process Automation service isn't yet shown in Landscape Management, define it manually:

1.  In SAP Cloud ALM, open the *Landscape Management* app.
2.  Choose :heavy_plus_sign:.
3.  Enter the SAP Build Process Automation subaccount name and tenant ID.
4.  Enter any description.
5.  Select the cloud service type *SAP Build Process Automation*.
6.  Select the correct tenant type, such as production, test, development.
7.  Enter the root URL of the workflow management application \(`https://.... build.cloud.sap`\) into the *Root URL* field and *Logon URL* field.
8.  Enter the subdomain ID in the *External ID* field.
9.  Choose *Save*.

**Add an Endpoint**

1.  In to SAP Cloud ALM, open the *Landscape Management* app.
2.  Select the relevant cloud service of type *SAP Build Process Automation*.
3.  Choose *Edit*.
4.  Go to the *Endpoints* tab.
5.  Choose :heavy_plus_sign:.
6.  Optionally overwrite the proposed name and add a description.
7.  Ensure that you have the service key JSON in your clipboard and choose *Paste Service Key*.
8.  Enter the API key.
9.  Choose *Save*.

> ### Note:  
> -   Save the endpoint only after you've entered the service key and API key, and not in between.
> -   The connection check in the endpoint definition fails. This can be ignored.



### Register the Operation Flow Definitions

The registration step is required to make the relevant workflows or automations known to SAP Cloud ALM for operations as operation flows.

Perform the following for each workflow or automation that should be triggered manually or automatically from SAP Cloud ALM for operations.

1.  In to SAP Cloud ALM, open the *Operations Automation* app.
2.  Choose *Register Operation Flow* \> *SAP Build Process Automation*.
3.  Choose the correct endpoint from the value help.
4.  Select the workflow and automation ID that you want to have triggered.
5.  Assign a use case corresponding to the planned usage of this workflow and automation.

    Example: If the workflow or automation should be triggered for monitoring events or alerts from Integration Monitoring, choose *Integration Monitoring*.

6.  Choose *OK*.

As a result, the new workflow and automation definition appear in the list of registered operation flows.

**Optional: Define Event Actions**

You can trigger the operation flow either manually from alerts or automatically as an event action for a monitoring event.

The configuration of operation flows as event actions for monitoring events is done in the configuration UI of the monitoring apps in SAP Cloud ALM.

