## **What is a Subnet?**

A **subnet** is a segment of a **[[Virtual Private Cloud (VPC)]]** that partitions the network into smaller, manageable sections.

---

## **Key Characteristics**

- 🏢 **Belongs to a Specific VPC:**
    - Every subnet is **part of a VPC**.
- 📍 **Single Availability Zone:**
    - A subnet **resides in only one Availability Zone** even though a VPC can span multiple zones.
- 🔢 **Range of IP Addresses (CIDR Block):**
    - Each subnet is assigned a **CIDR range** (Classless Inter-Domain Routing), which defines the pool of IP addresses available within that subnet.
    - **CIDR Example:** `10.0.1.0/24` represents a specific range of IP addresses.

---

## **Why Are Subnets Important?**

- **Network Organization:**
    - Subnets help organize and segment your network, which is essential for managing security, traffic flow, and resource allocation.
- **Enhanced Security:**
    - You can place resources with similar security requirements in the same subnet (e.g., public-facing vs. private resources) and apply appropriate network access controls.
- **Optimized Traffic Management:**
    - By segmenting your VPC, you can control how data flows between different parts of your network, improving performance and reliability.

---

## **Quick Recap**

- **Subnets are components of a VPC:**
    - They segment your VPC into manageable sections.
- **Located in a Single Availability Zone:**
    - Each subnet exists in just one AZ, making zone-specific resource planning critical.
- **Defined by a CIDR Range:**
    - The CIDR block allocated to a subnet determines the number of available IP addresses.