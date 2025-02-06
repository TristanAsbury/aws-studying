> [!NOTE]
> A root server is the highest level in the Domain Name System (DNS) hierarchy. It doesn’t contain detailed records for individual domains but knows where to direct requests to the next level. There are **13 DNS root servers** managed by large companies. The root zone is hosted by IANA.

- **Role in the DNS Process:**
    - **Starting Point:** When you type a website address into your browser, if your computer doesn’t have the necessary information cached, it begins the lookup process at a root server.
    - **Referral:** The root server doesn’t provide the website’s IP address. Instead, it tells your computer which TLD server (like one for `.com`, `.org`, etc.) to contact next.

- **Key Point:**  
    There are a limited number of root servers (organized into clusters and distributed around the world) that form the backbone of the DNS lookup process.