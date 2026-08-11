# WHAT IS DHCP?
DHCP (Dynamic Host Configuration Protocol) is a network protocol that automatically provides devices with network configuration 
such as IP address, subnet mask, default gateway, and DNS server information.

[*] DHCP ek network protocol hai jo network mein connected devices ko automatically
 IP address aur doosri network settings provide karta hai, jaise:

.IP Address

.Subnet Mask

.Default Gateway

.DNS Server

.IP Lease Time

# Example-:

Jab tum laptop ko Wi-Fi se connect karte ho:

Laptop

   ↓
   
DHCP Server

   ↓
   
IP Address: 192.168.1.10

Subnet Mask: 255.255.255.0

Gateway: 192.168.1.1

DNS: 8.8.8.8

Tumhe manually IP configure karne ki zarurat nahi padti.

# 2. DHCP ka main kaam kya hai?

DHCP ka primary purpose hai:

Automatically assign network configuration to clients.

# For example:

Device → DHCP Server

"Sir, mujhe network configuration chahiye."

DHCP Server →

IP:       192.168.1.25

Subnet:   255.255.255.0

Gateway:  192.168.1.1

DNS:      8.8.8.8

# . DHCP ke important components

DHCP environment mein mainly:

# 1. DHCP Client

Jo device IP address maangta hai.

# Examples:

Laptop

Desktop

Mobile

Printer

IoT device

# 2. DHCP Server

Jo IP address aur network configuration provide karta hai.

# Example:

Router

DHCP Server

Windows Server

Linux Server

# 3. DHCP Lease

DHCP usually IP address permanently nahi, balki ek specific time ke liye assign karta hai.

# Example:

IP Address: 192.168.1.20

Lease Time: 8 Hours

Lease expire hone se pehle client IP ko renew kar sakta hai.

# 4. DHCP kaise kaam karta hai? — DORA

DHCP ka sabse important concept hai:

# DORA
D = Discover

O = Offer

R = Request

A = Acknowledgement

#Step 1 — DHCP Discover

Client network mein broadcast karta hai:

"Kya koi DHCP Server available hai?"

Client

   |
   
   | DHCP Discover
   
   ↓
   
Network

# Step 2 — DHCP Offer

DHCP Server response karta hai:

"Haan, main available hoon. Main tumhe ye IP de sakta hoon."

# Example:

DHCP Server

     |
     
     | DHCP Offer
     
     ↓
     
IP: 192.168.1.20

# Step 3 — DHCP Request

Client kehta hai:

"Mujhe ye IP address chahiye."

Client

   |
   
   | DHCP Request
   
   ↓
   
DHCP Server

# Step 4 — DHCP ACK

Server confirm karta hai:

"Okay, ye IP tumhara hai."

DHCP Server

   |
   
   | DHCP ACK
   
   ↓
   
Client

IP = 192.168.1.20

# Cybersecurity mein DHCP important kyun hai?

SOC Analyst ko DHCP logs se device aur IP address ka relationship samajhne mein help milti hai.

# Example:

10:30 AM

IP: 192.168.1.50

MAC: AA:BB:CC:DD:EE:FF

Hostname: DESKTOP-01


# SOC analyst investigate kar raha hai:

"10:30 AM par 192.168.1.50 kis device ko assigned tha?"

DHCP logs useful ho sakte hain.

# 9. DHCP Logs — SOC Analyst ke liye

Suppose kisi suspicious IP se attack detect hua:

Source IP:

192.168.1.50

# SOC analyst ko pata lagana hai:

Ye IP kis machine ko assigned tha?

DHCP server logs mein search kiya ja sakta hai:

IP Address       MAC Address          Hostname

192.168.1.50     AA:BB:CC:11:22:33    PC-01

Ab analyst potentially identify kar sakta hai ki us IP ko kis client ne lease kiya tha.

# Important:

DHCP logs + Firewall logs + DNS logs + Endpoint logs

ko combine karne se investigation strong hoti hai.

# 10. DHCP Security Attacks

Cybersecurity mein DHCP ke against kuch attacks important hain.

# A. Rogue DHCP Server

Attacker network mein unauthorized DHCP server introduce karne ki koshish karta hai.

Normal:

Client

   ↓
   
Legitimate DHCP Server

   ↓
   
Correct Network Configuration

# Rogue scenario:

Client

   ↓
   
Rogue DHCP Server

   ↓
   
Malicious/Wrong Configuration

# Isse attacker potentially:

Wrong gateway provide kar sakta hai

Malicious DNS server provide kar sakta hai

Network traffic ko redirect karne ki situation create kar sakta hai

# SOC perspective:

Unauthorized DHCP server activity is a security indicator that should be investigated.

# 11. DHCP Starvation Attack

DHCP server ke available IP addresses ko exhaust karne ki attack technique ko DHCP Starvation kaha jata hai.

# Example:

DHCP Pool

192.168.1.10

192.168.1.11

192.168.1.12

192.168.1.100

Agar pool ke addresses maliciously consume ho jayein:

Available IPs = 0

To legitimate users ko IP address milne mein problem ho sakti hai.

# SOC Analyst indicators:
Unusual number of DHCP requests

Large number of different MAC addresses

DHCP pool exhaustion

Multiple failed/abnormal leases

# 12. DHCP Spoofing / Rogue DHCP

SOC mein ye distinction yaad rakho:

Legitimate DHCP Server

Client → DHCP Server

          ↓
          
      Correct IP
      
      Correct Gateway
      
      Correct DNS

# Rogue DHCP

Client

  ↓
  
Unauthorized DHCP Server

  ↓
  
Suspicious Configuration

# SOC analyst ko investigate karna chahiye:

DHCP server ka source

MAC address

DHCP logs

Switch logs

Network traffic

DNS configuration

Gateway configuration

# 13. Wireshark mein DHCP

Tum Wireshark seekh rahe ho, isliye DHCP ko Wireshark mein dekhna bahut important practical skill hai.

# Wireshark mein filter:

dhcp

# ya commonly:

bootp

# DHCP packets capture karte waqt tum DORA sequence dekh sakte ho:

DHCP Discover

       ↓
       
DHCP Offer

       ↓
       
DHCP Request

       ↓
       
DHCP ACK

# Wireshark mein tum inspect kar sakte ho:

Client MAC address

Requested IP

Offered IP

DHCP Server

Hostname

Lease information

DHCP message type
