# what is subnet mask ?
A subnet mask is a 32-bit value used with an IPv4 address to identify which portion represents
 the network and which portion represents the host.

 [*] Subnet Mask IP address ko 2 parts mein divide karta hai: Network part aur Host part.

# Simple language mein:

IP Address = Network + Host

Subnet Mask batata hai ki IP ka kaunsa part network hai aur kaunsa part device/host hai.

# Real-Life Example

Ek office mein 100 computers hain.

Sabko ek hi network mein rakhne ke bajay network ko organize kiya ja sakta hai.

# Example:

Network:

192.168.1.0/24

Subnet mask:

255.255.255.0

Devices:

192.168.1.10

192.168.1.11

192.168.1.12

192.168.1.13

Ye devices same subnet mein hain.

# 🔥 Subnet Mask ka main kaam

Subnet mask ke 4 important uses yaad rakho:

# 1. Network identify karna

# Example:

IP:

192.168.1.25

Mask:

255.255.255.0

Network:

192.168.1.0

# 2. Host identify karna
192.168.1.25

mein .25 host portion hai.

Matlab network ke andar particular device ko identify karne mein help karta hai.

# 3. Same Network ya Different Network determine karna

#
Suppose:

PC1:

192.168.1.10/24

PC2:

192.168.1.20/24

Dono ka network:

192.168.1.0/24

hai.

Isliye ye same subnet mein hain.

# Lekin:

PC1:

192.168.1.10/24

PC2:

192.168.2.10/24

# Networks:

192.168.1.0/24

192.168.2.0/24

alag hain.

# 🌐 Subnet Mask aur Default Gateway ka relation

Ab previous topic ko connect karo:

PC

IP: 192.168.1.10

Mask: 255.255.255.0

Gateway: 192.168.1.1

# Agar destination:

192.168.1.20

hai → same subnet → directly communicate kar sakta hai.

# Agar destination:

8.8.8.8

hai → different network → Default Gateway ko bhejega.

PC

192.168.1.10

     |
     
     | Different network
     
     ↓
     
Gateway

192.168.1.1

     |
     
     ↓
     
Internet

🔢 Common Subnet Masks

# Cybersecurity/networking mein ye bahut common hain:

CIDR	Subnet Mask	Usable Hosts*

/8	255.0.0.0	~16.7 million

/16	255.255.0.0	65,534

/24	255.255.255.0	254

/25	255.255.255.128	126

/26	255.255.255.192	62

/27	255.255.255.224	30

/28	255.255.255.240	14

/29	255.255.255.248	6

/30	255.255.255.252	2

*Traditional IPv4 subnet calculation; special cases such as point-to-point links and reserved addresses can differ.

# 🧩 /24 ka matlab kya hai?

# Example:

192.168.1.10/24

/24 ka matlab hai:

First 24 bits network portion ke liye reserved hain.

IPv4 mein total:

32 bits

hote hain.

Therefore:

32 - 24 = 8 bits

host ke liye bachte hain.

Host combinations:

2⁸ = 256

Traditional network mein:

256 - 2 = 254 usable hosts

-2 generally network address aur broadcast address ke liye hota hai.

# 🛡️ Cybersecurity mein Subnet Mask kyun important hai?

SOC Analyst ke liye subnet mask sirf networking theory nahi hai. Incident investigation mein iska direct use hota hai.

# 1. Network Segmentation

Companies networks ko different subnets mein divide karti hain:

User Network

10.10.10.0/24

Server Network

10.10.20.0/24

Security Network

10.10.30.0/24

Isse network ko organize aur isolate karna easier hota hai.

# 2. Incident Investigation

Suppose SIEM alert mein:

Source IP:

10.10.20.15

SOC Analyst ko pata hai ki:

10.10.20.0/24

server subnet hai.

To alert ko context milta hai ki suspicious traffic server network se originate hua hai.

# 3. Access Control

Firewall rules mein subnet use ho sakta hai.

# Example:

Allow:

10.10.10.0/24 → Server

Deny:

10.10.50.0/24 → Server

Yaani poore subnet ko rule apply kiya ja sakta hai.

# 4. Suspicious Scanning Identify karna

Agar logs mein:

10.10.10.15

10.10.10.16

10.10.10.17

10.10.10.18

multiple systems ko scan kar rahe hain, SOC Analyst subnet information se samajh sakta hai ki activity kis network segment mein ho rahi hai.

# 💻 Apne PC par Subnet Mask kaise dekhein?
 Windows

CMD open karo:

ipconfig

# Example:

IPv4 Address:

192.168.1.10

Subnet Mask:

255.255.255.0

Default Gateway:

192.168.1.1

Kali/Linux

ip addr

Aur routing information:

ip route
⚠️ Subnet Mask vs IP
