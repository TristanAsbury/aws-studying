#IAM 
## **What Are SCPs?**

**Service Control Policies (SCPs)** are a core feature of [[AWS Organizations]] used to **restrict the maximum available permissions** for accounts within your organization. They act as permission boundaries that limit what users, roles, and even the account's root user can do, regardless of the permissions granted by individual [[IAM Policy|IAM Policies]].

- 🔒 **Permission Boundaries:**
    - SCPs **limit** what actions can be performed, rather than granting permissions.
    - They work in conjunction with IAM policies. Only actions allowed by both the SCP and the IAM policy are permitted.

---

## **Key Features of SCPs**

- **Policy Document (JSON):**
    - 📝 SCPs are defined using **JSON policy documents** that follow the same syntax as IAM policies.
- **Attachment Options:**
    - 📂 **Organization-Wide:**
        - You can attach an SCP to the **entire organization** to enforce a baseline of security and compliance.
    - 📁 **Organizational Units (OUs):**
        - Attach SCPs to one or more **OUs**. All accounts in the OU inherit the SCP.
    - 🖥 **Individual AWS Accounts:**
        - SCPs can also be directly attached to individual AWS accounts.
- **Inheritance Down the Organizational Tree:**
    - 🌳 SCPs propagate **down the hierarchy**. If an SCP is attached to a parent OU, every child OU and account inherits it—ensuring consistent control across your organization.
- **Management Account Exceptions:**
    - 👑 **Management Account (formerly Master Account):**
        - Even if an SCP is attached to the management account, the management account itself is **not affected** by SCP restrictions.
        - **Best Practice:** Avoid using the management account for running production resources to prevent unintended access issues.

---

## **How SCPs Work**

- **Permission Boundary Concept:**
    - 📏 SCPs define the **maximum available permissions** for an account.
    - Even if an IAM policy in the account allows an action, if the SCP denies it, the action is **blocked**.
- **Effect on Account [[IAM root user|Root User]]:**
    - 🛑 By default, AWS does not restrict the root user with IAM policies alone. However, within an AWS Organization, an SCP can restrict **all principals** within the account, including the root user.
- **Default SCP Behavior:**
    - ⚙️ When you create an organization, AWS automatically applies a **default SCP** that grants full AWS access to all accounts.
    - You can then modify this default behavior to either tighten controls or apply an allow/deny list.
- **Operational Modes:**
    - 🔍 **Allow List (Block by Default):**
        - Start with a default-deny policy and then **explicitly allow** only specific services or actions.
    - 🚫 **Deny List (Allow by Default):**
        - Start with full access and then **explicitly deny** particular services or actions.
- **Policy Evaluation:**
    - ✅ For a request to be allowed, it must be permitted by **both** the IAM policy attached to the identity **and** the active SCP on the account.
    - ❌ If an action is not explicitly allowed by both, it is **denied**.
    - ![[Pasted image 20250206100826.png]]

---

## **Use Cases & Scenarios**

### **1. Enforcing Security & Compliance**

- **Restrict Critical Actions:**
    - 🔒 Ensure that no account can perform high-risk operations (like deleting production data or changing key configurations) even if an IAM policy inadvertently grants such permissions.
- **Control Regional Access:**
    - 🌍 Limit access so that certain actions can only be performed from specific regions or under specific conditions (e.g., where data residency requirements exist).

### **2. Managing Large AWS Platforms**

- **Consistent Governance Across Multiple Accounts:**
    - 🏢 For organizations with hundreds or thousands of accounts, SCPs provide a centralized mechanism to enforce security, compliance, and operational policies.
- **Organizational Hierarchy Management:**
    - 📂 Use OUs to group accounts by business unit, environment (development, testing, production), or regulatory requirements, and apply tailored SCPs to each group.

### **3. Emergency and "Break Glass" Scenarios**

- **Emergency Overrides:**
    - 🚨 In rare cases, you might allow temporary elevated permissions (via a “break glass” process) while ensuring that regular operations remain within strict SCP boundaries.

---

## **Best Practices for SCPs**

- **Start with Least Privilege:**
    - 🔍 Design SCPs to enforce the **principle of least privilege**. Only allow actions that are **absolutely necessary**.
- **Test Before Deployment:**
    - 🧪 Always test new SCPs in a sandbox environment or on a small subset of accounts to ensure they don’t inadvertently block required actions.
- **Document & Audit:**
    - 📜 Keep thorough documentation of all SCPs and regularly audit them to ensure they continue to meet your organizational requirements.
- **Limit Changes in Production:**
    - 🚦 Make changes to SCPs in a controlled manner, as they affect all users and roles in an account, including the root user.
- **Avoid Over-Restricting the Management Account:**
    - 👑 Since the management account is not affected by SCPs, it should be used solely for organizational management and not for running workloads.

---

## **Quick Recap**

- **SCPs are JSON policy documents** that define the maximum permissions available within an AWS Organization.
- They can be attached at the organization level, to OUs, or individual accounts, and they **inherit down the organizational tree**.
- SCPs **do not grant permissions**; they limit what permissions can be used even if allowed by IAM policies.
- **Management accounts** are exempt from SCP restrictions—so avoid using them for running critical resources.
- **Use cases include** enforcing security, managing large platforms, and ensuring compliance across multiple AWS accounts.
- **Best practices:** Start with least privilege, test thoroughly, document changes, and use emergency “break glass” processes when necessary.



