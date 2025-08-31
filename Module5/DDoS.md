**DDoS** stands for **Distributed Denial of Service**, and it’s one of the most common and disruptive types of cyberattacks on the internet.

---

### 🔹 What Is a DDoS Attack?

A **DDoS attack** is an attempt to **overwhelm a target system** — such as a website, server, or network — with a **flood of internet traffic** from **many distributed sources**, making it **unavailable to legitimate users**.

> 🚫 The goal is not to steal data, but to **disrupt service** — like blocking access to a website, API, or online game.

---

### 🔹 How DDoS Works: Simple Analogy

Imagine a restaurant that can serve 10 customers at a time.

Now, **thousands of fake customers** show up at once, filling every seat, blocking the doors, and tying up the staff.

✅ Real customers can't get in.  
🚫 The restaurant is still open — but **effectively unusable**.

That’s what a DDoS attack does to a website or server.

---

### 🔹 Key Components of a DDoS Attack

| Component         | Description                                                                      |
| ----------------- | -------------------------------------------------------------------------------- |
| **Target**        | A web server, game server, DNS provider, etc.                                    |
| **Attackers**     | Often automated — using **botnets** (networks of infected devices).              |
| **Botnet**        | Thousands (or millions) of compromised devices: computers, IoT cameras, routers. |
| **Traffic Flood** | Massive volume of requests: HTTP, UDP, SYN packets, DNS queries, etc.            |
| **Distributed**   | Traffic comes from **many different IPs** around the world — hard to block.      |

---

### 🔹 Types of DDoS Attacks

DDoS attacks are generally grouped into **three categories** based on the OSI layer they target:

#### 1. **Volume-Based Attacks** (Layer 3–4)

Flood the bandwidth of the target.

| Type                  | Description                                                                       |
| --------------------- | --------------------------------------------------------------------------------- |
| **UDP Flood**         | Sends junk UDP packets to random ports.                                           |
| **ICMP (Ping) Flood** | Overloads with ping requests.                                                     |
| **DNS Amplification** | Exploits open DNS resolvers to amplify traffic (e.g., 1 request → 100x response). |
| **SYN Flood**         | Exploits TCP handshake by sending many SYN requests but never completing them.    |

🎯 Goal: Saturate network bandwidth or exhaust connection tables.

---

#### 2. **Protocol Attacks** (Layer 3–4)

Target server resources or intermediate infrastructure (e.g., firewalls, load balancers).

| Type               | Description                                           |
| ------------------ | ----------------------------------------------------- |
| **Ping of Death**  | Sends malformed or oversized packets.                 |
| **Smurf Attack**   | Uses ICMP with spoofed broadcast to flood the target. |
| **Fraggle Attack** | Similar to Smurf, but uses UDP.                       |

🎯 Goal: Crash systems or consume processing power.

---

#### 3. **Application-Layer Attacks** (Layer 7)

Target the application itself — often mimicking real user behavior.

| Type                         | Description                                                                              |
| ---------------------------- | ---------------------------------------------------------------------------------------- |
| **HTTP Flood**               | Sends massive numbers of HTTP GET/POST requests (e.g., `/index.html`, form submissions). |
| **Slowloris**                | Opens many connections and keeps them open with slow, partial requests.                  |
| **R.U.D.Y. (R U Dead Yet?)** | Sends form data very slowly to keep connections open.                                    |

🎯 Goal: Exhaust server resources (threads, memory, CPU) — harder to detect than volume attacks.

---

### 🔹 Real-World Examples

| Event                     | Impact                                                                                             |
| ------------------------- | -------------------------------------------------------------------------------------------------- |
| **GitHub (2018)**         | Hit with 1.36 Tbps attack — one of the largest ever. Mitigated using a DDoS protection service.    |
| **Dyn DNS Attack (2016)** | A massive Mirai botnet attack on DNS provider Dyn, took down Twitter, Netflix, Reddit, and others. |
| **Banking Sector**        | Frequent DDoS attacks used as distraction during fraud attempts.                                   |

---

### 🔹 How to Detect a DDoS Attack

Signs include:

- Sudden spike in traffic from many IPs.
- Slow performance or timeouts.
- Unavailability of a website or service.
- Unusual traffic patterns (e.g., all requests to one endpoint).
- Firewall or server logs showing floods of SYN packets or UDP traffic.

---

### 🔹 How to Prevent or Mitigate DDoS

| Strategy                                   | Description                                                                                |
| ------------------------------------------ | ------------------------------------------------------------------------------------------ |
| ✅ **Use a CDN / DDoS Protection Service** | Cloudflare, AWS Shield, Akamai, or Azure DDoS Protection absorb and filter attack traffic. |
| ✅ **Rate Limiting**                       | Limit requests per IP or user.                                                             |
| ✅ **Web Application Firewall (WAF)**      | Blocks malicious patterns (e.g., HTTP floods).                                             |
| ✅ **Anycast Network**                     | Distributes traffic across global data centers, absorbing attacks.                         |
| ✅ **Scalable Infrastructure**             | Auto-scale servers to handle traffic surges (but attackers can scale too).                 |
| ✅ **Blackhole Routing**                   | Drop all traffic to the target (nuclear option — stops attack but also legitimate users).  |
| ✅ **Proper Configuration**                | Disable unused services, close open DNS resolvers, update firmware.                        |

---

### 🔹 Difference: DoS vs DDoS

| Feature       | DoS (Denial of Service)  | DDoS (Distributed DoS)         |
| ------------- | ------------------------ | ------------------------------ |
| **Source**    | One machine              | Thousands of machines (botnet) |
| **Scale**     | Smaller, easier to block | Massive, harder to stop        |
| **Detection** | Easier (single source)   | Harder (distributed)           |
| **Impact**    | Usually limited          | Can take down major sites      |

---

### ✅ Summary

**DDoS = Distributed Denial of Service**

- 🎯 Goal: Make a service **unavailable** by overwhelming it.
- 🧩 Method: Flood it with traffic from **many sources** (a botnet).
- 📦 Types: Volume-based, protocol, and application-layer attacks.
- 🛡️ Defense: Use CDNs, WAFs, rate limiting, and DDoS protection services.

It’s like a **digital traffic jam** — not a break-in, but still highly disruptive.

---

[DDoS Training](https://github.com/MohsenEbrahimi86/ACFCP-notes/blob/main/Module5/DDoS-Protection.md)
