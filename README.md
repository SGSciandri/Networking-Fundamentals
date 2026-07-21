# 🌐 Networking Architecture & Fundamentals
A structured repository dedicated to my study of core networking principles, routing mechanics, protocols, and architectural models.

---

## 🏛️ The 7 Layers of the OSI Model
1. **Layer 7: Application** – User-facing software and communication tools (Google Chrome, Discord, HTTP, DNS).
2. **Layer 6: Presentation** – Handles format translations, string compression algorithms, and SSL/TLS data encryption.
3. **Layer 5: Session** – Controls connection sessions, checkpointing, and separate communication streams.
4. **Layer 4: Transport** – Chooses shipment pathways. **TCP** (Connection-oriented; reliability over speed) or **UDP** (Connectionless; speed over reliability).
5. **Layer 3: Network** – Determines data routing across global infrastructures using logical **IP Addresses**.
6. **Layer 2: Data Link** – Groups data into local frames and handles hop-to-hop physical delivery using burned-in **MAC Addresses**.
7. **Layer 1: Physical** – The physical infrastructure medium (fiber-optic flashes, copper voltage spikes, Wi-Fi waves).

### Data Encapsulation Matrix
As a message descends through the networking stacks, it is wrapped in functional address envelopes at every tier:
$$\text{Data} \rightarrow \text{Segment (TCP)/Datagram (UDP)} \rightarrow \text{Packet (IP)} \rightarrow \text{Frame (MAC)} \rightarrow \text{Bits}$$

---

## 🤝 The TCP 3-Way Handshake
To negotiate sequence synchronization maps safely before exchanging data payloads, connection paths follow a three-step authorization protocol:
1. **`SYN` (Synchronize):** Client sends a random tracking sequence number to the host.
2. **`SYN/ACK` (Synchronize/Acknowledge):** Server acknowledges the client's position and passes back its synchronization counter.
3. **`ACK` (Acknowledge):** Client logs the data connection as live.

---

## 🛜 Core Protocols & Diagnostics
* **DNS (Domain Name System):** Resolves human strings into logical IP nodes.
* **DHCP (Dynamic Host Configuration Protocol):** Dynamically provisions system settings using the **DORA** sequence (**D**iscover, **O**ffer, **R**equest, **A**cknowledge).
* **ARP (Address Resolution Protocol):** Maps a known logical software IP address to an absolute physical hardware MAC address.
* **ICMP (Ping Tool):** Diagnostic framework used to track round-trip connectivity latency (ms) and monitor Time To Live (TTL).
# DNS & Networking Fundamentals

## DNS Hierarchy
`admin.tryhackme.com`
* `.com`: Top-Level Domain (TLD)
* `tryhackme`: Second-Level Domain (SLD)
* `admin`: Subdomain

## Essential DNS Record Types
| Record | Function | Purpose |
| :--- | :--- | :--- |
| **A** | Domain $\rightarrow$ IPv4 | Resolves hostname to 32-bit IP address. |
| **AAAA** | Domain $\rightarrow$ IPv6 | Resolves hostname to 128-bit hex address. |
| **CNAME** | Canonical Name | Aliases one domain name to another domain name. |
| **MX** | Mail Exchange | Directs incoming mail to specified mail servers (uses priority flags). |
| **TXT** | Text Records | Stores arbitrary strings used for ownership verification, SPF, and DKIM. |

## DNS Resolution Order
1. **Local OS Cache & Hosts File**
2. **Recursive Resolver** (ISP or public resolvers like `1.1.1.1` / `8.8.8.8`)
3. **Root Name Servers** (Directs query to designated TLD server)
4. **TLD Name Servers** (Directs query to target Authoritative server)
5. **Authoritative Name Server** (Final source of truth containing actual records)
