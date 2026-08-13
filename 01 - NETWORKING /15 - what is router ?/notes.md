# what is router ?
A router is a networking device that connects different networks and forwards IP packets between them based on their destination IP address.

[*] Router ek device hai jo different networks ko connect karta hai aur data packets ko unke destination IP address 
ke basis par sahi network/device ki taraforward kf arta hai.

# Simple Example-:

Tumhare ghar mein:

 Laptop ──┐

 Mobile ──┼──> Wi-Fi Router ───> Internet

PC ──────┘

Router tumhare local network (LAN) ko Internet/WAN se connect karta h 

# 2. Router ka main kaam kya hai?

Router ke important functions:

# 🔹 1. Different Networks Connect Karna

# Example:

LAN

192.168.1.0/24

       │
       
       ▼
       
     ROUTER
    
       │
       
       ▼
       
     Internet

Router LAN aur Internet jaise different networks ke beech communication karata hai.

# 2. Packet Forwarding

Jab tum browser mein website open karte ho:

Laptop

   │
   
   │ Packet
   
   ▼
   
  Router

   │
   
   ▼
Internet

   │
   
   ▼
   
Web Server

Router packet ke destination IP address ko dekhta hai aur decide karta hai ki packet ko kis direction mein bhejna hai.

# 3. Router aur Default Gateway ka relation

Ye SOC Analyst ke liye bahut important concept hai.

# Suppose:

Laptop IP:       192.168.1.10

Subnet Mask:     255.255.255.0

Default Gateway: 192.168.1.1

# Yahan:

Laptop

192.168.1.10

     │
     
     ▼
     
   Router

192.168.1.1

     │
     
     ▼
     
  Internet

Default Gateway generally router ka LAN-side IP address hota hai.

Agar laptop ko apne local network ke bahar kisi destination se communicate karna hai, to packet usually default gateway/router ko bheja jata hai.

# 4. Router routing table ka use karta hai

Router ke paas routing table hoti hai.

# Example:

Destination Network	Next Hop / Interface

192.168.1.0/24	LAN

10.0.0.0/8	Router B

0.0.0.0/0	ISP

Router destination IP ko routing table se compare karta hai aur best route select karta hai.

# Important:

0.0.0.0/0 ko generally default route kaha jata hai.

# . Router cybersecurity mein kyun important hai?

Ab sabse important part. 🔥

SOC Analyst ke perspective se router ko samajhna zaroori hai because router network traffic ka important point hota hai.

# Security mein router se related cheezein:
Routing

ACLs

NAT

Firewall features

VPN

Logging

Traffic filtering

Network segmentation

DHCP

DNS forwarding

Remote administration

Agar router ko destination ke liye specific route nahi milta, to default route use ho sakta hai.

