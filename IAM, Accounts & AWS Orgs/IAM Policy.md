#IAM 

> [!NOTE] Definition
> IAM policies define permissions for an action regardless of the method that you use to perform the operation. For example, if a policy allows the [GetUser](https://docs.aws.amazon.com/IAM/latest/APIReference/API_GetUser.html) action, then a user with that policy can get user information from the AWS Management Console, the AWS CLI, or the AWS API. When you create an [[IAM Identity|IAM User]], you can choose to allow console or programmatic access. If console access is allowed, the IAM user can sign in to the console using their sign-in credentials. If programmatic access is allowed, the user can use access keys to work with the CLI or API.

- Set of security statements to AWS
- Grants access or denies access to AWS products or features
- Created using JSON

![[Pasted image 20250205192145.png]]
***
# Types of Policies

### Inline Policies
Applying 3 individual policies to three identities simultaneously. Not best practice. Changing access rights would mean changing all of those policies.

- Special or Exceptional Allow or Deny
### Managed Policies
- One single policy that is attached to all identities. 
- Reusable. 
- **SHOULD BE USED BY DEFAULT** 

***
# Accessing Resources
When trying to access a resource, the [[IAM Identity|Identity]] has to prove who they are. Once they are permitted, that identity is known as an **Authenticated Identity**. AWS knows which policies an Identity has, and it could be multiple. Each policy could have multiple statements in them.

***
# Policy Statement

![[Pasted image 20250205192546.png]]
### What makes up a statement?
1. **Sid** - Optional field which identifies a statement and what it does. In this case, denies access to the cat bucket
2. **Action** - Matches one or more actions, in format of `<service>:<action>`
3. **Effect** - Whether to allow or deny. Controls what AWS to do if the action and resource match.
4. **Resource** - The resource to which the statement applies, using ARN

### Overlapping Statements
1. If there is an explicit deny, then it rules over anything else with the same action and resource. THE DENY ALWAYS WINS.