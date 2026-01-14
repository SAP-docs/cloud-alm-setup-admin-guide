<!-- loioe1efb9ee72a0453993d0236a53d1e16f -->

# SAP Central Business Configuration

This document provides guidance on connecting SAP Central Business Configuration to SAP Cloud ALM for monitoring purposes.

Currently, SAP Central Business Configuration supports the following monitoring applications:

-   [Process Management](https://help.sap.com/docs/cloud-alm/applicationhelp/processes)



<a name="loioe1efb9ee72a0453993d0236a53d1e16f__section_wrd_klv_xgc"/>

## Prerequisites

The information for your system or service has been imported to the *Landscape Management* app in SAP Cloud ALM. This happens daily with an automatic landscape import job. After subscribing to SAP Cloud ALM, you need to wait up to 24 hours for the job to run, for the first time.



<a name="loioe1efb9ee72a0453993d0236a53d1e16f__section_psx_slv_xgc"/>

## Setup in SAP Cloud ALM

You need to create the endpoint in your SAP Cloud ALM tenant, to enable data collection.

1.  Open the *Landscape Management* app from the launchpad and select your service under *Services & Systems*.
2.  Under *Endpoints*, choose *Create Endpoints Automatically*.
3.  The endpoint creation can take several minutes.

    You can check the status by choosing *Refresh* for the whole table and then choosing *Refresh* for the endpoint entry.




### Troubleshooting

-   *Error: \[500\] Endpoint Automation Failed - 400 Bad Request*

    Reason: We're using the service description for the description when creating the endpoint. The description of your service contains a special character. The description for SAP BTP destinations must not include special characters.

    Solution: Click the icon in the upper right corner of the service details and change the *Description* field. Remove all special characters.

    Remove the failed endpoint and create a new one.


