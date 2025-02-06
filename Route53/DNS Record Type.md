
### **1. Nameserver (NS) Record**

- **Purpose:**
    - Tells the internet which server(s) are responsible for managing all DNS records for a domain.
- **How It Works:**
    - When you type a website address into your browser, the NS record directs your request to the correct server that holds the domain’s DNS information.
    - Example: For `example.com`, the NS records might point to `ns1.example.com` and `ns2.example.com`.
- **Key Point:**
    - NS records are like the “phone directory” for a domain, pointing to the servers that know everything about that domain’s settings.

---

### **2. A and AAAA Records**

#### **A Record**

- **Purpose:**
    - Maps a domain name to an IPv4 address (e.g., `192.168.1.1`).
- **How It Works:**
    - When you enter a domain name in your browser, the A record tells your computer the numerical IP address where the website is hosted.
- **Key Point:**
    - IPv4 addresses are 32-bit numbers, usually written in the familiar dot-decimal format.

#### **AAAA Record**

- **Purpose:**
    - Maps a domain name to an IPv6 address (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
- **How It Works:**
    - Similar to A records, but for IPv6 addresses, which are 128-bit numbers. This is essential as the internet grows and more addresses are needed.
- **Key Point:**
    - IPv6 is the newer version of IP addressing, designed to overcome the limitations of IPv4.

---

### **3. CNAME Record (Canonical Name Record)**

- **Purpose:**
    - Creates an alias for a domain name, pointing it to another domain name rather than an IP address.
- **How It Works:**
    - If you have multiple domain names (e.g., `www.example.com` and `blog.example.com`) that should lead to the same website, you can set one as a CNAME to the main domain (e.g., `example.com`).
    - This means if the IP address changes for `example.com`, you only need to update it in one place.
- **Key Point:**
    - CNAME records simplify DNS management by allowing one domain to “borrow” the settings of another.

---

### **4. MX Record (Mail Exchange Record)**

- **Purpose:**
    - Directs email to the correct mail server for a domain.
- **How It Works:**
    - When someone sends an email to `user@example.com`, the MX record tells the sending mail server which server handles emails for `example.com`.
    - MX records often include a priority value. Multiple MX records can be set up, where a lower number indicates a higher priority.
- **Key Point:**
    - MX records ensure that emails are delivered to the right server, and priorities help manage multiple mail servers for reliability.

# 5. TXT Record
A TXT record is a DNS record that holds plain text data. It is stored in a zone file (or managed within a hosted zone in services like AWS Route 53) just like other DNS records (A, MX, etc.).

# 6. Time To Live (TTL)
- When someone queries an address, and the address is not cached in the resolver server, then we walk down the tree until we find the end address.
	- TTL is how long (in seconds) the results of this query can be cached in the resolver server for future visits.
- If changing the domain name, its a good idea to lower the TTL since your old domain name will be cached in the resolver server.
