# what is MAC Address
**MAC (Media Access Control) Address** is a unique hardware/network identifier assigned to a network interface, such as a Network Interface Card (NIC). It operates at **Layer 2 (Data Link Layer)** of the OSI Model and is primarily used for communication within a local network.

[*] MAC Address ek **unique network identifier** hota hai jo kisi device ke **network interface (NIC)** ko identify karta hai.

## 🔹 MAC Address Example-:

A MAC Address generally 48 bits ka hota hai aur hexadecimal format mein represent kiya jata hai.
00:1A:2B:3C:4D:5E

Isko different formats mein bhi represent kiya ja sakta hai:

00:1A:2B:3C:4D:5E

00-1A-2B-3C-4D-5E

001A.2B3C.4D5E

## 🔹 Main Functions of a MAC Address

### 1. Device Identification

MAC Address local network mein kisi network interface ko identify karne mein help karta hai.

Device: Laptop

MAC: 00:1A:2B:3C:4D:5E
### 2. Local Network Communication

MAC Address **Layer 2 communication** mein important role play karta hai.

Jab ek device same local network mein doosre device ko data bhejta hai, to Ethernet frame mein source aur destination MAC addresses hoti hain.

Source MAC-->network switch--->destination mac----> Target device
  
### 3. Switch Frame Forwarding

Network switch MAC addresses ko use karke decide karta hai ki Ethernet frame ko kis port par forward karna hai.

# Example-:

MAC Address          Switch Port

AA:AA:AA:11:11:11    Port 1

BB:BB:BB:22:22:22    Port 2

CC:CC:CC:33:33:33    Port 3

# Agar frame ka destination MAC hai-:

BB:BB:BB:22:22:22

to switch us frame ko corresponding port par forward karega.

# 🔐 MAC Address in Cybersecurity-:

MAC Address cybersecurity aur network security mein bhi useful hai.

## 1. Device Identification

Security teams MAC Address ki help se network par connected devices ko identify aur correlate kar sakti hain.

## 2. Network Monitoring

Network monitoring tools aur logs mein MAC Address source aur destination devices ko correlate karne mein useful ho sakta hai.

# Example-:

Source IP: 192.168.1.10

Source MAC: AA:BB:CC:11:22:33

Destination IP: 192.168.1.20

## 3. ARP Investigation

ARP (Address Resolution Protocol) IP Address ko MAC Address ke saath map karta hai.

# Example-:

192.168.1.10 → AA:BB:CC:11:22:33

SOC Analyst suspicious ARP activity ko investigate karte waqt IP-MAC mappings ko examine kar sakta hai.

## 4. MAC Spoofing Detection

MAC Spoofing mein attacker apne network interface ka MAC Address change karke kisi doosre device ke MAC Address jaisa appear karne ki koshish kar sakta hai.

# Example-:

Authorized Device:

MAC = AA:BB:CC:11:22:33

Attacker:

MAC = AA:BB:CC:11:22:33

Agar security monitoring mein unusual MAC activity detect hoti hai, SOC Analyst further investigation kar sakta hai.

# 🛡️ MAC Address for SOC Analyst L1

SOC Analyst ke liye MAC Address important hai because it can help with:

* Device identification
  
* Network event correlation
  
* ARP investigation
  
* Layer 2 traffic analysis
  
* Switch-level investigation
  
* Suspicious device identification
  
* MAC spoofing investigation

### Example SOC Investigation

# Suppose SIEM mein alert generate hota hai-:

Alert: Suspicious ARP Activity

Source IP: 192.168.1.25

MAC Address: AA:BB:CC:11:22:33


# SOC Analyst-:

Alert

  ↓
  
Source IP & MAC identify

  ↓
  
Device/Host identify

  ↓
  
Network & security logs check

  ↓
  
ARP activity investigate

  ↓
  
Determine whether activity is legitimate or suspicious

