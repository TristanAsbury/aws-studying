> [!NOTE] Definition
> A zone file is a file stored on a DNS server that lists all the resource [[DNS Record Type|records]] (like A, AAAA, NS, MX, etc.) for a specific domain or subdomain. It acts as a map to direct traffic—whether it’s for websites, email servers, or other services.

### **Key Components of a Zone File**

1. **SOA (Start of Authority) Record:**
    - **Purpose:** Indicates the beginning of the zone file and provides administrative information about the zone (like the primary nameserver, the email of the domain administrator, and various timers).

2. **NS (Nameserver) Records:**
    - **Purpose:** List the authoritative nameservers for the domain that are responsible for handling DNS queries.

3. **A and AAAA Records:**
    - **Purpose:** Map domain names to IPv4 (A) or IPv6 (AAAA) addresses, allowing browsers to locate the correct server.

4. **MX (Mail Exchange) Records:**
    - **Purpose:** Direct email to the appropriate mail servers for the domain.

5. **Other Record Types:**
    - **CNAME, TXT, SRV, etc.:** Depending on the domain’s needs, additional records can be included for various purposes like aliasing domains or verifying domain ownership.
# See Also
[[Route53]]