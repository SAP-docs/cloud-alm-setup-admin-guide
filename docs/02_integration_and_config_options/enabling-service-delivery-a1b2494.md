<!-- loioa1b2494bb9f54228bd6e77132740b195 -->

# Enabling Service Delivery

An SAP service is usually delivered as part of a service contract like SAP MaxAttention, SAP ActiveAttention or SAP Enterprise Support.



Typically, SAP consultants deliver such a service via SAP internal applications. Information required for the collaboration between SAP and the customer during the delivery of such services and the outcome of these service deliveries are shared with the customer via a data transfer into the customer's SAP Cloud ALM tenant.



With this data transfer, the following service-related information is sent from SAP to your SAP Cloud ALM tenant:

-   Service details and results

-   Preparation tasks, notes, issues, and actions

-   Attachments


In addition, SAP synchronizes changes that you make to the following service-related documents from your SAP Cloud ALM tenant back to SAP:

-   Comments and status changes for your preparation tasks, notes, and attachments

-   Status changes for issues and actions

    If you assign a task or an issue to a user, this assignment information is **not** replicated from your SAP Cloud ALM tenant back to SAP.

-   Attachments you upload


> ### Note:  
> All pictures and attachments are stored in a separate SAP-internal storage and don't affect the overall size of your SAP Cloud ALM tenant.



<a name="loioa1b2494bb9f54228bd6e77132740b195__section_xzy_k5r_szb"/>

## Activating and Deactivating the Data Transfer

This data transfer is automatically activated when your SAP Cloud ALM tenant was provisioned. If you don't want service information to be transferred into your SAP Cloud ALM tenant, you can request to deactivate the data transfer by creating a case on component SV-CLM-SD. Please provide the following information in the case:

-   Your customer number

    If you have multiple customer numbers, please list all customer numbers for which the data transfer should be deactivated.

-   The URL of the SAP Cloud ALM tenant for which you want to deactivate the data transfer


> ### Note:  
> Service information that was already transferred to your SAP Cloud ALM tenant is not deleted when the data transfer is deactivated.

You can reactivate the data transfer at any time in the same way and by providing the same information.

If you don't know whether the data transfer for your tenant is active, access the *Service Delivery Center* app in your SAP Cloud ALM tenant. If the data transfer is deactivated, you will see a message on the initial screen of the app.

For more information, refer to [Data Transfer for Service Information](https://help.sap.com/docs/CloudALM/877c96cf971648b09ee0d0a64f7f4fef/f747d1391c514e20af7b117b17696b25) and SAP Note [3401303](https://me.sap.com/notes/3401303).



<a name="loioa1b2494bb9f54228bd6e77132740b195__section_z3z_l5r_szb"/>

## Tenant Mapping

Services are always requested and delivered for a specific customer number. The data transfer for service data uses this customer number to determine which SAP Cloud ALM tenant should receive the service information. Customers with several customer numbers can maintain a tenant mapping to determine into which SAP Cloud ALM tenant the service information for each of their customer numbers should be transferred.

For more information, refer to [Maintain Tenant Mapping](https://help.sap.com/docs/cloud-alm/applicationhelp/maintain-tenant-mapping).

**Related Information**  


[SAP Cloud ALM for Service](https://help.sap.com/docs/cloud-alm/applicationhelp/service)

