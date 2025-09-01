**Static routing** is a form of routing in which network administrators manually configure routes in a router's routing table. Unlike dynamic routing, where routers automatically learn and update routes using routing protocols (like OSPF or RIP), static routes are fixed and do not change unless manually updated by an administrator.

### Key Characteristics of Static Routing:

- **Manually Configured**: Each route entry (e.g., destination network, subnet mask, next-hop address or exit interface) is entered by hand.
- **No Overhead**: Since no routing protocols are used, there is no bandwidth usage or CPU processing for route updates.
- **Predictable and Secure**: Because routes are predefined, they are less prone to routing loops or unauthorized changes.
- **Not Scalable for Large Networks**: Managing static routes becomes impractical as network size increases.
- **No Automatic Failover**: If a link fails, static routes do not automatically reroute traffic unless a backup static route is manually configured.

### Example:

To route traffic destined for network `192.168.2.0/24` via the next-hop router at `10.0.0.1`, a static route would be configured like this on a router:

```bash
ip route 192.168.2.0 255.255.255.0 10.0.0.1
```

### When to Use Static Routing:

- Small, stable networks with few paths.
- Default routes (gateway of last resort).
- Stub networks (networks with only one exit path).
- Enhancing security and control over routing decisions.

### Advantages:

- Simple to implement in small networks.
- Low resource usage.
- Full administrative control.

### Disadvantages:

- Not fault-tolerant (unless backup routes are configured).
- High administrative overhead in large networks.
- Prone to human error.

In summary, **static routing** is best suited for simple, predictable network environments where routes rarely change.
