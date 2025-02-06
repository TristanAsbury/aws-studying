#IAM

## **What Are IAM Roles?**

An **IAM Role** is an [[IAM Identity]] that you can **assume** to gain temporary security credentials. Unlike IAM Users, which are tied to a single long-term identity, **IAM Roles are designed to be assumed by multiple entities** (humans, applications, services) on a temporary basis.

---
## **Key Characteristics**

- **Versatile Usage:**
    - 🔄 **For AWS Services & External Access:**
        - Roles can be used by AWS services (e.g., EC2, Lambda) or to grant external entities access to your account.
    - 👥 **Multiple Principals:**
        - Designed for situations where an **unknown or varying number of principals** (users, applications, or services) require access.
    - ⏱️ **Temporary Credentials:**
        - Roles are intended for **short-term use**. When assumed, they provide temporary credentials that expire, after which the role must be re-assumed.
- **Not Like IAM Users:**
    - ❌ **No Permanent Credentials:**
        - Unlike IAM Users, roles do not have long-term credentials like passwords or access keys.
    - 🔄 **Borrowed Permissions:**
        - When you assume a role, you **borrow its permissions** for a short period, making it ideal for dynamic access management.

---

## **Components of an IAM Role**

IAM Roles have two key policy types:

1. **Trust Policy (Role Trust Policy):**
    - 📜 **Defines Who Can Assume the Role:**
        - Specifies the **trusted entities** (principals) that are allowed to assume the role.
        - Can include:
            - IAM Users and Roles within the same account.
            - Identities in **other [[AWS Account|AWS Accounts]]**.
            - **Anonymous users** (in certain controlled cases).
    - 🔄 **Assumption Conditions:**
        - You can set conditions to control how and when the role can be assumed.
2. **Permissions Policy:**
    - 🔒 **Grants Permissions:**
        - Specifies **what actions** are allowed (or denied) when the role is assumed.
        - Works like any other [[IAM Policy]] attached to a user, but applies to the temporary security credentials issued when the role is assumed.

---

## **How IAM Roles Work**

1. **Assuming a Role:**
    - 🛠️ **Using STS (Security Token Service):**
        - When a principal (user, service, or application) needs to use a role, they call STS to **assume the role**.
    - 🔑 **Temporary Credentials Issued:**
        - STS returns temporary security credentials (Access Key ID, Secret Access Key, and Session Token) valid for a limited duration.
    - ⏲️ **Expiration & Renewal:**
        - Once the credentials expire, the principal must **assume the role again** if continued access is required.
2. **Role Usage Scenarios:**
    - 🌍 **External Access:**
        - Granting third-party services or federated users access to your AWS resources.
    - ☁️ **Service Roles:**
        - Allowing AWS services (like EC2 or Lambda) to perform actions on your behalf.
    - 🔄 **Dynamic Environments:**
        - Ideal when the number of users or services needing the access is unknown or exceeds the limits for IAM Users.

---

## **When to Use IAM Roles**

## **1. Unknown or Large Numbers of Principals**

- **Dynamic Access Needs:**
    - 👥 When you **cannot determine or limit the number of principals** (users, applications, services) that need access, roles are ideal.
    - 🌐 **Scalability:**
        - If the potential number of principals exceeds typical limits (or is unknown), using roles lets you grant temporary permissions without managing a long list of static identities.

## **2. Short-Term Access Needs**

- **Temporary Tasks & Operations:**
    - ⏱️ Roles are perfect when access is needed **temporarily** – for example, when running an application, performing a batch job, or handling short-term processes.
    - 🔄 **Ephemeral Permissions:**
        - When a process requires permissions for only a short duration, the role provides the necessary access and then expires, keeping your environment secure.

## **3. Enhanced Security**

- **Minimizing Credential Exposure:**
    - 🔐 Roles eliminate the need for **long-term credentials** (like hard-coded access keys), thereby reducing the risk of credential exposure.
    - 🚀 **Borrowed Permissions:**
        - By "borrowing" permissions temporarily through a role, you minimize the risk associated with static credentials and simplify credential rotation.

## **4. AWS Service Roles – Most Common Use Case**

- **AWS Services Operating on Your Behalf:**
    - 🤖 **Service Integration:**
        - Many AWS services (e.g., EC2, Lambda, etc.) use roles to perform actions on your behalf.
    - **Example: AWS Lambda**
        - **Lambda Invocation:**
            - When a Lambda function runs, it **assumes a Lambda Execution Role**.
            - The trust policy for this role allows AWS Lambda to call `sts:AssumeRole`, generating **temporary credentials** for the runtime environment.
            - 🔄 **Secure Execution:**
                - Without roles, you would need to hardcode access keys into your code—a significant security risk that also complicates updates.

## **5. Emergency or "Break Glass" Situations**

- **Contingency Access:**
    - 🚨 **Emergency Access:**
        - In situations where critical teams (e.g., the Senior Tech Team) are unavailable, a **"Break Glass" role** can be assumed by Helpdesk or backup personnel.
    - **Tiered Permissions:**
        - For instance, Helpdesk might typically have read-only access, but in emergencies, they can assume an emergency role that grants higher, more destructive permissions to resolve urgent issues.

## **6. Integrating AWS into an Existing Corporate Environment**

- **Identity Federation with External IdPs:**
    - 🏢 **Corporate Integration:**
        - When an organization has an existing identity provider (IdP) like Microsoft Active Directory, roles can be set up to allow these external identities to assume roles in AWS.
    - **How It Works:**
        - External users from your corporate directory can assume an IAM role, receive temporary credentials via STS, and access AWS resources without creating separate AWS identities.
    - 🔗 **Single Sign-On (SSO):**
        - This approach supports SSO and can scale to manage thousands of identities, streamlining access management across your organization.

## **7. Large-Scale Applications (e.g., Ride Sharing Apps)**

- **Handling Millions of Users:**
    - 🚗 **Web Identity Federation:**
        - Large-scale applications with millions of users often let customers sign in using existing identities (Google, Facebook, Twitter, etc.).
    - **Advantages:**
        - **No AWS Credentials in the App:**
            - Temporary credentials are provided through roles, which is highly secure.
        - **Utilizing Existing Customer Logins:**
            - Leverages familiar login methods for users, improving user experience.
        - **Scalability:**
            - Can easily scale to handle hundreds of millions of users without the overhead of managing AWS-specific identities.

## **8. Cross-Account Access**

- **Multi-Account Environments:**
    - 🔄 **Seamless Collaboration:**
        - In scenarios where different AWS accounts need to interact (e.g., a partner company and your organization), roles facilitate secure cross-account access.
    - **Example:**
        - If a partner's application needs to store data in their S3 bucket, they can create a role that your account's identities can assume.
        - **Benefit:**
            - This avoids duplicating thousands of identities in the partner account while securely transferring data.
---

## **Quick Recap**

- **IAM Roles:**
    - **Temporary identities** that provide **temporary credentials**.
    - **Designed for multiple entities** (AWS services, users, external accounts) to assume.
- **Two Main Policies:**
    - **Trust Policy:** Defines who can assume the role.
    - **Permissions Policy:** Specifies what actions the role permits.
- **Operational Flow:**
    - Assumed via **STS**, temporary credentials are issued, and upon expiration, the role must be re-assumed.
- **Ideal Use Cases:**
    - External access, AWS service roles, and dynamic environments with many principals.