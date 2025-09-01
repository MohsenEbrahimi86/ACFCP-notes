**GRE Tunnel** stands for **Generic Routing Encapsulation Tunnel**. It is a tunneling protocol developed by Cisco (but widely supported across vendors) that can encapsulate a wide variety of network layer protocols (such as IP, IPv6, AppleTalk, etc.) inside virtual point-to-point or point-to-multipoint links over an IP network.

### Purpose of GRE Tunnel:

GRE allows the creation of a **virtual, point-to-point link** between two routers across an IP network (like the Internet or another IP backbone), enabling the transport of packets that might not otherwise be routable over the intermediate network.

---

### How GRE Tunnel Works:

1. **Encapsulation**:

   - The original packet (payload) is encapsulated inside a **GRE header**, and then inside an **IP header** (called the delivery or outer header).
   - This allows the packet to be routed across the intermediate IP network.

2. **Tunnel Endpoints**:

   - The tunnel has two endpoints: **tunnel source** (the physical interface or IP address of the ingress router) and **tunnel destination** (the IP address of the egress router).
   - These are statically configured.

3. **Decapsulation**:
   - When the encapsulated packet reaches the destination router, the GRE and outer IP headers are stripped off.
   - The original payload is then processed normally.

---

### GRE Packet Structure:

```
+------------------------+
| Outer IP Header        |  → Source: Tunnel Start, Dest: Tunnel End
+------------------------+
| GRE Header             |  → Identifies payload type (e.g., IPv4)
+------------------------+
| Original (Payload) IP  |  → The actual packet being tunneled
| Packet (e.g., IPv4)    |
+------------------------+
```

---

### Key Features of GRE:

- **Protocol Independence**: GRE can carry non-IP protocols (e.g., IPv6 over IPv4, multicast, etc.).
- **Supports Multicast and Broadcast**: Useful for routing protocols like OSPF or EIGRP that rely on multicast.
- **Simple and Lightweight**: No encryption or authentication by default (but can be combined with IPsec).
- **Stateless**: GRE itself does not maintain session state.

---

### Common Use Cases:

1. **Connecting Discontiguous Networks**:

   - For example, connecting two IPv6 networks over an IPv4-only backbone.

2. **Site-to-Site VPNs (with IPsec)**:

   - GRE is often used in combination with **IPsec** to provide secure, encrypted tunnels (GRE over IPsec).
   - GRE handles the encapsulation and routing; IPsec handles encryption and integrity.

3. **Extending Networks Over the Internet**:

   - Creating a virtual link between two remote offices.

4. **Supporting Routing Protocols**:
   - GRE tunnels allow dynamic routing protocols (like OSPF, EIGRP) to run across them, since they support multicast.

---

### Example:

You have two offices (Router A and Router B) connected via the Internet. You create a GRE tunnel between them:

- Tunnel source: Public IP of Router A
- Tunnel destination: Public IP of Router B
  Now, private traffic (e.g., 192.168.1.0/24 ↔ 192.168.2.0/24) can flow securely over the public Internet via the GRE tunnel.

> 🔐 Note: GRE does **not** provide encryption. For security, it's typically paired with **IPsec**.

---

### Advantages:

- Supports multiple protocols and multicast.
- Simple to configure.
- Works well with dynamic routing protocols.
- Flexible for various network designs.

### Disadvantages:

- No built-in encryption or authentication (insecure alone).
- Adds overhead (tunnel headers increase packet size).
- Requires static configuration (no auto-discovery).
- Can complicate troubleshooting (tunnel up ≠ path functional).

---

### Summary:

**GRE Tunnel** is a versatile and widely used tunneling protocol that enables the transport of various network layer packets over an IP network by encapsulation. While it doesn’t provide security on its own, it's often combined with IPsec to build secure and functional site-to-site connections in enterprise and service provider networks.
