# what is http protocol ?
HTTP (HyperText Transfer Protocol) is an application-layer protocol used for communication between a web client (browser) and a web server.

[*] HTTP ek Application Layer protocol hai jo browser/client aur web server ke beech data communicate karne ke liye use hota hai.

# Simple Example

Jab tum browser me:

http://example.com

open karte ho:

Your Browser

     |
     
     | HTTP Request
     
     ↓
     
 Web Server

     |
     
     | HTTP Response
     
     ↓
     
Your Browser

# 2. HTTP kis OSI Layer par hai?

HTTP → Application Layer (Layer 7)

OSI Layer 7 → Application → HTTP / HTTPS / DNS

HTTP normally TCP ke upar kaam karta hai.

HTTP

 ↓
 
TCP

 ↓
 
IP

 ↓
 
Ethernet / Wi-Fi

# HTTP ka commonly associated port:

TCP 80

# HTTPS ka commonly associated port:

TCP 443

# 3. HTTP Request kya hoti hai?

Browser server ko request bhejta hai.

# Example:
GET /index.html HTTP/1.1

Host: example.com

User-Agent: Mozilla/5.0

# Iska matlab:
Iska matlab:

GET → mujhe resource/data chahiye

/index.html → requested resource

Host → kis website/server ko request bhejni hai

User-Agent → client/browser ki information

# 4. HTTP Response

Server request process karke response bhejta hai.

# Example:

HTTP/1.1 200 OK

Content-Type: text/html

Content-Length: 1250

# 5. HTTP Cybersecurity me important kyu hai?

HTTP web applications ka major communication protocol hai, isliye attackers bhi web traffic ko target karte hain.

SOC Analyst HTTP traffic me suspicious activity identify kar sakta hai, jaise:

Client → HTTP Request → Web Server

                  ↓
                  
          Suspicious Request
          
                  ↓
                  
             SOC Alert

# Examples:

SQL Injection attempts

XSS attempts

Directory traversal

Malicious file requests

Brute-force login attempts

Suspicious user agents

Unusual HTTP methods

Large/abnormal requests

Scanning activity
