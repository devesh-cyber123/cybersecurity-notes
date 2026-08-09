# WHAT IS IP ADDRESS?
An IP (Internet Protocol) address is a unique logical address assigned to a device on a network to identify 
the device and enable communication between devices.

[*] IP Address ek logical address hota hai jo network mein kisi device ko identify karta hai.

Jaise real life mein kisi person/house ko identify karne ke liye address hota hai, waise hi network mein device
 ko identify aur communicate karne ke liye IP address use hota hai.
 # EXAMPLE-:
 Computer A
IP Address: 192.168.1.10

Computer B
IP Address: 192.168.1.20

Agar Computer A ko Computer B ko data bhejna hai, to network ko pata hona chahiye ki data kis device ko deliver karna hai.

# Purpose of IP Address-:
IP Address ke mainly 2 important purposes hote hain.
# 1. Identification
An IP address identifies a device on a network.

[*] IP address network mein device ki identity batata hai.
# EXAMPLE-:
PC     → 192.168.1.10

Server → 192.168.1.20

Router → 192.168.1.1

# 2. Routing
An IP address helps routers determine where network packets should be forwarded.

[*] IP address router ko help karta hai determine karne mein ki data packet ko kis destination ki taraf forward karna hai.
# EXAMPLE-:
    PC -----ROUTER-----SERVER
    
# Versions of IP Address-:
IP ke mainly 2 versions hain:
 1. IPv4
 2. IPv6
# 1.IPv4-:
IPv4 is a 32-bit addressing system used to identify devices on an IP network.

[*] IPv4 ek 32-bit addressing system hai jo network mein devices ko identify karne ke liye use hota hai.
# EXAMPLE-:
192.168.1.10
# IPv4 mein 4 octets hote hain:
192 . 168 . 1 . 10
# Har octet ki range:
0 – 255
# Example-:
192.168.1.10 ✅
192.168.300.10 ❌

# 2.IPv6-:
IPv6 is a 128-bit addressing system designed to provide a much larger address space than IPv4.

[*] IPv6 ek 128-bit addressing system hai jo IPv4 ke comparison mein bahut zyada IP addresses provide karta hai.
# Example-:
2001:0db8:85a3::8a2e:0370:7334

# TYPES OF IP ADDRESS #
# 1.Public IP Address-: 
A public IP address is a globally routable IP address used for communication over the Internet.

[*] Public IP ek aisa IP address hai jo Internet par communication ke liye use hota hai aur globally routable hota hai.
# EXAMPLE-:
INTERNET -->PUBLIC IP-->ROUTER

# 2.Private IP Address-:
A private IP address is used to identify devices within a private network and is not directly routable over the public Internet.

[*] Private IP local/private network ke andar devices ko identify karne ke liye use hota hai.
# Common Private IPv4 Ranges-:
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
# EXAMPLE-:
Router → 192.168.1.1 

PC     → 192.168.1.10

Laptop → 192.168.1.11

Phone  → 192.168.1.12

# 3.Static IP Address-:
A static IP address is an IP address that remains fixed unless it is manually changed or reconfigured.

[*] Static IP ek fixed IP address hota hai jo normally automatically change nahi hota.
# EXAMPLE-:
SERVER,WEBHOSTING,CCTV CAMERA,NETWORK PRINTER, FILE SERVER.

# 4.Dynamic IP Address-:
A dynamic IP address is automatically assigned to a device, typically by a DHCP server, and may change over time.

[*] Dynamic IP automatically assign hota hai, usually DHCP server ke through, aur future mein change ho sakta hai.
 # EXAMPLE-:
 LAPTOP---->DHCP---->IP
# 5.Source IP-:
Source IP identifies the device sending the packet.

[*] Source IP → Data bhejne wale device ka IP
# EXAMPLE-:
Source IP:      192.168.1.10

# 6.DESTINATION IP-:
Destination IP identifies the device that should receive the packet.

[*] Destination IP → Data receive karne wale device ka IP
# EXAMPLE-:
Destination IP: 192.168.1.20

# IP Address in Cybersecurity
IP addresses are important in cybersecurity for:

1.Network monitoring

2.Firewall analysis

3.Log analysis

4.Incident investigation

5.Threat detection

6.Traffic analysis

[*] Cybersecurity mein IP addresses ka use hota hai:

1.Network monitoring ke liye

2.Firewall logs analyze karne ke liye

3.Security logs investigate karne ke liye

4.Suspicious traffic identify karne ke liye

5.Incident investigation ke liye

6.Threat detection ke liye

# SOC EXAMPLE-:
Source IP:      185.x.x.x

Destination IP: 10.0.0.20

Port:           22

Protocol:       TCP

# SOC Analyst investigate kar sakta hai:

1.Source IP kiski hai?

2.Destination server kaunsa hai?

3.Kaunsa port target hua?

4.Connection allowed tha ya blocked?

5.Kya baar-baar connection attempts ho rahe hain?




