<!-- loio9cdf23482443424291d536344b1bb10e -->

# General Concepts

Before you start setting up and configuring SAP Cloud ALM, familiarize yourself with the following basic concepts.



<a name="loio9cdf23482443424291d536344b1bb10e__section_uql_wtl_b2c"/>

## SAP BTP Account Administration

When your SAP Cloud ALM tenant is provisioned, a global account and a subaccount are set up on SAP BTP. These accounts are set up exclusively for SAP Cloud ALM.

Therefore, don't use them for any other products, applications, or services.



### Global Accounts

A global account is the realization of a contract you made with SAP. It's region-independent and is used to manage subaccounts, members, entitlements, and quotas.

In the case of SAP Cloud ALM, your entitlement is based on the existence of other contracts or purchased solutions that are connected to your customer number. The entitlement also comes with other parameters, such as fair use rights for memory, which are provided free of charge. These factors require a separate global account to be established specifically for SAP Cloud ALM, which is separated from other global accounts containing chargeable entitlements.



### Subaccounts

In subaccounts, you deploy applications, use services, and manage your subscriptions. Your SAP Cloud ALM subaccount contains your SAP Cloud ALM subscription and a subscription to the Cloud Integration Automation service.

Each subaccount is associated with a region, which corresponds to the data center where your SAP Cloud ALM tenant is operated.

For more information on account administration topics in the SAP BTP cockpit, see [Account Model](https://help.sap.com/docs/btp/sap-business-technology-platform/account-model).



<a name="loio9cdf23482443424291d536344b1bb10e__section_sxt_dvf_c2c"/>

## Regions and Data Centers

The region that you select when requesting SAP Cloud ALM corresponds to the physical location of the data center where your SAP Cloud ALM tenant will be operated.

For an overview of the data centers that are currently available and those that are planned in the future, see [SAP Cloud ALM Data Centers](https://support.sap.com/en/alm/sap-cloud-alm.html?anchorId=section_1424572767_c) on SAP Support Portal. The page [Data Center Locations](https://www.sap.com/about/trust-center/data-center.html?currentLevel=world&mode=solutions&solutionId=NZA842) under SAP Security and Trust contains a full list of all **live** data centers, even ones that are no longer supported for new SAP Cloud ALM tenants \(for example, the **Netherlands | Amsterdam** region\).

> ### Note:  
> It's currently not possible to move your SAP Cloud ALM tenant from the data center in which it was originally provisioned to a different data center. However, if you're willing to accept loss of data, you can dismantle and resubscribe SAP Cloud ALM in a different data center by following the steps described in KBA [3352417](https://me.sap.com/notes/3352417).



<a name="loio9cdf23482443424291d536344b1bb10e__section_fqr_wtl_b2c"/>

## User Onboarding

To give users access to SAP Cloud ALM, you need to add them in two places:

-   The identity provider that is connected to SAP Cloud ALM

-   The *User Management* app in SAP Cloud ALM

    Alternatively, you can also add users in the SAP Cloud ALM subaccount on SAP BTP.


> ### Note:  
> Only when users are maintained both in the identity provider and in SAP Cloud ALM, they can log on.



<a name="loio9cdf23482443424291d536344b1bb10e__section_i2k_r5l_b2c"/>

## Identity Providers

With identity providers, you can manage user identities for multiple applications in one central place.

In SAP Cloud ALM, the Identity Authentication service \(IAS\), which is one component of the SAP Cloud Identity Services, typically assumes the role of the identity provider. Business users sign in to SAP Cloud ALM with the mechanisms and credentials defined there.

If you don't have an Identity Authentication tenant when you request SAP Cloud ALM, a new one will be created for you. If you already have a productive Identity Authentication tenant from another SAP solution, we recommend reusing it for SAP Cloud ALM to simplify your identity management.

For more information about the Identity Authentication service, see [What are Cloud Identity Services?](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/what-is-identity-authentication). To learn more about how they're used in SAP Cloud ALM, see [Step 1: Onboard Users in the Identity Authentication Service](01_required_setup/step-1-onboard-users-in-the-identity-authentication-service-f2a8a8c.md).



<a name="loio9cdf23482443424291d536344b1bb10e__section_wcq_szl_b2c"/>

## Roles, Role Collections, and Role Templates

Roles in SAP Cloud ALM are delivered predefined and ready to use.



### 

In general, each application role in SAP Cloud ALM represents a role collection in your SAP BTP subaccount. This means that most SAP Cloud ALM role collections correspond 1:1 to the respective role template and can be assigned to users without any further configuration.

Most application roles contains all the necessary authorizations that are required for all tasks that belong to a certain business role, rather than being confined to a single task. For example, the role *Project Administrator* doesn't just contain authorizations in the *Projects and Setup* app but also in other apps that are typically used as part of an implementation project.

Some areas also offer role templates without a 1:1 relationship with a role collection. Before you can use these role templates, you need to assign them to a custom role collection.

For a full list of all SAP Cloud ALM roles and their corresponding role collections, see [Roles](01_required_setup/roles-e1915af.md). For a list of all SAP Cloud ALM role templates and instructions on how to use them, see [Role Templates](01_required_setup/role-templates-f7294b2.md).



<a name="loio9cdf23482443424291d536344b1bb10e__section_uty_xwf_c2c"/>

## Managed Services and Systems

In SAP Cloud ALM, services are understood as subscribed cloud services, that is, solutions and applications that are offered on-demand from the servers of a cloud provider \(SaaS\).

Systems are defined as on-premise systems, that is, solutions and applications that are provided by SAP but installed and run on the premises of the company or organization using them, or in a private cloud solution.

To work with your services and systems in SAP Cloud ALM, they need to be set up in the *Landscape Management* app in SAP Cloud ALM. For more information, see [Step 3: Set Up Landscape Management](01_required_setup/step-3-set-up-landscape-management-23f1c49.md) and [Connecting Systems and Services](connecting-systems-and-services-31159aa.md).

However, you have full control over which data is transferred from your services and systems to SAP Cloud ALM. When you activate your SAP Cloud ALM tenant and register your systems and services in the *Landscape Management* app of SAP Cloud ALM, the collection of observability data is not started automatically. SAP Cloud ALM follows a central configuration approach: You need to explicitly configure the data collection processes.

