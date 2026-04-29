<!-- loiod5e097df5371403a823cf123cc4daf21 -->

# Automated Setup with Manual Preliminary Steps

If your SAP S/4HANA Cloud system uses a different customer number than your SAP Cloud ALM system, register and activate it through central monitoring.

This scenario occurs, for example, if customers have a global CCC/ultimate setup where an S-user has access to several customer numbers.

In such cases, the SAP S/4HANA Cloud system doesn't appear automatically in the *System Landscape* application in the SAP BTP global account. The automatic central monitoring setup can't be used.



## Prerequisites

-   The system information is automatically imported from the SAP backend \(SLIS\) to the Landscape Management app of SAP Cloud ALM.
-   In the Landscape Management, the service has the status *New*.
-   SAP Cloud ALM is not located in `eu10-004`.



## Setup



### 1. Manually add SAP S/4HANA Cloud to the System Landscape

1.  On SAP BTP, log in to your SAP Cloud ALM global account.
2.  Navigate to *System Landscape* and open *Systems*.
3.  Select *Add* to create a new system entry.
4.  For *System Type*, select *S/4HANA Cloud*.
5.  Enter a system name:
    -   You can use the system URL as the name.
    -   Alternatively, copy the system name from your landscape or documentation and paste it into the name field.

6.  Save the new system entry.



### 2. Generate a registration token for the system

1.  In the same system entry in *System Landscape*, go to the *Communication Scenario Group* section.
2.  Select *Get Token* to generate a registration token for SAP S/4HANA Cloud.
3.  Copy the generated registration token for later use.



### 3. Register SAP S/4HANA Cloud using the token

1.  Log on to the SAP S/4HANA Cloud target tenant you want to connect to SAP Cloud ALM.
2.  In the SAP S/4HANA Cloud Fiori launchpad, search for the app used to maintain integrations and extensions for SAP BTP.
3.  Open the app. Create a new entry for the extension or integration.
4.  Paste the registration token in the appropriate field.
5.  Enter a meaningful name and description. For example: “Cloud ALM integration for S/4HANA Cloud.”
6.  Save and create the extension. This establishes the registration and connection.
7.  Approve or activate the connection if prompted. The integration becomes active.



### 4. Verify that the system is registered in SAP Cloud ALM

1.  Return to your SAP Cloud ALM global account in SAP BTP.
2.  In the *Landscape Management* app of SAP Cloud ALM, under *System Landscape*, refresh the system list.
3.  Locate the system you created. It should now show as *Registered* and appear as a valid system in the list.
4.  Confirm that the system isn't yet included in any formations. This is expected before central monitoring activation.



### 5. Activate central monitoring setup

Now you can proceed with the standard setup that's described in [Automated Setup in SAP Cloud ALM](automated-setup-in-sap-cloud-alm-785d61b.md).

