**Dynamic routing** is a method used in computer networks where routers automatically learn, update, and share routing information with other routers using **routing protocols**. Unlike static routing (where routes are manually configured), dynamic routing adapts to changes in the network—such as link failures or new connections—without requiring manual intervention.

### How Dynamic Routing Works:

- Routers communicate with each other using **routing protocols** (e.g., OSPF, EIGRP, RIP, BGP).
- They exchange information about network topology and available paths.
- Based on this information, routers build and update their **routing tables** automatically.
- If a route becomes unavailable, routers detect the change and recalculate the best path to the destination.

---

### Common Dynamic Routing Protocols:

| Protocol                                               | Type                                         | Use Case                                    |
| ------------------------------------------------------ | -------------------------------------------- | ------------------------------------------- |
| **RIP (Routing Information Protocol)**                 | Distance-vector                              | Small, simple networks                      |
| **OSPF (Open Shortest Path First)**                    | Link-state                                   | Medium to large enterprise networks         |
| **EIGRP (Enhanced Interior Gateway Routing Protocol)** | Advanced distance-vector (Cisco-proprietary) | Cisco-based enterprise networks             |
| **BGP (Border Gateway Protocol)**                      | Path-vector                                  | Internet routing between autonomous systems |

---

### Advantages of Dynamic Routing:

- **Automatic updates**: Routes are updated automatically when network changes occur.
- **Scalability**: Suitable for large and complex networks.
- **Fault tolerance**: Can detect link failures and reroute traffic dynamically.
- **Reduced administrative overhead**: No need to manually configure every route.

---

### Disadvantages of Dynamic Routing:

- **Higher resource usage**: Uses CPU, memory, and bandwidth to exchange routing updates.
- **More complex configuration and troubleshooting** compared to static routing.
- **Potential for routing loops** (though modern protocols have mechanisms to prevent this).
- **Security considerations**: Requires protection against unauthorized route advertisements.

---

### Example:

If a router running **OSPF** detects that a link to a network has failed, it immediately notifies neighboring routers. They then recalculate the shortest path and update their routing tables—**all automatically**, without an administrator needing to reconfigure anything.

---

### When to Use Dynamic Routing:

- Medium to large networks with multiple paths.
- Networks requiring high availability and redundancy.
- Environments where network topology changes frequently.
- Enterprise or service provider networks.

---

### Summary:

**Dynamic routing** enables routers to intelligently and automatically determine the best paths for data transmission by exchanging routing information. It is essential for scalable, resilient, and self-healing networks, especially as network size and complexity grow.
