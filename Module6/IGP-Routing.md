**IGP Routing** stands for **Interior Gateway Protocol Routing**, which refers to routing protocols used to exchange routing information **within a single Autonomous System (AS)** — that is, within the same organization or network (such as a corporate network, campus, or ISP’s internal network).

### Purpose of IGP Routing:

- To enable routers **inside a network** to dynamically learn and share routes.
- To ensure efficient and reliable communication between devices within the same administrative domain.
- To support fast convergence and optimal path selection for internal traffic.

---

### Key Characteristics of IGP:

- Used for **intra-domain routing** (within one AS).
- Focuses on finding the **shortest or fastest path** using metrics like hop count, bandwidth, delay, or cost.
- Designed for **fast convergence** and efficient performance in medium to large internal networks.
- Not used for internet-wide routing.

---

### Common IGP Protocols:

| Protocol                                               | Type                                         | Description                                                         |
| ------------------------------------------------------ | -------------------------------------------- | ------------------------------------------------------------------- |
| **OSPF** (Open Shortest Path First)                    | Link-state                                   | Widely used, open standard, scales well, uses Dijkstra's algorithm. |
| **IS-IS** (Intermediate System to Intermediate System) | Link-state                                   | Similar to OSPF, often used in large service provider networks.     |
| **EIGRP** (Enhanced Interior Gateway Routing Protocol) | Advanced distance-vector (Cisco-proprietary) | Fast convergence, efficient updates, developed by Cisco.            |
| **RIP** (Routing Information Protocol)                 | Distance-vector                              | Older, simpler, limited to 15 hops; suitable for small networks.    |

---

### Example:

In a corporate office with multiple departments and routers, **OSPF** might be used so that all internal routers automatically learn how to reach each other’s subnets (e.g., Finance VLAN, HR VLAN, etc.) without manually configuring every route.

---

### IGP vs EGP at a Glance:

| Feature      | **IGP (Interior Gateway Protocol)**    | **EGP (Exterior Gateway Protocol)**        |
| ------------ | -------------------------------------- | ------------------------------------------ |
| Scope        | Within a single Autonomous System (AS) | Between different Autonomous Systems       |
| Purpose      | Optimize internal routing              | Exchange routing policies between networks |
| Examples     | OSPF, EIGRP, RIP, IS-IS                | BGP (Border Gateway Protocol)              |
| Metric Focus | Speed, cost, bandwidth, hops           | Policy, path attributes, reliability       |
| Convergence  | Fast                                   | Slower (prioritizes stability)             |
| Use Case     | Enterprise internal networks           | Internet routing (e.g., between ISPs)      |

---

### Why IGP Matters:

IGPs are essential for maintaining **efficient, scalable, and self-healing internal networks**. If a link fails, an IGP like OSPF or EIGRP can quickly detect the change and reroute traffic through an alternate path — all automatically.

---

### Summary:

**IGP Routing** is the use of interior gateway protocols (like OSPF, EIGRP, or RIP) to manage and distribute routing information **within a single autonomous system**. It ensures that data can be routed efficiently and reliably across internal networks, forming the backbone of enterprise and organizational network operations.
