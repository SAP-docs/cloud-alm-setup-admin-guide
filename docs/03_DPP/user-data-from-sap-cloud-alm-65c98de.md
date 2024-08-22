<!-- loio65c98de8ac484ad4896b051e2c985ee1 -->

# User Data from SAP Cloud ALM

The following types of personal data are stored in SAP Cloud ALM:

-   First and last name

-   Email address

-   User ID


Hyperscalers, on which SAP products are running, can't access personal data.

> ### Note:  
> Some APIs expose personal data from SAP Cloud ALM if the data is linked to relevant application objects, for example, the user responsible of a feature. For more information, see the respective API reference documentation in the [API Guide for SAP Cloud ALM](https://help.sap.com/docs/cloud-alm/apis).



<a name="loio65c98de8ac484ad4896b051e2c985ee1__section_vcv_fk3_2tb"/>

## Finding User Data

A user with the *User Administrator* role can find all user data in the *User Management* app in SAP Cloud ALM.

Apart from this user record, personal data in SAP Cloud ALM exists in form of personalization configuration and in relation to application objects \(such as projects, tasks, and alerts\). These objects have their own lifetime and retention periods, independent of the users.



<a name="loio65c98de8ac484ad4896b051e2c985ee1__section_oks_bk3_2tb"/>

## Deleting or Deactivating User Data

To protect the personal data of offboarded users, the user administrator can deactivate the user record within SAP Cloud ALM. If the SAP BTP account is integrated into a central identity management via the Identity Provisioning service, this also happens automatically if the user is deleted from the Identity Authentication tenant. To keep the link between application objects and users even after a user was offboarded, the user-related data is kept for auditability purposes \(for example, to see who performed a particular task, executed a test case, or made a certain configuration\).

However, this automatic deactivation is done only after a grace period of 30 days. This prevents an accidental automatic user deactivation while changing the settings in the Identity Authentication service. During this period, deactivated users aren't authorized to use SAP Cloud ALM, but their personal settings and tasks assignments are still valid after changing the settings in the Identity Authentication service.

When a user is deactivated in SAP Cloud ALM, all role assignments to the user are deleted and personalized data is removed. The person-related data of deactivated users is only visible for users with the role *User Administrator* or *Global Auditor*. To all other users, the deactivated user is anonymized.

The user's identity in the identity provider and a mapping of user groups to roles \(if available\) aren't affected by this. Therefore, if the user is still active in the Identity Authentication tenant and still has authorizations, for example, because of a group mapping, a deactivated user can still sign in to SAP Cloud ALM. In this case, the user is reactivated and the personal data becomes visible again to all users in the respective SAP Cloud ALM applications.

User records can also be deleted by the user administrator after the deactivation. However, deletion isn’t recommended when the user has worked in SAP Cloud ALM, since it’s more difficult to trace back actions to the user. Dependent data, that is, application objects that the user has worked on, have their own lifetime and are deleted according to their own deletion concept.

Only if the SAP Cloud ALM account is closed and deleted, all data is deleted as well.

