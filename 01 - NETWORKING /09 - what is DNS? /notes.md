# what is DNS?
DNS (Domain Name System) is a system that translates human-readable domain names into
IP addresses so that computers can locate and communicate with the correct server.

[*] DNS ek system hai jo website ke human-readable domain name ko IP Address mein convert karta hai, 
taaki computer/server ko pata chal sake ki request kahan bhejni hai.

# EXAMPLE-:

Hum browser mein likhte hain:

www.google.com

Computer ko directly domain name se server locate nahi karna hota; DNS resolution ke through domain ka IP address obtain hota hai.

# DNS ki zarurat kyu padti hai-:
Sabse pehle ye samjho:

Computer websites ko IP Address se locate karta hai.

Website Name:

google.com

IP Address:

142.250.xxx.xxx

# Ab socho agar har website ka IP yaad rakhna pade:

google.com       → 142.xxx.xxx.xxx

facebook.com     → 157.xxx.xxx.xxx

amazon.com       → 18.xxx.xxx.xxx

Bahut difficult hoga. 

Isliye DNS bana.

# Hum simply likhte hain:

google.com

# DNS us domain ko resolve karke corresponding IP address provide karta hai.

google.com

     ↓
     
    DNS
    
     ↓
     
IP Address

     ↓
     
Google Server

# Easy example

DNS = Internet ka Phonebook

Phonebook:

Rahul → 9876543210

DNS:

google.com → IP Address

# DNS ka actual kaam kya hai-:

DNS ka main kaam hai:

Domain Name Resolution

Yaani:

Domain Name

     ↓
     
    DNS
    
     ↓
     
 IP Address

# Example-:

www.example.com

       ↓
       
      DNS
     
       ↓
       
 93.184.xxx.xxx

Ab computer ko server ka address mil gaya.

# 4. Jab tum website open karte ho to kya hota hai?

Maan lo tum browser mein likhte ho:

www.example.com

Step 1 — Browser domain dekhta hai

www.example.com

Step 2 — DNS resolution hoti hai

Computer DNS resolver se poochta hai:

"www.example.com ka IP Address kya hai?"

Step 3 — DNS IP return karta hai

# Example:

www.example.com

        ↓
        
  93.184.xxx.xxx

Step 4 — Computer server se connect karta hai 

Your Computer

      ↓
      
93.184.xxx.xxx

      ↓
      
  Web Server
  
      ↓
      
   Website
   
# 5. Complete DNS Flow

Is flow ko SOC Analyst L1 ke liye yaad karna bahut important hai:

                 USER
                 
                   ↓
                   
              Web Browser
              
                   ↓
                   
            www.example.com
          
                   ↓
                   
              DNS Resolver
             
                   ↓
                   
               DNS Server
             
                   ↓
                   
               IP Address
               
                   ↓
                
              Web Server
              
                   ↓
                   
                 Website
                 
# 6. DNS mein "Resolver" kya hota hai?

Ye point important hai.

DNS Resolver wo service/component hai jo DNS query ko process karke domain ka IP address find karne mein help karta hai.

Simple:

Computer:

"example.com ka IP batao"

       ↓

DNS Resolver:

"Main iska IP find karta hoon."

       ↓

DNS Response:

"Ye raha IP."

# 7. DNS Query kya hoti hai?

Jab computer DNS se kisi domain ke baare mein information maangta hai, us request ko DNS Query kehte hain.

# Example:

Computer

   ↓
   
DNS Query:

# "What is the IP address of example.com?"

DNS response:

DNS Response:

"example.com = 93.184.xxx.xxx"

Simple:

Query = Question

Response = Answer

# 8. SOC Analyst ke liye DNS yahan se important hota hai -:

Ab networking se cybersecurity par aate hain.

SOC Analyst network mein hone wali activity monitor karta hai.

DNS requests bhi network activity ka part hain.

Example:

Employee PC

     ↓
     
DNS Query

     ↓
     
google.com

Ye normal ho sakta hai.

# Lekin:

Employee PC

     ↓
     
DNS Query

     ↓
     
random-suspicious-domain.xyz

# Ab SOC Analyst bolega:

"Ye domain kya hai?"

Yahin se investigation start hoti hai.

