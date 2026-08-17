# Day 10 - Networking Basics

## Overview

Linux provides networking commands to check connectivity, inspect network interfaces, view routing information, test ports, and troubleshoot DNS and network connections.

---

# Connectivity & Configuration

## ping

Tests connectivity to a host by sending ICMP packets.

```bash
ping <host>
```

Example:

```bash
ping google.com
```

Stop with `Ctrl + C`.

---

## ip a

Displays IP addresses assigned to network interfaces.

```bash
ip a
```

Useful for finding the machine's IPv4 and IPv6 addresses.

---

## ip link

Displays network interfaces and their state.

```bash
ip link
```

Common states:

- `UP` → Interface is active.
- `DOWN` → Interface is inactive.

---

## ifconfig

Displays network interface information.

```bash
ifconfig
```

`ifconfig` is a legacy command. Modern Linux systems generally use the `ip` command instead.

---

## hostname

Displays the system hostname.

```bash
hostname
```

---

## hostname -I

Displays the IP addresses assigned to the machine.

```bash
hostname -I
```

---

# Routing & Network Information

## ip route

Displays the system's routing table.

```bash
ip route
```

It shows where network traffic is sent and which interface or gateway is used.

---

## ip neigh

Displays the IP-to-MAC address neighbor table.

```bash
ip neigh
```

Useful for viewing devices recently discovered on the local network.

---

# Checking Network Ports

## ss

Displays network sockets and connections.

```bash
ss
```

To show listening TCP and UDP ports:

```bash
ss -tuln
```

Options:

- `-t` → TCP
- `-u` → UDP
- `-l` → Listening
- `-n` → Show numerical addresses and ports

---

# Data Transfer

## curl

Transfers data from or to a server using a URL.

```bash
curl <url>
```

Example:

```bash
curl https://example.com
```

Useful for testing HTTP/HTTPS connectivity and interacting with APIs.

---

## wget

Downloads files from the web.

```bash
wget <url>
```

Example:

```bash
wget https://example.com/file.zip
```

---

# DNS

## nslookup

Queries DNS information for a domain.

```bash
nslookup <domain>
```

Example:

```bash
nslookup google.com
```

---

## dig

Performs detailed DNS queries.

```bash
dig <domain>
```

Example:

```bash
dig google.com
```

`dig` provides more detailed DNS information than `nslookup`.

---

# Network Path

## traceroute

Shows the network path taken by packets to reach a host.

```bash
traceroute <host>
```

Example:

```bash
traceroute google.com
```

Useful for identifying where network delays or connectivity problems occur.

---

# Hostname Information

## hostname -f

Displays the fully qualified domain name (FQDN).

```bash
hostname -f
```

---

# Important Points

- `ping` → Test basic connectivity.
- `ip a` → Check IP addresses.
- `ip link` → Check network interfaces and their state.
- `hostname` → Check the system hostname.
- `ip route` → Check routing information.
- `ip neigh` → View local network neighbors.
- `ss` → Check network connections and listening ports.
- `curl` → Test URLs and transfer data.
- `wget` → Download files.
- `nslookup` and `dig` → Troubleshoot DNS.
- `traceroute` → Trace the network path to a host.
- `ifconfig` is a legacy command; `ip` is preferred on modern Linux systems.
