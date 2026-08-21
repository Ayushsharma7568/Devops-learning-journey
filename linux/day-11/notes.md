# Day 11 – DNS & Routing

## 1. What is DNS?

DNS stands for **Domain Name System**.

It translates human-readable domain names into IP addresses that computers use to communicate.

Example:

```text
google.com
     ↓
142.250.x.x
```

Instead of remembering an IP address, users can simply use a domain name.

---

## 2. Why is DNS important?

Computers communicate using IP addresses, but remembering IP addresses for every website would be difficult.

DNS provides a system that maps:

```text
Domain Name → IP Address
```

Example:

```text
github.com → IP Address
```

---

## 3. DNS Resolution

When a user enters a domain name, the system performs DNS resolution to find the corresponding IP address.

Basic flow:

```text
User
  ↓
Browser
  ↓
DNS Resolver
  ↓
DNS Servers
  ↓
IP Address
  ↓
Web Server
```

Once the IP address is obtained, the system can connect to the destination server.

---

## 4. Common DNS Record Types

### A Record

Maps a domain name to an IPv4 address.

```text
example.com → 192.168.1.10
```

### AAAA Record

Maps a domain name to an IPv6 address.

### CNAME Record

Creates an alias from one domain name to another.

```text
www.example.com → example.com
```

### MX Record

Specifies mail servers responsible for receiving email for a domain.

### NS Record

Specifies the authoritative DNS servers for a domain.

---

## 5. nslookup

`nslookup` is used to query DNS information.

Example:

```bash
nslookup google.com
```

It can be used to find the IP address associated with a domain.

---

## 6. dig

`dig` is a more detailed DNS troubleshooting tool.

Example:

```bash
dig google.com
```

It can also query specific DNS records:

```bash
dig google.com A
dig google.com MX
```

For a simple result:

```bash
dig +short google.com
```

---

## 7. What is Routing?

Routing is the process of determining the path that network packets should take from a source to a destination.

Example:

```text
Computer
   ↓
Router
   ↓
Internet
   ↓
Destination Server
```

Routers examine destination IP addresses and decide where packets should be forwarded.

---

## 8. Routing Table

A routing table contains information about available network routes.

To view the routing table:

```bash
ip route
```

Example:

```text
default via 192.168.1.1
192.168.1.0/24 dev eth0
```

The routing table helps the operating system determine where network traffic should go.

---

## 9. ping

`ping` is used to check whether a destination is reachable.

Example:

```bash
ping google.com
```

It sends ICMP packets and measures the response time.

Useful for basic connectivity troubleshooting.

---

## 10. traceroute

`traceroute` shows the path packets take from the local machine to a destination.

Example:

```bash
traceroute google.com
```

It displays the intermediate network hops.

Example:

```text
Computer
   ↓
Router
   ↓
ISP
   ↓
Network Router
   ↓
Google Server
```

This is useful for identifying where network delays or failures may occur.

---

## 11. curl

`curl` is commonly used to communicate with web servers and APIs.

Example:

```bash
curl https://example.com
```

It can also display HTTP headers:

```bash
curl -I https://example.com
```

It is especially useful for testing whether an API or web service is responding.

---

## 12. wget

`wget` is mainly used to download files from the internet.

Example:

```bash
wget https://example.com/file.zip
```

Unlike `curl`, `wget` is commonly used for downloading files directly to disk.

---

## 13. SSH

SSH stands for **Secure Shell**.

It allows a user to securely access a remote machine.

Example:

```bash
ssh user@server-ip
```

SSH is extremely important in Linux administration and cloud environments.

For example, administrators commonly use SSH to connect to Linux EC2 instances.

---

## 14. SCP

SCP stands for **Secure Copy Protocol**.

It allows files to be securely transferred between machines using SSH.

Example:

```bash
scp file.txt user@server:/home/user/
```

It can transfer files:

```text
Local Machine → Remote Machine
```

or:

```text
Remote Machine → Local Machine
```

---

## 15. netstat and ss

Both commands can be used to inspect network connections and listening ports.

### netstat

```bash
netstat -tulnp
```

### ss

```bash
ss -tulnp
```

`ss` is generally preferred on modern Linux systems.

---

## 16. Important Networking Terms

### IP Address

A numerical address used to identify a device on a network.

### Port

A logical endpoint used by applications to communicate over a network.

Examples:

```text
22   → SSH
80   → HTTP
443  → HTTPS
5432 → PostgreSQL
```

### Protocol

A set of rules used for communication between devices.

Examples:

```text
HTTP
HTTPS
TCP
UDP
SSH
DNS
```

### Router

A device that forwards packets between different networks.

### DNS Server

A server that helps resolve domain names into IP addresses.

### Gateway

A device or address through which traffic leaves the local network.

### Socket

A combination of an IP address and port used for network communication.

---

## 17. Useful Troubleshooting Flow

When a website or service cannot be reached, troubleshoot step by step:

```text
1. Check connectivity
       ↓
   ping <host>

2. Check DNS
       ↓
   nslookup <domain>
   dig <domain>

3. Check network route
       ↓
   traceroute <host>
   ip route

4. Check service response
       ↓
   curl <url>

5. Check listening ports
       ↓
   ss -tulnp

6. Check remote server
       ↓
   ssh user@host
```

This provides a basic approach to diagnosing network problems.

---

## 18. Key Takeaways

- DNS converts domain names into IP addresses.
- `nslookup` and `dig` are used for DNS queries.
- Routing determines the path network packets take.
- `ip route` displays the routing table.
- `ping` checks basic connectivity.
- `traceroute` shows the path to a destination.
- `curl` is useful for testing websites and APIs.
- `wget` is mainly used for downloading files.
- `ssh` provides secure remote access.
- `scp` securely transfers files between machines.
- `ss` displays network sockets and listening ports.
- Ports identify network services running on a machine.
