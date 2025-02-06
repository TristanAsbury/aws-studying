#IAM 

## **What Are IAM Groups?**

IAM Groups are **collections of related IAM identities** (users) that help you manage permissions and policies more efficiently.

- **Purpose:**
    - 👨‍💻 **Team Organization:**
        - Examples: Development Team, Finance, HR, etc.
    - 📦 **User Containers:**
        - Serve as containers for **IAM users** to simplify managing large numbers of users.

---

## **Key Benefits**

- **Simplified Policy Management:**
    - 📜 **Apply Policies in Bulk:**
        - Attach policies to the group, and every user in that group inherits those policies.
- **Ease of Administration:**
    - 🛠️ **Organized User Management:**
        - Managing permissions for a large set of users becomes easier by grouping them logically.

---

## **Important Characteristics**

- **No Direct Login:**
    - 🚫 **Groups Cannot Log In:**
        - Groups have **no credentials** and cannot be used to log into AWS.
- **Policy Attachment:**
    - 🔒 **Attach Policies to Groups:**
        - **Inline Policies** and **Managed Policies** can be attached to groups.
    - 📝 **Individual Policies:**
        - Users in groups can also have their **own inline policies** attached, in addition to the group’s policies.

---

## **Limitations & Considerations**

- **Group Limits:**
    - 🔢 **Maximum Groups:**
        - Each AWS account has a default limit of **300 groups** (this can be increased via a support ticket).
- **Not a True Identity:**
    - 🚷 **Cannot Be Referenced as a Principal:**
        - IAM Groups are **not true identities**; they cannot be referenced directly as a principal in a policy.
- **User Capacity:**
    - 👥 **Unlimited Users per Group:**
        - There is no limit on the number of users in a group. All 5,000 users in an account can belong to a single group if needed.

---

## **Quick Recap**

- **IAM Groups:**
    - Containers for related IAM users (e.g., teams like Development, Finance, HR).
- **Benefits:**
    - Simplifies policy management and user organization.
- **Key Points:**
    - Groups cannot log in or have credentials.
    - Both inline and managed policies can be attached to groups.
    - Default limit: 300 groups per account (adjustable via support).
    - Groups are not true identities and cannot be used as a principal in policies.