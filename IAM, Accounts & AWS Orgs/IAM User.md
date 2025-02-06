>[!NOTE] Definition
>An IAM user is an identity used for anything requiring long-term AWS access e.g. Humans, Applications, or service accounts

## IAM User: Definition and Key Points

### **What Is an IAM User?**

- **Definition:**  
    An IAM (Identity and Access Management) user is an identity within AWS that is used for **long-term access** to AWS resources.
    - **Who/What Can Use an IAM User?**
        - **Humans:** Developers, system administrators, or any AWS users who require persistent access.
        - **Applications:** Software that needs to interact with AWS APIs.
        - **Service Accounts:** Non-human entities (services or daemons) that run within your environment.

### **Key Characteristics:**
- **Long-Term Credentials:** Unlike temporary credentials (e.g., those provided via roles), IAM users have long-term credentials that can include passwords and access keys.
- **Policy Attachment:** Permissions for IAM users are defined by attaching IAM policies either directly to the user, via groups, or through roles.

---

## Limitations of IAM Users

Understanding these limitations is crucial when designing scalable AWS architectures:

1. **User Count Limit:**
    - **Maximum of 5,000 IAM Users per AWS Account**
        - **Design Implication:**
            - For organizations that require more than 5,000 identities (for example, large enterprises or in cases of mergers), managing one IAM user per individual may not be feasible.
            - **Alternative Approaches:**
                - **Federation:** Integrate with external identity providers (IdPs) like Active Directory or SAML-based systems.
                - **IAM Roles:** Use roles to delegate permissions without needing a long-term identity for every entity.
2. **Group Membership Limit:**
    - **An IAM User can be a member of at most 10 Groups**
        - **Design Consideration:**
            - When assigning policies and permissions, plan group hierarchies carefully to avoid hitting this limit.
            - Over-reliance on group memberships may require redesigning how permissions are organized across your users.

---

## Design Impacts and Best Practices

- **Scalability Concerns:**
    - If your system's design anticipates more than 5,000 distinct identities, consider integrating **federated access** or **IAM roles** instead of creating individual IAM users for every entity.
- **Federation vs. IAM Users:**
    - **Federation:**
        - Allows users to access AWS resources using their existing corporate credentials.
        - Reduces management overhead by not requiring the creation of separate AWS identities for every user.
    - **IAM Roles:**
        - Provide temporary credentials for AWS services and applications.
        - Facilitate secure cross-account access without sharing long-term credentials.
- **Group Management:**
    - Keep group assignments simple.
    - Organize permissions around roles and responsibilities rather than individual user policies.
    - Monitor and audit group memberships to ensure they remain within the allowed limit and adhere to your security policies.