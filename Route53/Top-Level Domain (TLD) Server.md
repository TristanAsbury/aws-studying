
> [!NOTE] Definition
> A TLD server handles queries for domain names that share the same extension, such as `.com`, `.org`, `.net`, or country codes like `.uk`, `.ca`.

    
- **Role in the DNS Process:**
    - **Next Step:** After the [[Root Server]] directs the query, your computer contacts the appropriate TLD server.
    - **Providing Authority:** The TLD server then provides the address of the domain’s authoritative nameserver (the one that has the A, AAAA, MX [[DNS Record Type|records]], etc.).
- **Key Point:**  
    TLD servers bridge the gap between the broad direction provided by root servers and the specific information held in the authoritative [[Nameserver|nameservers]] for each domain.