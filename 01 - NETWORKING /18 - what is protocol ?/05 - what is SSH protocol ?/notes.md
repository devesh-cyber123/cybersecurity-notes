# what is ssh protocol ?
SSH (Secure Shell) is a cryptographic network protocol used to securely access and manage remote systems over an untrusted network.

[*] SSH ek secure network protocol hai jo kisi remote computer/server ko securely access aur manage karne ke liye use hota hai.

# Simple example:

Your PC

   │
   
   │ 🔒 SSH
   
   │ TCP 22
   
   ↓
   
Remote Linux Server

Aap apne PC se kisi remote Linux server par securely login karke commands execute kar sakte ho.

# 2. SSH ka default port

SSH normally:

TCP Port 22

use karta hai.

SSH

 ↓
 
TCP

 ↓
 
Port 22

⚠️ Lekin port 22 = automatically SSH nahi hota. Administrators SSH ko kisi different port par bhi configure kar sakte hain.

# 3. SSH ki zarurat kyun padi?

Purane time mein Telnet remote login ke liye use hota tha.

# Problem:

Telnet ❌

Username

Password

Commands

   ↓
   
Plaintext communication

# SSH:

SSH ✅

Username

Password

Commands

   ↓
   
🔒 Encrypted connection

   ↓
   
Server

Isliye SSH remote administration ke liye much safer approach provide karta hai.

# 4. SSH kaise kaam karta hai?

Maan lo tumhare paas:

Your PC

IP: 192.168.1.20

Aur remote server:

Server

IP: 192.168.1.100

# Tum command chalate ho:

ssh username@192.168.1.100

# Flow:

Your PC

   │
   
   │ 1. SSH Request
   
   ↓
   
Server:22

   │
   
   │ 2. Secure session setup
   
   ↓
   
Authentication

   │
   
   ↓
   
Access Granted

   │
   
   ↓
   
Remote Shell

Ab tum remote server par commands execute kar sakte ho.

# 5. SSH ke important security features

SSH ka cybersecurity mein importance mainly in security properties ki wajah se hai.

# 🔐 1. Encryption

SSH communication ko encrypt karta hai.

Client

  │
  
  │ 🔒 Encrypted
  
  ↓
  
Internet

  │
  
  │ 🔒 Encrypted
  
  ↓
  
Server

Isse network par communication ko directly read karna difficult hota hai.

#  2. Authentication

SSH verify karta hai ki user authorized hai ya nahi.

# Common methods:

Password authentication

SSH public/private key authentication

# 🛡️ 3. Integrity

SSH communication mein cryptographic protections use karta hai taaki data ko transit mein secretly modify karna difficult ho.

# 🖥️ 4. Secure Remote Administration

Administrator remotely server manage kar sakta hai.

# Example:

Admin PC

   ↓
   
  SSH
  
   ↓
   
Linux Server

# Phir admin:

ls

cd

pwd

systemctl status

journalctl

jaise commands execute kar sakta hai.

# 6. SSH Key Authentication 🔑

Cybersecurity mein ye bahut important concept hai.

SSH key authentication mein generally key pair hota hai:

Public Key
     +
Private Key

Public Key

Server par store ki ja sakti hai.

Private Key

Client/user ke paas securely rakhi jati hai.

Client                         Server

Private Key 🔑              Public Key 🔑

     │                           │
     
     └────── SSH Authentication ─┘
     
                  ↓
                  
             Access Granted
# ⚠️ Important

Private key ko kisi ke saath share nahi karna chahiye.

# 7. SSH aur SFTP ka relation

Ye tumhare previous topic se directly connected hai.

                 SSH
                 
                  │
                  
        ┌─────────┴─────────┐
        
        ↓                   ↓
        
   Remote Shell           SFTP
   
        │                   │
        
   Commands             File Transfer
   
# SSH

Remote system ko securely access/manage karne ke liye.

# SFTP

Files securely transfer karne ke liye.

# 8. SSH ke practical examples

Remote server login

ssh user@192.168.1.100

Specific port

Agar SSH port 22 ke instead kisi aur port par configured ho:

ssh -p 2222 user@192.168.1.100

SFTP

sftp user@192.168.1.100

# 9. Cybersecurity / SOC Analyst mein SSH

SOC Analyst ke liye SSH traffic important hai because attackers bhi compromised systems ko remotely control karne ke liye SSH credentials/keys ka misuse kar sakte hain.

SOC analyst ko monitor karna pad sakta hai:

SSH Activity

     ↓
     
Source IP

     ↓
     
Destination IP

     ↓
     
Destination Port

     ↓
     
Login Attempts

     ↓
     
Success / Failure

     ↓
     
User Account

     ↓
     
Time of Activity

     ↓
     
Commands / Server Logs

# 10. SSH Brute-Force Attempt

# Example:

Internet

   │
   
   ├── Login attempt 1
   
   ├── Login attempt 2
   
   ├── Login attempt 3
   
   ├── Login attempt 4
   
   ├── Login attempt 5
   
   └── ...
   
          ↓
          
      SSH Server
      

Agar ek IP repeatedly different passwords ke saath login try kar raha hai, to possible brute-force activity ho sakti hai.

SOC Analyst ko logs mein multiple failed SSH authentication attempts dikh sakte hain.

# 11. SSH ke security risks

SSH secure protocol hai, lekin SSH server automatically secure nahi ho jata. Configuration important hai.

# Common risks:

🔴 Weak passwords

Weak Password

     ↓
     
Brute Force Risk

🔴 Stolen SSH private key

Private Key Compromised

        ↓
        
Unauthorized SSH Access

🔴 Exposed SSH service

Internet-facing SSH service ko properly secure aur monitor karna important hai.

🔴 Excessive privileges

Agar compromised account ke paas unnecessary administrative privileges hain, to impact badh sakta hai.

# 12. SOC mein SSH logs

Linux systems mein SSH authentication activity commonly logs/journals mein record hoti hai.

# Example:

Failed password for user

Accepted password for user

Accepted publickey for user

# Invalid user

SOC Analyst in events ko investigate kar sakta hai.

# Example:
10:30 → Failed SSH login

10:31 → Failed SSH login

10:31 → Failed SSH login
10:32 → Successful login

⚠️ Ye pattern suspicious ho sakta hai, aur analyst ko source IP, account, timing aur context investigate karna chahiye.
