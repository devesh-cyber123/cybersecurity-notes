# what is gateway ?
A Gateway is a network device or node that connects one network to another network 
and acts as an entry and exit point for network traffic.

[*] Gateway ek aisa device/node hota hai jo ek network ko doosre network se connect karta hai.
Ye network ke traffic ke liye entry point aur exit point ki tarah kaam karta hai.

# Simple Example

Maan lo tumhare ghar mein:

          INTERNET
          
             │
             
             │

        [ Wi-Fi Router ]
        
        Gateway: 192.168.1.1
        
             │
             
       ┌─────┴─────┐
   
       │           │
     Laptop      Mobile
     
192.168.1.10  192.168.1.20

# Tumhare laptop ka IP hai:

192.168.1.10

# Aur router ka LAN IP:

192.168.1.1

To laptop ka Default Gateway = 192.168.1.1 ho sakta hai.

Jab laptop ko apne local network ke bahar kisi destination se communicate karna hota hai, traffic gateway/router ki taraf bheja jata hai.

# 🧠 Default Gateway kya hota hai?

Default Gateway woh IP address hota hai jahan device un packets ko bhejta hai jinka destination local network ke bahar hota hai.

# Example:

Laptop

IP:       192.168.1.10

Subnet:   255.255.255.0

Gateway:  192.168.1.1

# Agar laptop communicate kar raha hai:

192.168.1.20

to ye same local network mein hai.

Lekin agar destination hai:

8.8.8.8

to packet local network ke bahar hai.

Laptop generally packet ko default gateway 192.168.1.1 ko forward karega.

# 🔐 Cybersecurity mein Gateway ka importance

SOC Analyst ke liye gateway important hai kyunki network traffic ko understand karte waqt humein pata hona chahiye:

Traffic kahan se aa raha hai → kahan ja raha hai → kis gateway/router se pass ho raha hai.

# Example:

Internal PC

10.0.0.25
     │
     
     ▼
     
Gateway / Router

10.0.0.1

     │
     ▼
Internet

# Agar SOC Analyst logs mein dekhta hai:

10.0.0.25 → 185.x.x.x

to gateway/router/firewall logs se additional information mil sakti hai.

# 🎯 SOC Analyst ko Gateway mein kya yaad rakhna chahiye?

Tumhare liye ye 6 points important hain:

Gateway networks ko connect karta hai.

Default Gateway local network se bahar traffic ka next hop hota hai.

Home networks mein router commonly default gateway hota hai.

Gateway IP ko ipconfig / ip route se identify kar sakte ho.
Network investigation mein gateway/router/firewall logs useful hote hain.
Gateway ko firewall ke saath confuse nahi karna—firewall ka primary role traffic filtering/security enforcement hai.
Interview answer
