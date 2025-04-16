<!-- loioe1915af019da48cc8b8e58399e8ea235 -->

# Role Collections

Role collections in SAP Cloud ALM are delivered predefined and ready to use.





### 

In general, each application role in SAP Cloud ALM represents a role collection in your SAP BTP subaccount. This means that most SAP Cloud ALM role collections correspond 1:1 to the respective role template and can be assigned to users without any further configuration.

> ### Note:  
> Some SAP Cloud ALM areas also offer single role templates. Before you can use these role templates, you need to assign them to a role collection. For more information, see [Role Templates](https://help.sap.com/docs/cloud-alm/setup-administration/role-templates).

Each application role contains all the necessary authorizations that are required for all tasks that belong to a certain business role, rather than being confined to a single task. For example, the role *Health Monitoring Administrator* also contains authorizations in the *Intelligent Event Processing* and *Notification Management* apps because someone in that role also needs to be able to configure events and set up notifications.



<a name="loioe1915af019da48cc8b8e58399e8ea235__section_nrl_qlc_pdc"/>

## Available Role Collections

****


<table>
<tr>
<th valign="top">

SAP Cloud ALM Area

</th>
<th valign="top">

SAP Cloud ALM Capability

</th>
<th valign="top">

Role Title in SAP Cloud ALM User Management

</th>
<th valign="top">

Description

</th>
<th valign="top">

Role Collection Name

</th>
<th valign="top">

Role Template

</th>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Cross Application

</td>
<td valign="top">

*Global Administrator* 

</td>
<td valign="top">

Create and manage all SAP Cloud ALM objects, except for personal or sensitive data

</td>
<td valign="top">

*Cross Global Administrator* 

</td>
<td valign="top">

`x_calm_GlobalAdministrator`

`FlexOperator`

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Cross Application

</td>
<td valign="top">

*Global Auditor* 

</td>
<td valign="top">

View all SAP Cloud ALM objects, except personal or sensitive data

This role is to be used for general audit purposes.

</td>
<td valign="top">

*Cross Global Auditor* 

</td>
<td valign="top">

`x_calm_GlobalAuditor` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

User & Access Management

</td>
<td valign="top">

*User Administrator* 

</td>
<td valign="top">

Create and manage users, assign and approve authorizations

</td>
<td valign="top">

*User & Access Management Administrator* 

</td>
<td valign="top">

`x_uam_UserAdministrator`

`FlexOperator` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

User & Access Management

</td>
<td valign="top">

*User Viewer* 

</td>
<td valign="top">

View users and authorization assignments

</td>
<td valign="top">

*User & Access Management Viewer* 

</td>
<td valign="top">

`x_uam_UserViewer` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Security Administrator* 

</td>
<td valign="top">

Manage certificates and service keys, view landscape objects

</td>
<td valign="top">

*Landscape Management Security Administrator* 

</td>
<td valign="top">

`x_landscape_SecurityAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Security Viewer* 

</td>
<td valign="top">

View and download certificates and service keys, view landscape objects

</td>
<td valign="top">

*Landscape Management Security Viewer* 

</td>
<td valign="top">

`x_landscape_SecurityViewer` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Access Controller* 

</td>
<td valign="top">

View landscape objects \(subject to access control\) and manage access control

</td>
<td valign="top">

*Landscape Management Access Controller* 

</td>
<td valign="top">

`x_landscape_AccessController` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Access Viewer* 

</td>
<td valign="top">

View landscape objects and view access control

</td>
<td valign="top">

*Landscape Management Access Viewer* 

</td>
<td valign="top">

`x_landscape_AccessViewer` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Administrator* 

</td>
<td valign="top">

Create and manage landscape objects

</td>
<td valign="top">

*Landscape Management Administrator* 

</td>
<td valign="top">

`x_landscape_Administrator` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Landscape Management

</td>
<td valign="top">

*Landscape Viewer* 

</td>
<td valign="top">

Display landscape objects

</td>
<td valign="top">

*Landscape Management Viewer*

</td>
<td valign="top">

`x_landscape_Viewer` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Tag Management

</td>
<td valign="top">

*Tag Administrator* 

</td>
<td valign="top">

Create, update, merge and centrally delete tags, view tag usage and organize tags into groups

</td>
<td valign="top">

*Tag Management Administrator* 

</td>
<td valign="top">

`x_tag_TagAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Tag Management

</td>
<td valign="top">

*Tag Viewer* 

</td>
<td valign="top">

View tags, tag groups and tag usage

</td>
<td valign="top">

*Tag Management Viewer* 

</td>
<td valign="top">

`x_tag_TagViewer` 

</td>
</tr>
<tr>
<td valign="top">

Cross Topics

</td>
<td valign="top">

Tenant Information

</td>
<td valign="top">

*Tenant Information Viewer* 

</td>
<td valign="top">

View tenant details on memory consumption and outbound API usage

</td>
<td valign="top">

*Tenant Information Viewer* 

</td>
<td valign="top">

`x_tenantinfo_TenantInformationViewer` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Change & Deployment Management

</td>
<td valign="top">

*Change Manager* 

</td>
<td valign="top">

Approve features for production deployment.

This role has to be combined with either the *Project Member* or the *Project Lead* role.

</td>
<td valign="top">

*Change & Deployment Management Change Manager* 

</td>
<td valign="top">

`imp_cdm_ChangeManager` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Change & Deployment Management

</td>
<td valign="top">

*Deployment Manager* 

</td>
<td valign="top">

Deploy transports into test and production systems.

This role has to be combined with either the *Project Member* or the *Project Lead* role.

</td>
<td valign="top">

*Change & Deployment Management Deployment Manager* 

</td>
<td valign="top">

`imp_cdm_DeploymentManagerTest`

`imp_cdm_DeploymentManagerProd`

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Change & Deployment Management

</td>
<td valign="top">

*Developer* 

</td>
<td valign="top">

Create and assign transports and transport references, and create transport of copies.

This role has to be combined with the *Project Viewer* role.

</td>
<td valign="top">

*Change & Deployment Management Developer* 

</td>
<td valign="top">

`imp_cdm_DeveloperCore`

`imp_cdm_StartImplementation`

`imp_cdm_HandoverToTest`

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Process Management

</td>
<td valign="top">

*Process Administrator* 

</td>
<td valign="top">

Create, edit and delete custom solution processes and unlock custom solution process flow diagrams

</td>
<td valign="top">

*Process Management Process Administrator* 

</td>
<td valign="top">

`imp_pm_ProcessAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Process Management

</td>
<td valign="top">

*Process Author* 

</td>
<td valign="top">

Create, edit, and delete custom solution processes

</td>
<td valign="top">

*Process Management Process Author* 

</td>
<td valign="top">

`imp_pm_ProcessAuthor` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Process Management

</td>
<td valign="top">

*Process Hierarchy Author* 

</td>
<td valign="top">

Create, edit, and delete process hierarchy nodes

</td>
<td valign="top">

*Process Management Process Hierarchy Author* 

</td>
<td valign="top">

`imp_pm_ProcessHierarchyAuthor` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Project Management

</td>
<td valign="top">

*Project Administrator* 

</td>
<td valign="top">

Manage projects, deployment plans, tasks, scopes, requirements, features, documents, test cases, defects, tags, and SAP Readiness Check analyses. View process hierarchy nodes.

The permissions of users with this role additionally depend on the access level of the project and the team assignment. For more information, refer to [Configuring Project User Permissions](https://help.sap.com/docs/cloud-alm/setup-administration/project-user-permissions).

</td>
<td valign="top">

*Project & Task Management Administrator* 

</td>
<td valign="top">

`imp_pjm_ProjectAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Project Management

</td>
<td valign="top">

*Project Lead* 

</td>
<td valign="top">

Manage projects, deployment plans, tasks, scopes, requirements, features, documents, test cases, and defects. View process hierarchy nodes and SAP Readiness Check analyses.

The permissions of users with this role additionally depend on the access level of the project and the team assignment. For more information, refer to [Configuring Project User Permissions](https://help.sap.com/docs/cloud-alm/setup-administration/project-user-permissions).

</td>
<td valign="top">

*Project & Task Management Project Lead* 

</td>
<td valign="top">

`imp_pjm_ProjectLead` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Project Management

</td>
<td valign="top">

*Project Member* 

</td>
<td valign="top">

Manage tasks, scopes, requirements, features \([with restrictions](https://help.sap.com/docs/cloud-alm/applicationhelp/features#roles-and-authorizations)\), documents, test cases, and defects. View projects, deployment plans, SAP Readiness Check analyses, and process hierarchy nodes.

The permissions of users with this role additionally depend on the access level of the project and the team assignment. For more information, refer to [Configuring Project User Permissions](https://help.sap.com/docs/cloud-alm/setup-administration/project-user-permissions).

</td>
<td valign="top">

*Project & Task Management Project Member* 

</td>
<td valign="top">

`imp_pjm_ProjectMember` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

Project Management

</td>
<td valign="top">

*Project Viewer* 

</td>
<td valign="top">

View projects, deployment plans, tasks, scopes, process hierarchy nodes, requirements, features, documents, test cases, defects, and SAP Readiness Check analyses

The permissions of users with this role additionally depend on the access level of the project and the team assignment. For more information, refer to [Configuring Project User Permissions](https://help.sap.com/docs/cloud-alm/setup-administration/project-user-permissions).

</td>
<td valign="top">

*Project & Task Management Project Viewer* 

</td>
<td valign="top">

`imp_pjm_ProjectViewer` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

SAP Readiness Check

</td>
<td valign="top">

*Readiness Check Analysis Administrator* 

</td>
<td valign="top">

Create, edit, and delete SAP Readiness Check analyses

</td>
<td valign="top">

*Readiness Check Analysis Administrator* 

</td>
<td valign="top">

`imp_rc_AnalysisAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Implementation

</td>
<td valign="top">

SAP Readiness Check

</td>
<td valign="top">

*Readiness Check Analysis Viewer* 

</td>
<td valign="top">

View all SAP Readiness Check analyses

</td>
<td valign="top">

*Readiness Check Analysis Viewer* 

</td>
<td valign="top">

`imp_rc_AnalysisViewer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Process Monitoring

</td>
<td valign="top">

*Process Monitoring Administrator* 

</td>
<td valign="top">

Maintain global and specific configurations, consume KPIs and the respective process content \(including sensitive data\), and process alerts

</td>
<td valign="top">

*Business Process Monitoring Administrator* 

</td>
<td valign="top">

`ops_bm_ProcessMonitoringAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Process Monitoring

</td>
<td valign="top">

*Process Manager* 

</td>
<td valign="top">

Consume KPIs and the respective process content \(including sensitive data\), process alerts, and maintain specific configurations

Additionally, the access to particular business processes and data criteria can be restricted for users with this role by setting up access groups. For more information, refer to [Creating Access Groups](https://help.sap.com/docs/cloud-alm/applicationhelp/creating-access-groups).

</td>
<td valign="top">

*Business Process Monitoring Process Manager* 

</td>
<td valign="top">

`ops_bm_ProcessManager` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Process Monitoring

</td>
<td valign="top">

*Process Executor* 

</td>
<td valign="top">

Consume KPIs and the respective process content \(including sensitive data\), and process alerts

Additionally, the access to particular business processes and data criteria can be restricted for users with this role by setting up access groups. For more information, refer to [Creating Access Groups](https://help.sap.com/docs/cloud-alm/applicationhelp/creating-access-groups).

</td>
<td valign="top">

*Business Process Monitoring Process Executor* 

</td>
<td valign="top">

`ops_bm_ProcessExecutor` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Process Monitoring

</td>
<td valign="top">

*Process Monitoring Consumer* 

</td>
<td valign="top">

Consume KPIs and the respective process content \(including sensitive data\), and view alerts

Additionally, the access to particular business processes and data criteria can be restricted for users with this role by setting up access groups. For more information, refer to [Creating Access Groups](https://help.sap.com/docs/cloud-alm/applicationhelp/creating-access-groups).

</td>
<td valign="top">

*Business Process Monitoring Consumer* 

</td>
<td valign="top">

`ops_bm_ProcessMonitoringConsumer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Process Monitoring

</td>
<td valign="top">

*Process Monitoring Viewer* 

</td>
<td valign="top">

Consume KPIs and non-sensitive process content, without access to alert information

Additionally, the access to particular business processes and data criteria can be restricted for users with this role by setting up access groups. For more information, refer to [Creating Access Groups](https://help.sap.com/docs/cloud-alm/applicationhelp/creating-access-groups).

</td>
<td valign="top">

*Business Process Monitoring Viewer* 

</td>
<td valign="top">

`ops_bm_ProcessMonitoringViewer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Service Management

</td>
<td valign="top">

*Business Service Management Administrator* 

</td>
<td valign="top">

Create and manage business services, and plan events

</td>
<td valign="top">

*Business Service Management Administrator* 

</td>
<td valign="top">

`ops_bsm_BusinessServiceManagementAdmin` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Business Service Management

</td>
<td valign="top">

*Business Service Management Viewer* 

</td>
<td valign="top">

View business services, their configuration, and the event calendar

</td>
<td valign="top">

*Business Service Management Viewer* 

</td>
<td valign="top">

`ops_bsm_BusinessServiceManagementViewer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Configuration & Security Analysis

</td>
<td valign="top">

*Configuration Monitoring Administrator* 

</td>
<td valign="top">

Administrate managed objects, configuration settings, and display application data

</td>
<td valign="top">

*Configuration Monitoring Administrator* 

</td>
<td valign="top">

`ops_csa_ConfigurationMonitoringAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Configuration & Security Analysis

</td>
<td valign="top">

*Configuration Monitoring Analyst* 

</td>
<td valign="top">

Display application configuration data

</td>
<td valign="top">

*Configuration Monitoring Analyst* 

</td>
<td valign="top">

`ops_csa_ConfigurationMonitoringAnalyst` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Health Monitoring

</td>
<td valign="top">

*Health Monitoring Administrator* 

</td>
<td valign="top">

Create, edit, delete, and manage configuration settings, including the display of monitoring data

</td>
<td valign="top">

*Health Monitoring Administrator* 

</td>
<td valign="top">

`ops_hm_HealthMonitoringAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Health Monitoring

</td>
<td valign="top">

*Health Monitoring Viewer* 

</td>
<td valign="top">

View health overview and metrics of cloud services

</td>
<td valign="top">

*Health Monitoring Viewer* 

</td>
<td valign="top">

`ops_hm_HealthMonitoringViewer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Integration & Exception Monitoring

</td>
<td valign="top">

*Integration Architect* 

</td>
<td valign="top">

Configure integration monitoring

</td>
<td valign="top">

*Integration Monitoring Integration Architect* 

</td>
<td valign="top">

`ops_im_IntegrationArchitect` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Integration & Exception Monitoring

</td>
<td valign="top">

*Integration Owner* 

</td>
<td valign="top">

View the messages in integration monitoring

</td>
<td valign="top">

*Integration Monitoring Integration Owner* 

</td>
<td valign="top">

`ops_im_IntegrationOwner` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Integration & Exception Monitoring

</td>
<td valign="top">

*Integration Owner Sensitive* 

</td>
<td valign="top">

View the messages in integration monitoring, including data defined as sensitive

</td>
<td valign="top">

*Integration Monitoring Integration Owner Sensitive* 

</td>
<td valign="top">

`ops_im_IntegrationOwnerSensitive` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Job & Automation Monitoring

</td>
<td valign="top">

*Job Monitoring Administrator* 

</td>
<td valign="top">

Create, edit, delete, and manage configuration settings, including the display of monitoring data

</td>
<td valign="top">

*Job Monitoring Administrator* 

</td>
<td valign="top">

`ops_jm_JobMonitoringAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Job & Automation Monitoring

</td>
<td valign="top">

*Job Monitoring Consumer* 

</td>
<td valign="top">

View the job monitoring application for the maintained global configurations

</td>
<td valign="top">

*Job Monitoring Consumer* 

</td>
<td valign="top">

`ops_jm_JobMonitoringConsumer` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Real User Monitoring

</td>
<td valign="top">

*Real User Analyst Administrator* 

</td>
<td valign="top">

View utilization and performance of requests, including sensitive data like the user ID, and configure the real user monitoring app

</td>
<td valign="top">

*Real User Monitoring Analyst Administrator* 

</td>
<td valign="top">

`ops_rum_RealUserAnalystAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Real User Monitoring

</td>
<td valign="top">

*Real User Analyst* 

</td>
<td valign="top">

View utilization and performance of requests

</td>
<td valign="top">

*Real User Monitoring Analyst* 

</td>
<td valign="top">

`ops_rum_RealUserAnalyst` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Real User Monitoring

</td>
<td valign="top">

*Real User Analyst Sensitive* 

</td>
<td valign="top">

View utilization and performance of requests, including sensitive data like the user ID

</td>
<td valign="top">

*Real User Monitoring Analyst Sensitive* 

</td>
<td valign="top">

`ops_rum_RealUserAnalystSensitive` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Synthetic User Monitoring

</td>
<td valign="top">

*Scenario Administrator* 

</td>
<td valign="top">

Create, edit, delete, manage configurations and manage global application settings. View performance and availability of scenario executions

</td>
<td valign="top">

*Synthetic User Monitoring Administrator* 

</td>
<td valign="top">

`ops_sum_SyntheticUserMonitoringAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Synthetic User Monitoring

</td>
<td valign="top">

*Scenario Expert* 

</td>
<td valign="top">

Create, edit, delete, and manage configuration settings. View performance and availability of scenario executions

</td>
<td valign="top">

*Synthetic User Monitoring Scenario Expert* 

</td>
<td valign="top">

`ops_sum_SyntheticUserMonitoringExpert` 

</td>
</tr>
<tr>
<td valign="top">

Operations

</td>
<td valign="top">

Synthetic User Monitoring

</td>
<td valign="top">

*Scenario Viewer* 

</td>
<td valign="top">

View performance and availability of scenario executions

</td>
<td valign="top">

*Synthetic User Monitoring Scenario Viewer* 

</td>
<td valign="top">

`ops_sum_SyntheticUserMonitoringViewer` 

</td>
</tr>
<tr>
<td valign="top">

Service

</td>
<td valign="top">

Service Collaboration

</td>
<td valign="top">

*Services Administrator* 

</td>
<td valign="top">

Maintain tenant mapping for receiving service information in your SAP Cloud ALM tenant. View all service information, collaborate in service delivery, and follow up on issues and actions.

Users with this role additionally require the *Project Administrator* role.

</td>
<td valign="top">

*Service Collaboration Administrator* 

</td>
<td valign="top">

`sdc_sc_ServicesAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

Service

</td>
<td valign="top">

Service Collaboration

</td>
<td valign="top">

*Services Expert* 

</td>
<td valign="top">

View all service information, collaborate in service delivery, and follow up on issues and actions.

Users with this role additionally require the *Project Member* role.

</td>
<td valign="top">

*Service Collaboration Expert* 

</td>
<td valign="top">

`sdc_sc_ServicesExpert` 

</td>
</tr>
<tr>
<td valign="top">

Service

</td>
<td valign="top">

Service Collaboration

</td>
<td valign="top">

*Services Viewer* 

</td>
<td valign="top">

View all service information, including preparation tasks, notes, attachments, service results, and issues and actions.

Users with this role additionally require the *Project Viewer* role.

</td>
<td valign="top">

*Service Collaboration Viewer* 

</td>
<td valign="top">

`sdc_sc_ServicesViewer` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Cycle & Monitoring

</td>
<td valign="top">

*Cycle Administrator* 

</td>
<td valign="top">

Manage cycles, run cycles and migrations

</td>
<td valign="top">

*Cycle & Monitoring Administrator* 

</td>
<td valign="top">

`btc_cm_CycleAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Cycle & Monitoring

</td>
<td valign="top">

*Cycle Viewer* 

</td>
<td valign="top">

View cycles and all included information

</td>
<td valign="top">

*Cycle & Monitoring Viewer* 

</td>
<td valign="top">

`btc_cm_CycleViewer` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Modeling

</td>
<td valign="top">

*Transformation Modeling Expert* 

</td>
<td valign="top">

Maintain transformation models and transformation model versions, as well as view all included information regarding the transformation project

</td>
<td valign="top">

*Transformation Modeling Expert* 

</td>
<td valign="top">

`btc_modeling_Expert` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Modeling

</td>
<td valign="top">

*Transformation Modeling Viewer* 

</td>
<td valign="top">

View transformation models and all included information regarding the transformation project

</td>
<td valign="top">

*Transformation Modeling Viewer* 

</td>
<td valign="top">

`btc_modeling_Viewer` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Scoping

</td>
<td valign="top">

*Digital Blueprint Administrator* 

</td>
<td valign="top">

Create and edit digital blueprints and all associated tasks, company code scoping, and transformation object scoping

</td>
<td valign="top">

*Digital Blueprint Administrator* 

</td>
<td valign="top">

`btc_bdts_DigitalBlueprintAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Scoping

</td>
<td valign="top">

*Digital Blueprint Viewer* 

</td>
<td valign="top">

Consume digital blueprint content, view company code scoping and transformation object scoping

</td>
<td valign="top">

*Digital Blueprint Viewer* 

</td>
<td valign="top">

`btc_bdts_DigitalBlueprintViewer` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Transformation

</td>
<td valign="top">

*Transformation Project Administrator* 

</td>
<td valign="top">

Create and edit transformation projects and all associated tasks

</td>
<td valign="top">

*Transformation Project Administrator* 

</td>
<td valign="top">

`btc_transformation_TransformationProjectAdministrator` 

</td>
</tr>
<tr>
<td valign="top">

SAP Business Transformation Center

</td>
<td valign="top">

Transformation

</td>
<td valign="top">

*Transformation Project Viewer* 

</td>
<td valign="top">

Consume and edit transformation projects and all associated tasks

</td>
<td valign="top">

*Transformation Project Viewer* 

</td>
<td valign="top">

`btc_transformation_TransformationProjectViewer` 

</td>
</tr>
</table>

