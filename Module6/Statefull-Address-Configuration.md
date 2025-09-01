The term **"Stateful Address Configuration"** refers to a method used in networking—particularly in **IPv6**—where a host obtains its IP address and other network configuration settings (like default gateway, DNS servers, etc.) from a centralized server that **keeps track of the state** (i.e., what has been assigned to which device).

---

### 🔹 What Does "Stateful" Mean?

- **"Stateful"** means the server **maintains state information** about each client’s configuration.
- It knows which IP addresses are assigned, to whom, and for how long.
- This is similar to how **DHCP (Dynamic Host Configuration Protocol)** works in IPv4.

---

### 🔹 Stateful Address Configuration in IPv6

In IPv6, **Stateful Address Configuration** is primarily done using:

> **DHCPv6 (Dynamic Host Configuration Protocol for IPv6)**

With DHCPv6:

- A client requests network configuration from a **DHCPv6 server**.
- The server assigns an IPv6 address (or a range of addresses), DNS servers, domain name, time servers, and other options.
- The server **keeps a record (state)** of which addresses have been leased and to which clients.

---

### 🔹 How It Works:

1. **Client sends a DHCPv6 request** (e.g., `Solicit` message).
2. **DHCPv6 server responds** with an available IPv6 address and other settings.
3. **Server tracks the lease** (address + duration + client ID).
4. The client **renews the lease** before it expires.

This is called **Stateful DHCPv6** because the server maintains the state of all address assignments.

---

### 🔹 Comparison with Other IPv6 Configuration Methods:

| Method                                           | Description                                                                                    | Server Keeps State?                           |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------- | --------------------------------------------- |
| **Stateful Address Configuration (DHCPv6)**      | Full configuration from DHCPv6 server (IP, DNS, etc.)                                          | ✅ Yes                                        |
| ** Stateless Address Autoconfiguration (SLAAC)** | Client generates its own IPv6 address using router advertisements (RA). No server involvement. | ❌ No                                         |
| **Stateless DHCPv6**                             | Uses SLAAC for IP address, but gets additional info (like DNS) from a DHCPv6 server.           | ❌ No (server doesn’t assign IP, so no state) |

> 🔍 Example:
>
> - A laptop on a corporate network uses **SLAAC** to assign itself an IPv6 address based on the network prefix.
> - But it uses **Stateless DHCPv6** to learn the DNS server address.
> - In contrast, in **Stateful DHCPv6**, the server assigns both the IPv6 address **and** DNS settings.

---

### 🔹 When Is Stateful Address Configuration Used?

- In enterprise environments requiring **centralized control**.
- When **audit, tracking, or policy enforcement** is needed.
- For assigning additional configuration beyond what SLAAC provides.
- When administrators want full control over IP address assignment.

---

### 🔹 Advantages:

- Centralized management of IP addresses and network settings.
- Ability to track and control which device gets what address.
- Supports rich configuration options (DNS, NTP, domain names, etc.).

### 🔹 Disadvantages:

- Requires a DHCPv6 server (more complexity).
- Single point of failure if not redundant.
- Less "plug-and-play" than SLAAC.

---

### ✅ Summary:

**Stateful Address Configuration** is a method—used mainly in IPv6 via **DHCPv6**—where a server **assigns and tracks** IP addresses and network settings for clients. It is called "stateful" because the server maintains a record (state) of all address leases, enabling centralized, controlled network management. It contrasts with **SLAAC**, which is stateless and decentralized.
