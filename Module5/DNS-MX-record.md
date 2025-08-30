A **DNS MX Record** (Mail Exchange Record) is a type of DNS (Domain Name System) record that specifies the mail servers responsible for receiving email messages on behalf of a domain.

### Purpose:

When someone sends an email to `user@example.com`, the sending mail server performs a DNS lookup to find the **MX records** for `example.com`. These records tell the sender which mail servers are designated to accept incoming emails for that domain.

---

### Key Features of MX Records:

1. **Priority (Preference Value):**

   - MX records include a **priority number** (also called preference value).
   - Lower numbers indicate higher priority.
   - Example:
     ```
     MX 10 mail.example.com
     MX 20 backupmail.example.com
     ```
     Here, `mail.example.com` is tried first. If it's unavailable, the email is sent to `backupmail.example.com`.

2. **Multiple MX Records:**

   - Domains can have multiple MX records for redundancy and load distribution.
   - This ensures email delivery continues even if one server is down.

3. **Points to Hostnames:**
   - MX records must point to **hostnames** (e.g., `mail.example.com`), not IP addresses directly.
   - The hostname should have a corresponding A (or AAAA) record in DNS.

---

### Example:

For the domain `example.com`, the MX records might look like this in DNS configuration:

```
example.com.    IN  MX  10  mail.example.com.
example.com.    IN  MX  20  backup.example.com.
```

This means:

- Email for `example.com` should be delivered to `mail.example.com` first.
- If that server is unreachable, try `backup.example.com`.

---

### Why MX Records Are Important:

- They ensure emails are routed to the correct mail servers.
- They enable reliable email delivery through failover and redundancy.
- Without proper MX records, email may not be delivered to your domain.

---

### Common Mistakes:

- Forgetting to set MX records when setting up email.
- Pointing MX records to a hostname without a valid A record.
- Using incorrect priority values (e.g., higher priority should have lower number).

---

In summary, **MX records are essential for email delivery**, directing sending servers to the correct destination mail servers based on priority and availability.
