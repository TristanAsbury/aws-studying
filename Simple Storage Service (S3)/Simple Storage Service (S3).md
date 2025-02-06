## 1. Service Overview

- **Global Storage Platform**
    - 🌐 **Access Anywhere:**
        - Runs from **all regions** and can be accessed from anywhere with an internet connection.
    - 📍 **Regional Storage:**
        - Although global, data is stored in a **specific region**.
        - Data **does not leave the region** unless explicitly configured.
    - 🔓 **Public Service:**
        - Accessible worldwide.
        - Operates in the **Public Zone** (often referred to as _The Network Zones_).
    - 💪 **Region Resilient:**
        - Designed to maintain data durability and availability across regions.

---

## 2. Access Methods

You can access S3 using several methods:

- 🖥️ **UI (User Interface)**
- 🖱️ **CLI (Command Line Interface)**
- 🛠️ **API (Application Programming Interface)**
- 🌐 **HTTP**

---

## 3. Objects in S3

S3 stores data as **objects**, which have two main components:

### **🔑 Object Key**

- **Definition:**
    - A unique identifier that **identifies the object** within a bucket.

### **📦 Object Value (Content)**

- **Definition:**
    - The **actual data** or content being stored.
- **Size Limit:**
    - **Up to 5TB** per object!

---

## 4. Buckets 🪣

Buckets are **containers** that hold your objects. Here’s what you need to know:

- **Region-Specific:**
    - Buckets are created in a specific region and **never leave the region** unless configured otherwise.
- **Unlimited Objects:**
    - Each bucket can hold an unlimited number of objects.
- **Flat Structure:**
    - **No native folders or directories.**
    - What appears as folders in the UI are just **prefixes** added to object keys.

### **Bucket Name Requirements:**

- **Global Uniqueness:**
    - The bucket name must be **unique across all regions and all AWS accounts**.
- **Length:**
    - **3-63 characters.**
- **Format:**
    - Must **start with a lowercase letter or number**.
    - **Cannot be IP-formatted.**

### **Quantity Limits:**
- **Soft Limit:** 100 buckets per account.
- **Hard Limit:** 1,000 buckets per AWS account.
- **Note:** Unlimited objects can be stored **within each bucket**.

---

## 5. Patterns and Anti-Patterns

### **When to Use S3:**
- ✅ **Ideal Use Cases:**
    - Storing and accessing **entire files at once**.
    - **Large-scale data storage, distribution, or uploads.**
    - **Offloading media or static content:**
        - For instance, instead of hosting large media files on your web server, store them in S3 and fetch them as needed.
    - **Input for AWS Services:**
        - Acts as a data source for many AWS products.

### **When Not to Use S3:**
- ❌ **Anti-Patterns:**
    - **Not a File System:**
        - S3 is an **object store**, not a traditional file or block storage system.
    - **Avoid as a Mount Point:**
        - Do not use S3 as a mount point or storage for compute-intensive operations.

---

## 🎓 Quick Recap
- **S3 is a Global Storage Platform:**
    - Access via UI, CLI, API, or HTTP.
- **Data is stored as Objects:**
    - Each with a unique key and content (up to 5TB per object).
- **Buckets are Region-Specific Containers:**
    - Unique naming, unlimited objects, and flat structure.
- **Best Practices:**
    - Use S3 for large-scale, offload, and distribution scenarios.
    - Avoid using S3 as a direct file system or mount point.