#Private #IAAS  #Service 

- IAAS (Infrastructure as a service) - Provides Virtual Machines => Instances
- AWS Handles Hardware etc, **YOU** handle the OS etc.
- *On-Demand Billing - Per Second*
- Different instance sizes and capabilities (storage, cpu, gpu, etc)

## Resilience
- Private service by default - uses [[Virtual Private Cloud (VPC)]] networking
- ==AZ Resilient - Instance fails if AZ fails

# States

#### Running
- Can be stopped
- Can be terminated
- Charged while running, even if idle
#### Stopped
- Can be ran
- Can be terminated
- Only charges for storage.
#### Terminated
- Once terminated, it cannot be ran
- Stops ALL resource usage, including disk. Non reversible.

# Connecting to EC2
- Connect to Windows instance using RDP (Remote Desktop Protocol), port 3389
- Linux instances use SSH, port 22
	- Login or auth using [[SSH Keypair]]