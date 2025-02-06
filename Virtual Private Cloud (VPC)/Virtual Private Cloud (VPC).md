A **VPC** is a **Virtual Network** inside AWS that allows you to launch AWS resources into a **logically isolated** section of the cloud.

- **Account & Region Specific:**
    - 🏷️ **One Account, One Region:**
        - A VPC exists within **one AWS account** and is confined to **one region**.
- **Isolation & Privacy:**
    - 🔒 **Private by Default:**
        - VPCs are **isolated** unless you configure them to connect with other networks.
    - 🖥️ **Service Instance Isolation:**
        - Resources (e.g., EC2 instances) inside a VPC are **isolated** and communicate with each other or external networks **only if allowed**.
- **[[Region Resilient]]:**
    - 🌟 **Reliable Within a Region:**
        - VPCs are designed to be resilient **within the region** they are deployed in.

---

## **Types of VPCs**

### **1. Default VPC**

- **Availability:**
    - 📍 **One per Region:**
        - There is **one default VPC per region**.
- **Lifecycle:**
    - 🔄 **Easily Deleted & Recreated:**
        - You can **delete** and **recreate** the default VPC from the AWS Console UI.
- **Architecture:**
    - 🏗️ **Standard Configuration:**
        - **Preconfigured IP range** and a **"1 subnet per [[Availability Zone]] (AZ)"** architecture.
        - Contains **one subnet in every AZ** within the region.
- **IP Range:**
    - 📡 **Default CIDR:**
        - **CIDR:** `172.31.0.0/16`
        - Each AZ gets a **/20 subnet**.
- **Included Components:**
    - 🌉 **Internet Gateway:**
        - Provides direct access to the Internet.
    - 🔐 **Security Group:**
        - Acts as a virtual firewall.
    - 🚧 **Network ACL (NACL):**
        - Offers an extra layer of subnet-level security.
- **Public IP Assignment:**
    - 🌍 **Automatic Public IPs:**
        - Instances launched in a default VPC are automatically assigned a **public IPv4 address**.

### **2. Custom VPC**

- **Private by Default:**
    - 🤫 **Starts Private:**
        - Custom VPCs are **private** by default, giving you control over Internet exposure.
- **Full Customization:**
    - 🎨 **Tailor-Made Configurations:**
        - Configure the VPC exactly how you need:
            - Choose your own **CIDR block**.
            - Set up **subnets**, **route tables**, and **security settings**.
            - Customize **connectivity** as required.

---

## **Regionally Resilient Architecture**

- **VPC CIDR:**
    - 📏 **Assigned IP Range:**
        - Every VPC is given a range of IP addresses, known as the **VPC CIDR** (e.g., `10.0.0.0/16`).
- **Internal Communication:**
    - 🔄 **Within the CIDR:**
        - All resources inside the VPC use the **VPC CIDR** for internal communication.
- **Subnet Division:**
    - 🗂️ **Segmenting Your Network:**
        - You can divide a VPC into **multiple subnets** to manage and secure your resources more effectively.

---

## **Quick Recap**

- **VPC Overview:**
    - 🌐 A **virtual network** in AWS, confined to one account and region.
    - 🔒 Provides an **isolated environment** for your AWS resources.
- **Types of VPCs:**
    - **Default VPC:**
        - Preconfigured with standard components (Internet Gateway, Security Group, NACL) and automatic public IP assignment.
    - **Custom VPC:**
        - Fully customizable to fit your exact needs.
- **Regionally Resilient:**
    - 📡 Each VPC gets its own **CIDR block**, ensuring all resources communicate within this range.
    - 🗂️ **Subnets** further segment your network for better organization and security.