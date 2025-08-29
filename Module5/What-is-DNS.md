**DNS** stands for **Domain Name System**. It is a fundamental system that translates human-readable domain names (like `www.google.com`) into machine-readable **IP addresses** (like `142.250.179.174`) so that computers can locate and communicate with each other on the internet.

### How DNS Works:

1. **You type a URL** (e.g., `www.example.com`) into your web browser.
2. Your computer contacts a **DNS resolver** (usually provided by your ISP or a public service like Google DNS or Cloudflare).
3. The resolver checks if it already knows the IP address for that domain.
4. If not, it queries a series of DNS servers:
   - **Root servers** → identify the top-level domain (like `.com`).
   - **Top-Level Domain (TLD) servers** → point to the domain’s authoritative name servers.
   - **Authoritative name servers** → provide the actual IP address for the domain.
5. Once the IP address is found, it’s sent back to your computer.
6. Your browser uses the IP address to load the website.

### Why DNS Is Important:

- **User-Friendly**: You don’t need to remember complex IP addresses.
- **Scalability**: Enables the internet to handle billions of devices and websites.
- **Redundancy & Speed**: DNS is distributed globally, improving reliability and performance.

### Example:

```
Domain Name: www.example.com
IP Address:  93.184.216.34
```

Without DNS, we’d have to memorize IP addresses for every website we want to visit — much like remembering phone numbers instead of using contact names.

In short, **DNS is the internet’s phonebook**, translating names into numbers so devices can find each other.
