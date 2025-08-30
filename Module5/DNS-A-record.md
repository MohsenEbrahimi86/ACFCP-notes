A **DNS A Record** (short for **Address Record**) is a type of DNS (Domain Name System) record that maps a **domain name** (like `example.com`) to an **IPv4 address** (like `192.0.2.1`). It is one of the most fundamental and commonly used DNS records.

### Purpose:

When you type a domain name into your web browser, your computer needs to find the corresponding IP address of the server hosting that website. The A record provides this mapping, enabling the translation of human-readable domain names into machine-readable IP addresses.

### Example:

```
example.com   A   192.0.2.1
```

This means that when someone visits `example.com`, the DNS system will resolve it to the IP address `192.0.2.1`.

### Key Points:

- **Only supports IPv4 addresses** (e.g., 192.0.2.1).
- For IPv6 addresses, a different record type called the **AAAA record** is used.
- A records are essential for directing web traffic, email delivery, and other internet services to the correct servers.
- Multiple A records can be created for the same domain to support load balancing or redundancy.

### Common Use Cases:

- Hosting a website on a specific server.
- Pointing a subdomain (like `www.example.com`) to a server.
- Configuring services like FTP or mail servers (though MX records are typically used for email routing).

In summary, the A record is a crucial part of DNS that links domain names to IPv4 addresses, enabling users to access websites using easy-to-remember names instead of numerical IP addresses.
