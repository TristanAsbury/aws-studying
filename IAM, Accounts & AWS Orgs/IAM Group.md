#IAM 

- Groups of related [[IAM Identity]]. E.g. development team, finance, HR, etc.
- Containers for [[IAM User|users]]
- Exist to make organizing large groups of users easier
- Cannot log into groups, Have no credentials
- No limit on users in a single group, all 5,000 users could be in there
- Groups can have policies attached to them
	- Inline
	- Managed
	- Nothing stopping the users in the groups from having their own inline policies attached to them
- Limitations
	- No groups
	- 