A **Reverse Proxy** is a server that sits **in front of one or more origin servers** (like web servers, APIs, or applications) and **intercepts client requests** on their behalf. Unlike a _forward proxy_ (which protects clients), a **reverse proxy protects and enhances servers**.

It acts as a **gateway**, handling incoming traffic before it reaches the actual backend servers.

---

### 🔹 How a Reverse Proxy Works

```
Client → Reverse Proxy → Backend Server (e.g., web app)
         ← Reverse Proxy ← Response
```

1. A client (e.g., browser) requests `https://example.com`.
2. The request goes to the **reverse proxy**, not directly to the backend server.
3. The reverse proxy forwards the request to the appropriate backend server.
4. The backend processes the request and sends the response back to the reverse proxy.
5. The reverse proxy returns the response to the client.

✅ To the client, it appears as if the reverse proxy **is** the server.

---

### 🔹 Key Features & Benefits

| Feature                                | Description                                                                                 |
| -------------------------------------- | ------------------------------------------------------------------------------------------- |
| ✅ **Load Balancing**                  | Distributes traffic across multiple backend servers to improve performance and reliability. |
| ✅ **SSL/TLS Termination**             | Handles HTTPS decryption at the proxy level, reducing load on backend servers.              |
| ✅ **Security & Obfuscation**          | Hides the internal structure of your servers (e.g., IPs, hostnames).                        |
| ✅ **Caching**                         | Stores static content (e.g., images, CSS) to reduce server load and speed up responses.     |
| ✅ **Compression**                     | Compresses responses before sending them to clients.                                        |
| ✅ **Rate Limiting / DDoS Protection** | Blocks abusive traffic before it hits your app.                                             |
| ✅ **URL Rewriting / Path Routing**    | Routes `/api` to one server, `/blog` to another, etc.                                       |
| ✅ **High Availability**               | Can reroute traffic if a backend server fails.                                              |

---

### 🔹 Common Use Cases

| Use Case                              | Example                                                                  |
| ------------------------------------- | ------------------------------------------------------------------------ |
| **Web Acceleration**                  | Cache static assets to reduce load on web servers.                       |
| **Microservices Routing**             | Route `/users` → User Service, `/orders` → Order Service.                |
| **HTTPS Offloading**                  | Reverse proxy handles SSL; internal servers use HTTP.                    |
| **DDoS & Security Protection**        | Cloudflare, AWS WAF, or NGINX block malicious requests.                  |
| **Single Point of Entry**             | All traffic goes through one IP/domain, even with many backend services. |
| **A/B Testing or Canary Deployments** | Send a portion of traffic to a new version of an app.                    |

---

### 🔹 Real-World Examples

| Service                                 | Acts as Reverse Proxy                                                      |
| --------------------------------------- | -------------------------------------------------------------------------- |
| **Cloudflare**                          | Sits in front of websites, providing CDN, security, and caching.           |
| **NGINX**                               | One of the most popular reverse proxies and web servers.                   |
| **Apache HTTP Server (with mod_proxy)** | Can be configured as a reverse proxy.                                      |
| **HAProxy**                             | High-performance load balancer and reverse proxy.                          |
| **Traefik, Envoy, Caddy**               | Modern reverse proxies with auto-configuration (especially in containers). |

---

### 🔹 Example: NGINX as a Reverse Proxy

```nginx
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://192.168.1.10:8000;  # Forward to backend
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

This config tells NGINX:

- Accept requests for `example.com`.
- Forward them to a backend server at `192.168.1.10:8000`.
- Pass along client info so the backend can see the real IP.

---

### 🔹 Reverse Proxy vs Forward Proxy

| Feature                | Reverse Proxy                     | Forward Proxy                       |
| ---------------------- | --------------------------------- | ----------------------------------- |
| **Location**           | Near the **server**               | Near the **client**                 |
| **Purpose**            | Protects/optimizes **servers**    | Controls/protects **clients**       |
| **Who configures it?** | Server admin                      | Client/user                         |
| **Seen by client?**    | Yes — appears as the server       | Yes — must be configured in client  |
| **Hides**              | Backend servers                   | Client IP                           |
| **Use Case**           | Load balancing, security, caching | Content filtering, privacy, logging |

> Think:
>
> - **Forward Proxy**: "I’m protecting **users** from the internet."
> - **Reverse Proxy**: "I’m protecting the **server** from the internet."

---

### 🔹 Security Benefits

- 🛡️ **Shield internal architecture**: Attackers can't see how many servers you have or their IPs.
- 🔐 **Centralized SSL management**: One certificate for all backends.
- 🚫 **Block malicious traffic**: Rate limiting, bot detection, WAF integration.
- 🔄 **Graceful degradation**: Serve cached content if backend is down.

---

### ✅ Summary

A **Reverse Proxy** is a powerful intermediary that:

- Sits **in front of servers**.
- Handles **incoming client requests**.
- Provides **security, performance, scalability, and reliability**.

It’s essential in modern web architectures — used by nearly every major website and cloud service.

---
