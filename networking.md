# Linux Networking Notes

## 1. View Network Information

### ip (modern command)
```bash
ip a
```
Shows all interfaces and IPs.

```bash
ip link
```
Shows network interfaces.

```bash
ip route
```
Displays routing table.

## 2. Legacy Network Commands

### ifconfig
```bash
ifconfig
```

### route
```bash
route -n
```

## 3. Connectivity Testing

### ping
```bash
ping google.com
```

### traceroute
```bash
traceroute google.com
```

## 4. Network Analysis

### netstat
```bash
netstat -tulnp
```

### ss (modern netstat)
```bash
ss -tulnp
```

## 5. DNS Tools

### dig
```bash
dig google.com
```

### nslookup
```bash
nslookup google.com
```

## 6. Network Scanning

### nmap
```bash
nmap -sV 192.168.1.10
```

```bash
nmap -sn 192.168.1.0/24
```

## 7. Local Network Tools

### arp
```bash
arp -a
```

### ip neigh
```bash
ip neigh
```

## 8. Important Network Files

| File | Purpose |
|------|---------|
| `/etc/hosts` | Local hostname-to-IP mapping |
| `/etc/resolv.conf` | DNS configuration |
| `/etc/network/interfaces` | Network config (Debian legacy) |
| `/etc/sysconfig/network-scripts/` | Network config (RedHat) |

## 9. Network Services

### Restart networking

Debian:
```bash
sudo systemctl restart networking
```

RedHat:
```bash
sudo systemctl restart NetworkManager
```

## 10. Packet Sniffing

### tcpdump
```bash
sudo tcpdump -i eth0
```

```bash
sudo tcpdump -i wlan0 port 80
```

