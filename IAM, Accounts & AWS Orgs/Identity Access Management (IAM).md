#IAM #Service 

## **Overview**

- **Purpose:**  
    IAM manages [[IAM Identity|Identities]], [[IAM Role|Roles]], and [[IAM Group|Groups]], and acts as an Identity Provider (IDP) for your [[AWS Account]]. It is used to authenticate and authorize access to AWS resources.
    
- **Global Resilience:**  
    Every AWS account includes a running instance of IAM that is [[Globally Resilient]]. This means IAM data is secure and consistent across all AWS Regions.
    
- **Account Trust Model:**
    - **Internal Trust:** Each AWS account trusts only its own IAM instance.
    - **External Control:** You do not have direct control over external accounts or users through your IAM instance.

---
## **Key IAM Functions**

1. **Authentication:**
    - **What It Does:** Proves that a user or service is who it claims to be.
    - **How It Works:**
        - A principal (e.g., a person, service, or application) makes a request to IAM.
        - The principal provides credentials such as:
            - **For Humans:** Username, password, and often Multi-Factor Authentication (MFA).
            - **For Applications/CLI:** Access keys.
        - Upon successful verification, the principal becomes an _Authenticated Identity_.
2. **Authorization:**
    - **What It Does:** Determines whether the authenticated identity has permission to perform a specific action on a resource.
    - **How It Works:**
        - Once authenticated, the IAM system checks the identity's associated [[IAM Policy]].
        - These policies define allowed or denied actions on AWS resources.

---

## **Principal and Identity**

- **Principal:**  
    Any entity that can make a request to AWS, including:
    - **People:** Human users.
    - **Services:** AWS services acting on your behalf.
    - **Applications:** Software or scripts making API calls.
    - **Other Entities:** Any system or process that can be authenticated.
- **Authenticated Identity:**  
    A principal that has successfully passed IAM's authentication process. Only after this step will the IAM policies be evaluated for authorization.
    
