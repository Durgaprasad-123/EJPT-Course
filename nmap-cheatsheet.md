# 🧠 Nmap Cheatsheet
---
## nmap -p<Port number> --script vuln <ip>

## 🧭 Host Discovery (Ping Scans)
Use `-sn` to perform **discovery without port scanning**.

| Scan Type | Example Command |
|-----------|------------------|
| ARP Scan | `sudo nmap -PR -sn 192.168.1.0/24` |
| ICMP Echo | `sudo nmap -PE -sn 192.168.1.0/24` |
| ICMP Timestamp | `sudo nmap -PP -sn 192.168.1.0/24` |
| ICMP Address Mask | `sudo nmap -PM -sn 192.168.1.0/24` |
| TCP SYN Ping | `sudo nmap -PS22,80,443 -sn 192.168.1.0/30` |
| TCP ACK Ping | `sudo nmap -PA22,80,443 -sn 192.168.1.0/30` |
| UDP Ping | `sudo nmap -PU53,161,162 -sn 192.168.1.0/30` |

### Additional Options
| Option | Purpose |
|--------|---------|
| `-n` | no DNS resolution |
| `-R` | reverse DNS lookup |
| `-sn` | host discovery only |

---

## 📦 Port Scanning

| Port Scan Type | Example Command |
|----------------|------------------|
| TCP Connect Scan | `nmap -sT <IP>` |
| TCP SYN Scan | `sudo nmap -sS <IP>` |
| UDP Scan | `sudo nmap -sU <IP>` |

### Port Range & Performance
| Option | Purpose |
|--------|---------|
| `-p-` | all ports (1-65535) |
| `-p1-1023` | scan ports 1–1023 |
| `-F` | fast scan (100 common ports) |
| `-r` | scan in order |
| `-T0` to `-T5` | speed (T5 is fastest) |
| `--max-rate 50` | max 50 packets/sec |
| `--min-rate 15` | at least 15 packets/sec |
| `--min-parallelism 100` | min. 100 parallel probes |

---

## 🔍 Service & Version Detection

| Option | Purpose |
|--------|---------|
| `-sV` | detect service version |
| `--version-light` | try 2 common probes |
| `--version-all` | try all probes |

---

## 💻 OS Detection & Scripting

| Option | Purpose |
|--------|---------|
| `-O` | detect OS |
| `--traceroute` | show network path |
| `--script=<script>` | run specific scripts |
| `-sC` or `--script=default` | default scripts |
| `-A` | aggressive scan: `-sV -O -sC --traceroute` |

---

## 💾 Output Formats

| Option | Purpose |
|--------|---------|
| `-oN` | normal output |
| `-oG` | grepable output |
| `-oX` | XML output |
| `-oA` | all formats (normal, grepable, XML) |

---

## 📌 Pro tip:
Use `-vv` or `-d` for **verbose** or **debugging** output if you want to dig deeper.