# 9. SOC Analyst DNS mein kya check karta hai?

Agar suspicious DNS alert aaye, L1 Analyst generally ye cheezein dekhta hai:

① Source IP

Kis computer ne DNS request bheji?

Source IP:

192.168.1.25

② Domain

Kis domain ko request ki gayi?

Domain:

suspicious-example.com

③ Time

Request kab hui?

Time:

10:25:31

④ Frequency

Ek baar request hui ya hundreds of times?

10:25 → request

10:26 → request

10:27 → request

10:28 → request

Repeated unusual requests suspicious ho sakti hain.

⑤ Resolved IP

# Domain kis IP address par resolve ho raha hai?

Domain

   ↓
   
IP Address

⑥ User/Host

Kaunsa user ya machine involved hai?

# 10. DNS aur Malware-:

Maan lo kisi employee ke computer mein malware aa gaya.

Malware attacker ke server se communication karna chahta hai.

# Conceptually:

Infected PC

    ↓
    
DNS Query

    ↓
    
attacker-domain.com

    ↓
    
Malicious IP

    ↓
    
Attacker Server

# SOC Analyst DNS logs mein suspicious domain dekh sakta hai.

Phir wo check karega:

Domain

 ↓
 
IP

 ↓
 
Endpoint

 ↓
 
Process

 ↓
 
Other Security Logs

Isliye DNS logs SOC investigation ke liye valuable evidence/source of telemetry ho sakte hain.

# 11. DNS aur Phishing-:

Maan lo employee ko phishing email aayi:

"Your account is locked.

# Click here to verify."

Employee link par click karta hai:

Employee

   ↓
   
Phishing Website

   ↓
   
DNS Query

   ↓

Suspicious Domain

   ↓
   
IP Address

SOC Analyst DNS logs check karke dekh sakta hai ki user ne suspicious domain access kiya ya nahi.

# 12. DNS Tunneling-:

Ye SOC L1 ke liye important concept hai.

DNS Tunneling mein attacker DNS traffic ka misuse karke information ya command-and-control communication carry karne ki koshish kar sakta hai.

# Normal DNS:

Computer

   ↓
   
example.com

   ↓
   
DNS Response

# Suspicious pattern:

Computer

   ↓
   
very-long-random-data.example.com

   ↓
   
DNS Server

# Agar repeatedly unusual/long/random-looking DNS queries generate ho rahi hain, SOC Analyst investigate kar sakta hai.

⚠️ Har long/random domain malicious nahi hota — context aur additional logs check karna zaroori hai.

# 13. DNS Record Types — SOC L1 ko kitna pata hona chahiye?

Basic level par ye records yaad rakho:

Record	Kaam

A	Domain → IPv4 Address

AAAA	Domain → IPv6 Address

CNAME	Domain ko another domain name par point karta hai

MX	Mail server identify karta hai

NS	DNS name server identify karta hai

TXT	Text/configuration information

PTR	IP → Domain Name

# Sabse important:
A     → IPv4

AAAA  → IPv6

MX    → Mail

CNAME → Another Name

PTR   → Reverse DNS

14. DNS aur IP Address ka relation

Ye bahut important hai:

IP Address

Device/server ko network par address karta hai.

DNS

# Domain name ko IP address se resolve karne mein help karta hai.

# Example:

google.com

     ↓
     
    DNS
    
     ↓
     
IP Address

     ↓
     
  Server

# So:

DNS khud IP Address nahi hai. DNS ek naming/resolution system hai.

# 15. SOC Analyst L1 ka Realistic Example

Suppose SIEM mein alert aaya:

🚨 ALERT

Suspicious DNS Query

Source IP:

192.168.1.25

Domain:

abc-random-example.xyz

Time:

10:30:45

# SOC Analyst kya karega?

Alert

  ↓
  
Source IP identify

  ↓
  
Host/User identify

  ↓
  
Domain investigate

  ↓
  
DNS history check

  ↓
  
Resolved IP check

  ↓
  
Endpoint logs check

  ↓
  
Other alerts correlate

  ↓
  
Legitimate / Suspicious / Malicious

  ↓
  
Escalate if required


# Important: L1 Analyst sirf domain dekhkar "malware" declare nahi karega. Evidence correlate karega.

