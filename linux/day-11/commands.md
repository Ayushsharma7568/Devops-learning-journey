# Day 11 – DNS & Routing Commands

## 1. curl

### Syntax
```bash
curl <url>
```

### Description
Transfers data from or to a URL. Commonly used for testing APIs and checking web servers.

### Examples
```bash
curl https://example.com
curl -I https://example.com
curl -X GET https://example.com
```

---

## 2. wget

### Syntax
```bash
wget <url>
```

### Description
Downloads files from the web directly to the local system.

### Examples
```bash
wget https://example.com/file.zip
wget -O myfile.zip https://example.com/file.zip
```

---

## 3. nslookup

### Syntax
```bash
nslookup <domain>
```

### Description
Queries DNS to find the IP address associated with a domain.

### Examples
```bash
nslookup google.com
nslookup github.com
```

---

## 4. dig

### Syntax
```bash
dig <domain>
```

### Description
Performs detailed DNS lookups and displays DNS record information.

### Examples
```bash
dig google.com
dig google.com A
dig google.com MX
```

---

## 5. traceroute

### Syntax
```bash
traceroute <host>
```

### Description
Shows the network path and hops that packets take to reach a destination.

### Examples
```bash
traceroute google.com
traceroute 8.8.8.8
```

> On some systems, `traceroute` may need to be installed separately.

---

## 6. netstat

### Syntax
```bash
netstat -tulnp
```

### Description
Displays network connections, listening ports, and associated processes.

### Examples
```bash
netstat -tuln
netstat -tulnp
netstat -an
```

---

## 7. ss

### Syntax
```bash
ss -tulnp
```

### Description
A modern replacement for `netstat`. It displays socket statistics, listening ports, and network connections.

### Examples
```bash
ss -tuln
ss -tulnp
ss -s
```

---

## 8. scp

### Syntax
```bash
scp file user@host:/path
```

### Description
Securely copies files between machines using SSH.

### Examples
```bash
scp file.txt user@192.168.1.10:/home/user/
scp user@192.168.1.10:/home/user/file.txt .
scp -r myfolder user@192.168.1.10:/home/user/
```

---

## 9. ssh

### Syntax
```bash
ssh user@host
```

### Description
Creates a secure remote shell session with another machine over SSH.

### Examples
```bash
ssh user@192.168.1.10
ssh ubuntu@server-ip
```

---

# Additional Useful DNS & Networking Commands

## 10. ping

### Syntax
```bash
ping <host>
```

### Description
Tests whether a host is reachable and measures the round-trip time of packets.

### Examples
```bash
ping google.com
ping 8.8.8.8
ping -c 4 google.com
```

---

## 11. hostname

### Syntax
```bash
hostname
```

### Description
Displays the hostname of the current machine.

### Examples
```bash
hostname
hostname -I
```

---

## 12. ip addr

### Syntax
```bash
ip addr
```

### Description
Displays network interfaces and their assigned IP addresses.

### Examples
```bash
ip addr
ip addr show
ip -br addr
```

---

## 13. ip route

### Syntax
```bash
ip route
```

### Description
Displays the system's routing table and shows how network traffic is routed.

### Examples
```bash
ip route
ip route show
```

---

## 14. hostnamectl

### Syntax
```bash
hostnamectl
```

### Description
Displays system hostname and related system information.

### Examples
```bash
hostnamectl
hostnamectl status
```

---

## 15. dig +short

### Syntax
```bash
dig +short <domain>
```

### Description
Displays a simplified DNS lookup result, usually showing only the IP address.

### Examples
```bash
dig +short google.com
dig +short github.com
```

---

## 16. getent hosts

### Syntax
```bash
getent hosts <domain>
```

### Description
Queries the system's configured name service to resolve a hostname to an IP address.

### Examples
```bash
getent hosts google.com
getent hosts github.com
```
