A VPC is a Virtual Network inside AWS. A VPC is within 1 account and 1 region. 
- Regionally Resilient
- VPCs are private and isolated unless configured otherwise
- Service instances can be put inside these VPCs, and they will be isolated and only be able to communicate if configured so

# Types of VPCs

#### Default VPC
- One default VPC per [[Region]]
- CAN BE DELETED AND RECREATED FROM CONSOLE UI
- They always have the same IP range and same '1 subnet per AZ' architecture.
- Preconfigured to have one subnet in every [[Availability Zone]].
- Default VPC CIDR is always 172.31.0.0/16
- /20 subnet in each AZ in that region
- Comes with:
	- Internet Gateway
	- Security Group
	- NACL
- Anything placed within a VPC is automatically assigned a public IPv4 address

#### Custom VPC
- Private by default
- Configure exactly how you need

# [[Region Resilient|Regionally Resilient]]

- Each VPC is given a range of IPs, called a VPC CIDR
- Everything inside the VPC (Services, etc) uses the CIDR Range of the VPC
- If anything needs to communicate with the VPC, it needs to communicate to the VPC CIDR
- Each VPC can be divided into multiple subnets.

![[Pasted image 20250204174541.png]]