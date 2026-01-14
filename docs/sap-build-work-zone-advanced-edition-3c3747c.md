<!-- loio3c3747ceca5e44c396c049f7d47fe929 -->

# SAP Build Work Zone, advanced edition

This page explains how to connect products that are related SAP Build Work Zone in **SAP BTP, Cloud Foundry environment** to SAP Cloud ALM to enable monitoring.

This includes the following products:

-   SAP Build Work Zone, standard edition
-   SAP Build Work Zone, advanced edition
-   SAP Cloud Portal service
-   SAP SuccessFactors Work Zone

Currently, products that are related to SAP Build Work Zone support the following monitoring applications:

-   [Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/real-user-monitoring)



<a name="loio3c3747ceca5e44c396c049f7d47fe929__d8e362"/>

## Setup in SAP Build Work Zone

Enable the data collection for HTML5 apps and locally created HTML5 apps:

1.  Access the SAP Build Work Zone.
2.  Go to *Site Settings*.
3.  Open the *Services*section.
4.  Enable the *Statistical Data Collection* setting.

More information:

-   [SAP Build Work Zone, standard edition\(opens in new tab\)](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/enable-statistical-data-for-your-apps)
-   [SAP Build Work Zone, advanced edition](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/enable-statistical-data-for-your-apps)

**How data is collected and can be displayed:**

You can activate the following applications from SAP Build Work Zone:

-   HTML5 apps from the HTML5 content provider.

-   Locally created SAPUI5 applications in the Content Manager.


Iframe-embedded applications, such as SAP Fiori applications from on-premise systems, send the data to their backend system and need to be collected and displayed there.



<a name="loio3c3747ceca5e44c396c049f7d47fe929__d8e441"/>

## Setup in SAP Cloud ALM

The integration between SAP Cloud ALM and many SAP cloud services is orchestrated by [SAP-Managed Connectivity](https://help.sap.com/docs/cloud-alm/setup-administration/sap-managed-connectivity).

SAP-managed connectivity uses SAP's infrastructure for OpenTelemetry-based data collection to report monitoring data to SAP Cloud ALM.

To activate the data collection, activate the monitoring in the respective SAP Cloud ALM monitoring app. By activating the data collection, you also give consent for the data exchange.

For details, check the documentation for the supported use cases:

-   [Activate the data collection in Real User Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/rum-connecting-services#activate-real-user-monitoring-data-collection)

