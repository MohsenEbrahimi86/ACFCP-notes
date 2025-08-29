**Windows Internet Name Service (WINS)** is a legacy Microsoft networking service designed to resolve **NetBIOS (Network Basic Input/Output System) names** to **IP addresses** in Windows networks. It was primarily used in older Windows environments (such as Windows NT, 2000, and early versions of Windows Server) before the widespread adoption of DNS for name resolution.

---

### Purpose of WINS:

In early Windows networks, computers identified each other using **NetBIOS names** (e.g., `COMPUTER01`) rather than domain names. WINS was developed to:

- Dynamically map NetBIOS names to IP addresses.
- Reduce network traffic caused by NetBIOS broadcast-based name resolution.

Without WINS, computers would use **broadcasts** to find each other on the local network, which doesn't work across subnets and increases traffic.

---

### How WINS Works:

1. When a Windows computer starts up, it **registers its NetBIOS name** with the WINS server.
2. The WINS server stores this name-to-IP mapping in a database.
3. When another computer wants to communicate with it, it queries the WINS server instead of broadcasting.
4. The WINS server responds with the correct IP address.

This process enables **name resolution across different subnets**, making it ideal for larger, routed networks.

---

### Example:

- Computer Name: `SALES-PC`
- IP Address: `192.168.1.50`
- When `SALES-PC` connects to the network, it registers with the WINS server.
- Another computer can now find `SALES-PC` by querying the WINS server instead of sending a broadcast.

---

### WINS vs DNS:

| Feature              | WINS                               | DNS                                 |
| -------------------- | ---------------------------------- | ----------------------------------- |
| Name Type            | NetBIOS names (e.g., `COMPUTER01`) | Hostnames (e.g., `pc01.domain.com`) |
| Used In              | Legacy Windows networks            | Modern internet and networks        |
| Resolution           | NetBIOS name → IP                  | Domain name → IP                    |
| Scalability          | Limited, outdated                  | Highly scalable and hierarchical    |
| Cross-Subnet Support | Yes (unlike NetBIOS broadcasts)    | Yes (natively)                      |
| Current Relevance    | **Deprecated / Legacy**            | **Standard and widely used**        |

---

### Current Status:

- **WINS is largely obsolete** today.
- Modern networks use **DNS** for name resolution, especially in Active Directory environments.
- NetBIOS has been replaced by more efficient protocols like **DNS-based service discovery**.
- Microsoft no longer recommends WINS for new deployments.

---

### When Was WINS Used?

- Common in **Windows NT 4.0** and **Windows 2000 Server** networks.
- Phased out with the introduction of **Active Directory** and **Dynamic DNS (DDNS)** in Windows Server 2003 and later.

---

### Summary:

**WINS (Windows Internet Name Service)** was a Microsoft solution for resolving NetBIOS computer names to IP addresses in older Windows networks. It helped reduce broadcast traffic and enabled name resolution across subnets but has been **replaced by DNS** in modern networks. Today, WINS is considered **outdated and deprecated**, though it may still exist in some legacy systems.
