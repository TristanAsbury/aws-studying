#IaaS #Private #Service 
### 🔹 **Private | IaaS | Compute Service**

- **IaaS (Infrastructure as a Service)** – Provides **virtual machines (EC2 instances)** in the cloud.
- **AWS handles the hardware** (servers, networking, storage), **YOU** manage the OS, applications, and security patches.
- **Billing is On-Demand ⏳** – Charged **per second** of usage.
- EC2 instances come in **various sizes** tailored for different workloads:
    - 🖥️ **General Purpose** – Balanced CPU & Memory (e.g., `t3.micro`, `m5.large`).
    - 🚀 **Compute Optimized** – High-performance CPUs for gaming, rendering, etc. (`c6g.xlarge`).
    - 📀 **Storage Optimized** – High disk throughput (`i3.large`).
    - 🎮 **GPU Instances** – Machine learning, gaming, and deep learning (`g4dn.xlarge`).

---

## 🛡️ **Resilience & Availability**

- **EC2 runs inside a [[Virtual Private Cloud (VPC)]]** 🏠 for security.
- 🌍 **Region-based Service** – Choose the AWS region closest to your users.
- 🏢 **[[Availability Zone]] (AZ) Resilient**:
    - If an **AZ fails**, the instance will fail unless you have **multi-AZ deployments**.
    - Use **Auto Scaling Groups** and **Elastic Load Balancers** (ELB) for redundancy.

📌 **Example:**

- A company running a web app deploys multiple EC2 instances in **3 AZs** under an **ELB** to ensure high availability. If one AZ fails, the others remain operational.

---

## 🔄 **EC2 Instance Lifecycle & States**

### 🟢 **Running**

✅ **Instance is active and consuming compute resources.**

- Can be **stopped** (saved for later) or **terminated** (permanently deleted).
- ⏳ **Billing applies while running, even if idle**!

### 🟡 **Stopped**

💾 **Instance is powered off but storage remains.**

- Can be **started** again without data loss.
- Billing applies **only for EBS storage (Elastic Block Store)**.

📌 **Example:**

- You stop a `t3.micro` instance overnight to save costs but retain the **EBS volume** for data persistence.

### 🔴 **Terminated**

⚠️ **Instance is permanently deleted.**

- 🚫 **Cannot be restarted.**
- 🗑️ **All associated resources (like storage) are removed unless separately retained.**

📌 **Example:**

- A company runs batch jobs on temporary EC2 instances. Once processing is complete, they terminate the instances to avoid unnecessary charges.

---

## 🔗 **Connecting to EC2 Instances**

### 💻 **Windows Instances**

🔹 **Use RDP (Remote Desktop Protocol)** – Port **3389**

- Requires a **public IP** or **VPN connection** if in a private subnet.
- Default username: **Administrator**

### 🐧 **Linux Instances**

🔹 **Use SSH (Secure Shell)** – Port **22**

- Authenticate using **SSH Key Pairs 🔑** (`.pem` file).
- Default usernames vary by OS:
    - **Amazon Linux**: `ec2-user`
    - **Ubuntu**: `ubuntu`
    - **RHEL**: `ec2-user`
    - **Debian**: `admin`

📌 **Example:**  
To connect to a Linux EC2 instance:

`ssh -i "my-key.pem" ec2-user@your-ec2-public-ip`

💡 **Security Tip:**
- Avoid using the **root** account.
- Use **IAM roles** instead of hardcoding AWS credentials on the instance.
- Restrict SSH/RDP access using **Security Groups** (`0.0.0.0/0` is dangerous!).