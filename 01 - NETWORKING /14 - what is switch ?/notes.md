# what is switch ?
A network switch is a networking device that connects devices within a Local Area Network (LAN) and 
forwards Ethernet frames to the appropriate destination using MAC addresses.

[*] Switch ek networking device hai jo LAN ke andar multiple devices ko connect karta hai aur MAC address 
ke basis par data ko correct device tak forward karta hai.

# Real-Life Example

Maan lo ek office mein:

             SWITCH
             
          /     |     \
          
         /      |      \
         
       PC1     PC2     PC3
       
       💻       💻       💻

# PC1 ko PC3 ko data bhejna hai:

PC1

 ↓
 
Switch

 ↓
 
PC3

# Switch check karega:

"PC3 ka MAC Address kis port par connected hai?"

Phir frame ko usi port par forward karega.

# 🧠 Switch kaise kaam karta hai?

Switch primarily MAC Address Table maintain karta hai.

# Example:

MAC Address	Port

AA:AA:AA:AA:AA:01	Port 1

BB:BB:BB:BB:BB:02	Port 2

CC:CC:CC:CC:CC:03	Port 3

# Suppose:

PC1 → PC3

PC3 ka MAC:

CC:CC:CC:CC:CC:03

# Switch table dekhta hai:

CC:CC:CC:CC:CC:03 → Port 3

Aur frame:

PC1

 ↓
 
Switch

 ↓
 
Port 3

 ↓
 
PC3

# 🔥 Switch MAC Address kaise seekhta hai?

Ye bahut important hai.

# Maan lo:

PC1 → Switch Port 1

PC1 ek Ethernet frame switch ko bhejta hai.

Frame ka Source MAC Address dekhkar switch learn karta hai:

PC1 MAC → Port 1

Isi process ko MAC address learning kehte hain.

# Example:

Frame arrives

     ↓
     
Source MAC dekho

     ↓
     
MAC table mein save karo

     ↓
     
Destination MAC dekho

     ↓
     
Correct port par forward karo

# 📦 Switch Frame ko kaise Forward karta hai?

Yahan ek important distinction hai:

Switch mainly Layer 2 device hai.

# OSI Model:

Layer 7 → Application

Layer 6 → Presentation

Layer 5 → Session

Layer 4 → Transport

Layer 3 → Network

Layer 2 → Data Link ← SWITCH

Layer 1 → Physical

# Cybersecurity mein Switch important kyun hai?

SOC Analyst ke liye switch samajhna important hai kyunki enterprise network ka large portion switches ke through connected hota hai.

# 1. Network Traffic Analysis

Network mein traffic flow samajhne ke liye:

Endpoint

   ↓
   
Switch

   ↓
   
Router/Firewall

   ↓
   
Internet

SOC investigation mein ye architecture useful hota hai.

# 2. MAC Address Investigation

Suppose suspicious device ka MAC address mila:

AA:BB:CC:DD:EE:FF

Switch ki MAC table se network administrator determine kar sakta hai ki MAC kis switch port par learned hai.

# Example:

MAC:

AA:BB:CC:DD:EE:FF

Port:

Fa0/12

Isse physical/network location identify karne mein help mil sakti hai.

# 3. MAC Flooding Attack


Cybersecurity mein switch se related important attack hai:

MAC Flooding

Attacker switch ko bahut saare fake/random MAC addresses wale frames bhejne ki koshish kar sakta hai.

# Conceptually:

Attacker

   ↓
   
Many fake MAC addresses

   ↓
   
Switch

   ↓
   
MAC Table pressure

Agar switch ki MAC table exhaust ho jaye, misbehavior ho sakta hai, aur kuch configurations 
mein switch unknown destinations ke frames ko multiple ports par flood kar sakta hai.

Isliye MAC flooding ek important Layer-2 security concept hai.

# 4. ARP Spoofing

Switch environment mein ARP spoofing/poisoning bhi important hai.

# Example:

Victim

   ↓
   
ARP information manipulated

   ↓
   
Attacker

   ↓
   
Traffic interception

Isse attacker traffic ko apne system ki taraf redirect karne ki koshish kar sakta hai.

SOC Analyst ko suspicious ARP behavior detect karna aana chahiye.

# 5. VLAN Security

Enterprise networks mein switches par VLANs use kiye jaate hain.

# Example:

VLAN 10 → Employees

VLAN 20 → Servers

VLAN 30 → Guest

# Conceptually:

              SWITCH
              
          /      |       \
          
       VLAN10  VLAN20   VLAN30
       
       Users   Servers   Guest

VLANs network segmentation provide karte hain.

Cybersecurity mein important question:

Kya VLANs properly isolated hain?

# 6. Port Security

Managed switches mein Port Security configure ki ja sakti hai.

# Example:

Port 1

Allowed MAC:

AA:BB:CC:11:22:33

Agar unauthorized device connect ho:

Unknown MAC

     ↓
     
  Switch
  
     ↓
     
Security violation

Organization configuration ke according port restrict/shutdown ya alert generate kar sakti hai.

# 7. SPAN / Port Mirroring

SOC/network monitoring mein ye bahut useful concept hai.

SPAN (Switched Port Analyzer) ya Port Mirroring switch traffic ki copy monitoring device ko bhejne ke liye use kiya ja sakta hai.

# Example:

PCs
 |
 
 |
 
Switch

 | \
 
 |  \----> Monitoring Port
 
 |             ↓
 
 |         Wireshark
 
 |
 
Router

Isse network traffic analysis ke liye packet capture possible hota hai.

# 🦈 Wireshark + Switch

Tum Wireshark padh rahe ho, isliye ye connection important hai.

# Example:

Network

   ↓
   
Switch

   ↓
   
Traffic

   ↓
   
SPAN/Mirror

   ↓
   
Wireshark

   ↓
   
# SOC Analyst

SOC Analyst packet capture mein dekh sakta hai:

Source MAC

Destination MAC

Source IP

Destination IP

Protocol

Ports

# ARP activity
Suspicious communication

🔐 Managed vs Unmanaged Switch

Unmanaged Switch

Simple plug-and-play:

PC → Switch → PC

Usually advanced configuration nahi hoti.

Managed Switch

Administrator configuration kar sakta hai:

VLAN

Port Security

STP

SPAN

MAC address table

Access/Trunk ports

Monitoring

Authentication features

Cybersecurity/enterprise networks mein managed switches bahut important hain.

Switch Layer 2 par Ethernet Frames aur MAC Addresses ke saath kaam karta hai.

Router primarily Layer 3 par IP addresses ke basis par routing karta hai.
