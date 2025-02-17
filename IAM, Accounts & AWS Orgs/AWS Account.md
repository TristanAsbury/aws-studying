- An **AWS Account is a container** for [[IAM Identity|Users/Identities]] or Resources
- When creating an AWS Account you provide: 
	- an account name (e.g. PROD)
	- a unique email address 
	- a credit card
		- Resources bill to the AWS Account payment method as they are consumed.
- When creating an account, the first identity is the *[[IAM root user]]*
- AWS Accounts can contain the impact of admin errors, or exploits by bad actors. Use separate accounts for separate things (DEV, TEST, PROD) or teams or products or clients.
