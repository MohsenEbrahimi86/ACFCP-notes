**Dynamic DNS (DDNS)** is a method that automatically updates a domain name's IP address in the DNS system whenever the IP address changes—without manual intervention. It’s especially useful when a device (like a home router, security camera, or server) is assigned a **dynamic IP address** by an Internet Service Provider (ISP), which can change over time.

---

### 🔹 Why Is Dynamic DNS Needed?

Most residential internet connections use **dynamic IP addresses**, meaning:

- Your public IP address can change after a reboot, ISP maintenance, or lease expiration.
- This makes it hard to access devices at home (e.g., a personal website, security camera, or remote desktop) using a fixed domain name.

**Dynamic DNS solves this** by linking a domain name (like `myhome.ddns.net`) to your changing IP address.

---

### 🔹 How Dynamic DNS Works

1. **Client Software or Device**: A DDNS client (on a router, computer, or IoT device) runs and checks your current public IP address regularly.
2. **IP Change Detection**: If the IP changes, the client detects it.
3. **Update Request**: The client sends an update request to a **DDNS service provider** (e.g., No-IP, DynDNS, DuckDNS).
4. **DNS Record Update**: The DDNS provider updates the associated **A record** (or AAAA for IPv6) with the new IP address.
5. **Domain Stays Accessible**: Now, anyone accessing your domain name is directed to your current IP address.

---

### 🔹 Example Use Cases

- **Remote Access**: Connect to a home computer or NAS (Network Attached Storage) via a consistent domain name.
- **Security Cameras**: View your home surveillance system remotely.
- **Hosting a Server**: Run a web, game, or Minecraft server from home without a static IP.
- **IoT Devices**: Access smart devices securely over the internet.

---

### 🔹 How to Set Up Dynamic DNS

1. **Sign up** with a DDNS provider and choose a hostname (e.g., `yourname.ddns.net`).
2. **Configure your router or device** with DDNS settings (most modern routers support DDNS).
3. **Enter credentials** (username, password, domain) provided by the DDNS service.
4. **Enable the DDNS client**—it runs in the background and updates the IP automatically.

---

### 🔹 Limitations

- **Free DDNS services** may require you to **renew the hostname** every 30–60 days to prevent expiration.
- Slight delay in IP update propagation (usually under a minute).
- Not as reliable as a **static IP address** (offered by business ISPs), but much more affordable.

---

### 🔹 DDNS vs Static DNS

| Feature         | Dynamic DNS (DDNS)           | Static DNS                        |
| --------------- | ---------------------------- | --------------------------------- |
| IP Address Type | Changes frequently           | Fixed (never changes)             |
| Cost            | Often free or low-cost       | Requires static IP (often costly) |
| Setup           | Requires DDNS client/service | Manual DNS record update          |
| Use Case        | Home servers, remote access  | Business websites, servers        |

---

### ✅ Summary

**Dynamic DNS (DDNS)** is a smart, automated way to keep a domain name pointing to a device with a changing IP address. It bridges the gap between dynamic internet connections and the need for reliable remote access—making it a powerful tool for home users, hobbyists, and small businesses.
