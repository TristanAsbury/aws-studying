A physical location around the world where we cluster data centers. We call each group of logical data centers an [[Availability Zone]]. Each AWS Region consists of a **minimum of three**, isolated, and physically separate AZs within a geographic area. Unlike other cloud providers, who often define a region as a single data center, the multiple AZ design of every AWS Region offers advantages for customers. Each AZ has independent power, cooling, and physical security and is connected via redundant, ultra-low-latency networks. AWS customers focused on high availability can design their applications to run in multiple AZs to achieve even greater fault-tolerance. AWS infrastructure Regions meet the highest levels of security, compliance, and data protection.

## Advantages
- Regions are geographically isolated so data can be safe from any disasters from one region
- Location control, move your services as close to your customers as possible

## Region Code
- When referring to a region, you refer to it by a region code
	- ex: ap-southeast-2

## Region Name
- Along with the Region Code, there is a region name
	- ex: Asia Pacific (Sydney)

- Some examples:
	- N. Virginia
	- Ohio
	- N. California
	- Oregon
	- etc

## See Also
[[Region Resilient]]
[[Globally Resilient]]