#Infrastructure 

Within an [[Region]], there are many availability zones. An Availability Zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity in an AWS Region. AZs give customers the ability to operate production applications and databases that are more highly available, fault tolerant, and scalable than would be possible from a single data center. All AZs in an AWS Region are interconnected with high-bandwidth, low-latency networking, over fully redundant, dedicated metro fiber providing high-throughput, low-latency networking between AZs. All traffic between AZs is encrypted. The network performance is sufficient to accomplish synchronous replication between AZs.

## Resilience
- Each Availability Zone is separated from another Availability Zone. This allows for resilience, and we should remember this when designing architecture.
- Availability Zones usually have one or more discrete data centers!
