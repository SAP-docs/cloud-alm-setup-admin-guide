<!-- loioe9134c5eb1bf40cc8d4fea1d0d25252a -->

# Development and Product Security

SAP applies the following measures to make SAP Cloud ALM safe for you to use.



-   **Security Scans - SAST and FOSS**:

    -   SAP performs daily scans for static application security testing \(SAST\).

    -   SAP scans daily for vulnerabilities in the used free and open-source software \(FOSS\).


-   **Threat Modeling**:

    -   For every new app and every new functionality, threat modeling is mandatory.

    -   New software is only released after all risks are mitigated.


-   **Security Validation**: Regular security validations ensure that security requirements are fulfilled.

-   **Hacker Simulation and Penetration Test**: Regular external penetration tests enhance protection from outside attacks.

-   **Bug Bounty**: Constant security testing by external security researchers.

-   **Compliance Standards**:

    -   SAP Cloud ALM is compliant with SAP-internal technical policies, procedures, directives, guidelines, and product standards, such as the directive for network device security and the directive for cloud infrastructure.

    -   Employees and operators are bound to the SAP code of business conduct and other behavioral security standards, such as clean desk and communication.


-   **Security Product Standards**: SAP Cloud ALM follows the general SAP security product standards.

-   **Certifications and Compliance**: SAP Cloud ALM is certified for ISO 27001 and ISO 9001.

-   **Security Incident Management**:

    -   An emergency plan for sudden security incidents is in place.

    -   Security incidents are handled according to the Security Incident Management Process. This process foresees classification, containment, and resolving of the issue. Internal groups and decision-makers are involved as needed.


-   **Security Education and Awareness**: SAP employees that are involved in SAP Cloud ALM are regularly trained on the importance of security. Software developers are trained for secure programming.




### Product Security

-   Audit logs provide security-relevant logging. They can also be accessed through third-party tools. More under [Change Log and Audit Log](https://help.sap.com/docs/cloud-alm/setup-administration/change-audit-logging).

-   SAP Cloud ALM provides security configuration recommendations to empower you to make informed security-related decisions. More under [Security Configuration Recommendations](https://help.sap.com/docs/cloud-alm/setup-administration/security-configuration-recommendations).
-   The ability of users to access certain types of data and to perform certain activities in SAP Cloud ALM can be managed with role collections. More under [Role Collections](https://help.sap.com/docs/cloud-alm/setup-administration/role-collections).
-   Connections are encrypted with TLS 1.3, X.509 authentication.
-   Geo blocking and blocking of sanctioned persons and organizations are in place.
-   Data at rest is encrypted.
-   SAP HANA databases are regularly backed up. More:
    -   [Backup and Recovery \(SAP HANA Cloud\)](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-administration-guide/backup-and-recovery)

    -   [Resilience, High Availability, and Disaster Recovery \(SAP BTP\)](https://help.sap.com/docs/btp/sap-business-technology-platform/resilience-high-availability-and-disaster-recovery)


-   For the time being, tenant-specific data recovery is not available.
-   Physical security is ensured by hyperscalers.
-   Uploaded files are scanned for malware.
-   Free text input is sanitized.
-   Denial of service attacks are prevented.
-   Session timeout is enabled.



### Data Protection and Privacy

SAP Cloud ALM is compliant with DSGVO and GDPR.

-   Only limited personal data is stored: first name, last name, and email address.

-   Information retrieval, edit, and deletion is possible and documented in [User Data from SAP Cloud ALM](03_DPP/user-data-from-sap-cloud-alm-65c98de.md).

-   Data is anonymized after an employee leaves the company. Then, the data is only visible for auditors with special authorization.

-   Hyperscalers can't access personal data.

-   EU access and SAP NS2 aren't supported.


More under [Data Protection and Privacy](03_DPP/data-protection-and-privacy-2fdc2f0.md).

