<!-- loio84602a521c5946f88a409b39587dd70e -->

# SAP S/4HANA Cloud Public Edition

This page explains how to connect SAP S/4HANA Cloud Public Edition to SAP Cloud ALM to enable monitoring.

Currently, SAP S/4HANA Cloud Public Edition supports the following monitoring applications:

-   [Business Process Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/business-process-monitoring)
-   [Integration and Exception Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/integration-exception-monitoring)
-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)
-   [Job and Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring)
-   [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring)

**To set up the monitoring in SAP Cloud ALM, follow the instructions for your scenario:**

-   [Automated Setup in SAP Cloud ALM](automated-setup-in-sap-cloud-alm-785d61b.md)

    You can use the fully automated setup for SAP S/4HANA Cloud public edition if your implementation meets all of these prerequisites:

    -   The system information is automatically imported from the SAP backend \(SLIS\) to the Landscape Management app of SAP Cloud ALM.
    -   In the Landscape Management, the service has the status *New*.
    -   The customer number for SAP S/4HANA Cloud public edition matches the customer number for the SAP Cloud ALM tenant.
    -   SAP Cloud ALM is not located in `eu10-004`.

-   [Automated Setup with Manual Preliminary Steps](automated-setup-with-manual-preliminary-steps-d5e097d.md)

    If your SAP S/4HANA Cloud system uses a **different customer** number than your SAP Cloud ALM system, some preliminary steps are required. All of the following prerequisites must be met:

    -   The system information is automatically imported from the SAP backend \(SLIS\) to the Landscape Management app of SAP Cloud ALM.
    -   In the Landscape Management, the service has the status *New*.
    -   SAP Cloud ALM is not located in `eu10-004`.

-   [Classic Setup](classic-setup-e144305.md)

    **This setup is required if *any* of the following applies:**:

    -   You have manually created the system information for SAP S/4HANA Cloud public edition in the Landscape Management app of SAP Cloud ALM,
    -   or the service is in status *Active* or *Inactive* in the Landscape Management service,
    -   or your SAP Cloud ALM tenant is in `eu10‑004`.


-   **[Automated Setup in SAP Cloud ALM](automated-setup-in-sap-cloud-alm-785d61b.md "An automated standard setup is available for SAP S/4HANA Cloud public edition
		systems.")**  
An automated standard setup is available for SAP S/4HANA Cloud public edition systems.
-   **[Automated Setup with Manual Preliminary Steps](automated-setup-with-manual-preliminary-steps-d5e097d.md "If your SAP S/4HANA Cloud system uses a different customer number than your SAP Cloud
		ALM system, register and activate it through central monitoring.")**  
If your SAP S/4HANA Cloud system uses a different customer number than your SAP Cloud ALM system, register and activate it through central monitoring.
-   **[Classic Setup](classic-setup-e144305.md "This page describes the classic, manual setup of SAP S/4HANA Cloud public edition for
		monitoring in SAP Cloud ALM.")**  
This page describes the classic, manual setup of SAP S/4HANA Cloud public edition for monitoring in SAP Cloud ALM.
-   **[Troubleshooting for ABAP Cloud-Based Systems](troubleshooting-for-abap-cloud-based-systems-85d30d1.md "This page gives you some hints when you run into a problem for the communication
		scenarios SAP_COM_0523 and SAP_COM_0527.")**  
This page gives you some hints when you run into a problem for the communication scenarios SAP\_COM\_0523 and SAP\_COM\_0527.

