<!-- loioe21f91558ab145378c0c6de77516cec6 -->

# Integrating SAP Central Business Configuration

By integrating SAP Central Business Configuration with SAP Cloud ALM, you can import roadmap content into the *Tasks* app. This helps you understand the order in which the tasks need to be carried out, and lets you navigate directly to SAP Central Business Configuration as needed.

SAP Central Business Configuration is a solution that supports the configuration of SAP S/4HANA Cloud Public Edition. SAP S/4HANA Cloud Private Edition is not supported.

While an SAP Cloud ALM project applies the SAP Activate methodology to provide end-to-end procedural guidance on how to start and run an implementation project, an SAP Central Business Configuration workspace shows the activities focused on your specific business configuration.

To use SAP Central Business Configuration in SAP Cloud ALM, you first need to carry out the following setup procedure.



<a name="loioe21f91558ab145378c0c6de77516cec6__section_mck_kpd_ncc"/>

## Prerequisites

-   You have the role *Landscape Administrator*.

-   You have the role *Project Administrator* or *Project Lead*.




<a name="loioe21f91558ab145378c0c6de77516cec6__section_qyd_jx4_nnb"/>

## Procedure



### Technical Setup

For guidance on the connection of your SAP Central Business Configuration tenant to SAP Cloud ALM, see [SAP Central Business Configuration](../sap-central-business-configuration-e1efb9e.md).

Please note that you can maintain only one service and one endpoint for the integration of SAP Central Business Configuration.



### Integration During Project Creation

After you've completed the technical setup, select SAP Central Business Configuration as an integration scenario by carrying out the following steps:

1.  Go back to the SAP Cloud ALM launchpad and open the *Implementation* tab.

2.  Open the *Projects and Setup* app.

3.  To create a new project, choose *Create*.

4.  Enter the following parameters:

    -   *Project*: Enter a project name of your choosing, such as `Implementation Project`.

    -   *SAP Activate Roadmap*: Select the desired roadmap.

    -   *Access Level*: Select an access level for your project.

    -   *Status*: Select `On Track`.

    -   *Current Phase*: Select `Prepare`.

    -   *Scenario*: Select `SAP Central Business Configuration`.

        ![](images/CBC_Project-Creation_4b7a778.png)


5.  Select the SAP Central Business Configuration workspace or workspaces that you want to connect to SAP Cloud ALM.

    You can unassign SAP Central Business Configuration workspaces from the corresponding SAP Cloud ALM project at any time.

6.  Save the new project.




<a name="loioe21f91558ab145378c0c6de77516cec6__section_xmq_5qd_ncc"/>

## Result and Next Steps

You have now connected your SAP Central Business Configuration workspace or workspaces with your SAP Cloud ALM project.

You can now navigate to your SAP Central Business Configuration workspace with the direct links in the table or via the respective tasks.



> ### Note:  
> To access SAP Central Business Configuration from SAP Cloud ALM, users need to be maintained both in the Identity Authentication tenant that is connected to SAP Cloud ALM and in the Identity Authentication tenant that is connected to SAP Central Business Configuration.

**Related Information**  


[SAP Central Business Configuration – SAP Help Portal](https://help.sap.com/docs/CENTRAL_BUSINESS_CONFIGURATION)

[Integrating SAP Cloud ALM with SAP Central Business Configuration – SAP Community](https://blogs.sap.com/2021/01/29/integrating-sap-cloud-alm-with-sap-central-business-configuration/)

