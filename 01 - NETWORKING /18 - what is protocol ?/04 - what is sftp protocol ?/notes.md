# what is sftp protocol ?
SFTP (SSH File Transfer Protocol) is a secure protocol used to transfer files between a client and a server over an encrypted SSH connection.

[*] SFTP ek secure file transfer protocol hai jo client aur server ke beech files ko securely upload aur download karne ke liye use hota hai.

# example-:

Your PC

  │
  
  │  SFTP
  
  │  Encrypted Connection
  
  ↓
  
SFTP Server

  │
  
  ├── report.pdf
  
  ├── logs.txt
  
  └── backup.zip

  # 2. SFTP kis protocol par based hai?

Sabse important point:

SFTP SSH protocol ke through operate karta hai.

Isliye iska default port:

TCP Port 22

# Flow:

SFTP

  ↓
  
 SSH
 
  ↓
  
 TCP
 
  ↓
  
  Ip
  
# Yaad rakho:

Protocol	Default Port	Encryption

FTP	TCP 21	❌ No

FTPS	TCP 21/990	✅ TLS

SFTP	TCP 22	✅ SSH

# 3. SFTP kaise kaam karta hai?

Suppose tumhe server par report.pdf upload karni hai.

# Step 1 — SSH connection

Client → Server

       TCP 22
       
# Step 2 — Authentication

Server user ko authenticate karta hai.

# Authentication methods:

Username + Password

SSH Key

Public/Private Key Authentication

# Step 3 — Secure session

Authentication ke baad encrypted SSH session establish hota hai.

Client

  │
  
  │ 🔒 Encrypted SSH Session
  
  ↓
  
Server

# Step 4 — File transfer

Ab file securely transfer hoti hai:

report.pdf

    ↓
    
🔒 Encrypted

    ↓
    
SFTP Server

# 4. SFTP mein encryption kyun important hai?

Normal FTP mein credentials aur data plaintext mein transmit ho sakte hain.

# Example:

FTP ❌


Username: admin

Password: Password123

       ↓
       
    Network
    
       ↓
       
Potentially readable

# SFTP mein:

SFTP ✅


Username

Password

Files

Commands

   ↓
   
 Encrypted SSH Connection

   ↓
   
Server

Isliye network attacker ke liye traffic ko directly read karna much harder hota hai.

# 5. SFTP ke 3 important security features
# 🔐 1. Confidentiality

Data encrypted hota hai.

File → Encryption → Network → Server

Unauthorized person easily data nahi padh sakta.

# 🛡️ 2. Integrity

Data transmission ke dauran modification detect/protect karne ke mechanisms SSH provide karta hai.

# Matlab:

Original File

     ↓
     
Encrypted Transfer

     ↓
     
   Server

Data ko secretly modify karna difficult hota hai.

# 👤 3. Authentication

Server verify karta hai ki user authorized hai ya nahi.

# Example:

Username + Password

        OR
        
SSH Private Key

        ↓
        
Authentication

        ↓
        
Access Granted

# 6. SFTP mein SSH Key Authentication

Cybersecurity mein ye bahut important hai.

SSH keys ke pair hote hain:

Public Key  → Server par

Private Key → Client ke paas

# Example:

Client

Private Key 🔑

     │
     
     ↓
     
   SSH/SFTP
   
     │
     
     ↓
     
   Server
   
Public Key 🔑

Private key ko secret rakhna bahut important hai.

# 7. SFTP ke common commands

Linux/Kali mein:

sftp username@server-ip

# Example:

sftp analyst@192.168.1.10

# Login ke baad:

ls

Server ki files dekhne ke liye.

pwd

Current remote directory dekhne ke liye.

get report.pdf

Server se file download karne ke liye.

put report.pdf

Server par file upload karne ke liye.

cd /var/log

Remote directory change karne ke liye.

exit

SFTP session close karne ke liye.

# 8. Cybersecurity mein SFTP ka use

SFTP organizations mein sensitive files securely transfer karne ke liye use ho sakta hai.

# Examples:

Company

   │
   
   ├── Backup Files
   
   ├── Log Files
   
   ├── Reports
   
   ├── Configuration Files
   
   └── Data
   
          ↓
          
        SFTP
        
          ↓
          
     Secure Server

SOC environment mein bhi SFTP-related traffic ko monitor kiya ja sakta hai.

# 9. SOC Analyst ke liye SFTP 🔎

SOC Analyst ko SFTP activity investigate karte waqt dekhna ho sakta hai:

① Source IP

Connection kahan se aa raha hai?

10.0.0.25
② Destination IP

Connection kis server par ja raha hai?

10.0.0.50
③ Destination Port
TCP 22

Lekin port 22 ka matlab automatically SFTP nahi hota—SSH par multiple services operate kar sakti hain.

④ Authentication activity

Successful Login

Failed Login

Multiple Failed Login

⑤ File-transfer behavior

Upload
Download
Large File Transfer
Unusual Transfer Time
