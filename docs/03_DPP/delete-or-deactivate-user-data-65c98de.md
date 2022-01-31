<!-- loio65c98de8ac484ad4896b051e2c985ee1 -->

# Delete or Deactivate User Data

Since customers have a legitimate interest to keep the link between application objects and users, even after the user was offboarded, the user-related data is kept for auditability purposes \(for example, to see who performed a particular task, executed a test, or made a certain configuration\).

In order to protect the personal data of offboarded users, the user administrator can deactivate the user record within SAP Cloud ALM. If the SAP BTP account of the customer is integrated into a central identity management via the Identity Provisioning service, this also happens automatically if the user is deleted from the Identity Authentication tenant.

However, this automatic deactivation is done only after a grace period of 30 days. This prevents an accidental automatic user deactivation while changing the settings in the Identity Authentication service. During this period, deactivated users aren't authorized to use SAP Cloud ALM, but their personal settings and tasks assignments are still valid after changing the settings in the Identity Authentication service.

When a user is deactivated in SAP Cloud ALM, all role assignments to the user are deleted and personalized data is removed. The person-related data of deactivated users is only visible for users with the role *User Administrator* or *User Auditor*. To all other users, the deactivated user is anonymized.

The user's identity in the identity provider and a mapping of user groups to roles \(if available\) aren't affected by this. Therefore, if the user is still active in the Identity Authentication tenant and still has authorizations, for example, because of a group mapping, a deactivated user can still log on to SAP Cloud ALM. In this case, the user is reactivated and the personal data becomes visible again to all users in the respective SAP Cloud ALM applications.

User records can also be deleted by the user administrator after the deactivation. However, deletion isn’t recommended when the user has worked in SAP Cloud ALM, since it’s more difficult to trace back actions to the user. Dependent data, that is, business objects that the user has worked on, have their own lifetime and are deleted according to their own deletion concept.

Only if the SAP Cloud ALM account is closed and deleted, all data is deleted as well.

