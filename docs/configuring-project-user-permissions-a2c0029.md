<!-- loioa2c0029b94784563898f797138068f0b -->

# Configuring Project User Permissions

Assign project access levels and project roles in the *Projects and Setup* app to control the access to and ability to display or change application objects in SAP Cloud ALM for implementation apps.

Project user authorizations are defined by a combination of the project access levels, the roles users are assigned to in the user management, and the roles users are assigned to in project management.

In the *Projects and Setup* app, three access levels can be determined in a project:

-   *Public*: This project is publicly accessible by all users with project management authorizations.

-   *Restricted*: This project is restricted and only project members can make changes within the project \(display for non-project-members allowed\).

-   *Private*: This project is private and can only be accessed by project members \(display for non-project-members not allowed\).


> ### Note:  
> When a project is created, the access level is set to *Restricted* by default. This can be changed later.

Within each access level, the combination of role assignments in *User Management* and the team assignment in a project defines the project permissions for a user.

You can find the available authorization roles for project management under [Role Collections](https://help.sap.com/docs/cloud-alm/setup-administration/role-collections?table_cj5_kfp_jgb-capability=Project%20Management).

In the *Projects and Setup* app, users can be assigned to teams based on numerous roles, such as Project Lead, Analytics Expert, Business Process Expert. As soon as a user is assigned, a request is triggered in *User Management* to assign the user to the respective role collection.

Please refer to the below table to get detailed information.

![](images/Access_Level_Matrix_ccbc066.jpg)

The first column of the table shows the three access levels that can be determined during project setup in the *Projects and Setup* app. The second column shows the team assignment type. The rest of the columns shows the different roles a user can be assigned to in the *User Management* app. In the table legend, the different authorizations are defined that result from the user assignments and project access level settings in the different apps.

When you set the access level for a project to *Public*, user authorizations are only affected by the roles that are assigned in *User Management*. This is not the case for the access levels *Restricted* and *Private*. Here, user authorizations are both affected by the roles that are assigned in *User Management* and the team assignments made in the *Projects and Setup* app.

> ### Note:  
> Any authorization changes to projects or assignments to projects or teams only apply to the individual users after they have logged out of SAP Cloud ALM.

