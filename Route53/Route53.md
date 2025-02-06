#GlobalService

- [[Globally Resilient]]
# Register Domains
- Has relationships with all major domain registries
	- .com, .io, .net, etc
- When a domain is registered
	- Route53 creates a [[Zone File]] for the domain being registered
	- Allocates [[Nameserver|nameservers]] which Route53 manages and 
		- are distributed globally
	- Puts the zone file on the four [[Nameserver|nameservers]]

# Host Zones
- Route53 provides DNS zones as well as hosting for those zones
	- Basically DNS as a service
- Lets you create zone files, called **[[Hosted Zones]]** in Route53 terminology
- When a hosted zone is created, a number of servers are allocated and linked to that zone

- Managed nameservers

