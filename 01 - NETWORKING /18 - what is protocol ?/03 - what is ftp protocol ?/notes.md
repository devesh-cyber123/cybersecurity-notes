# what is ftp protocol ?
FTP (File Transfer Protocol) is a network protocol used to transfer files between a client and a server over a network.

[*] FTP ek network protocol hai jiska use client aur server ke beech files upload aur download karne ke liye hota hai.

# example-:

Your PC (FTP Client)

        |
        
        |  FTP
        
        ↓
        
     FTP Server
        |
        
        └── files
        
            ├── report.pdf
            
            ├── image.jpg
            
            └── data.txt
            
# 2. FTP kis layer par kaam karta hai?

FTP Application Layer ka protocol hai. 

OSI Model

│

├── Application       ← FTP

├── Presentation

├── Session

├── Transport         ← TCP

├── Network

├── Data Link

└── Physical

# 3. FTP ke important ports

FTP mein mainly 2 TCP connections use hote hain:

Connection	Port	Purpose

Control Connection	TCP 21	Commands/control

Data Connection	TCP 20	Data/file transfer

TCP 21 — Control

# Client server ko commands bhejta hai:

USER

PASS

LIST

RETR

STOR

QUIT

TCP 20 — Data

Actual file/data transfer ke liye traditionally TCP 20 use hota hai, especially active FTP mein.

# Important: FTP ke active/passive modes mein data connection ka port behavior different hota hai. Passive FTP mein server ek dynamically selected port provide karta hai.

# 4. FTP kaise kaam karta hai?

# Example:

Aapko server se report.pdf download karni hai.

# 1. Client → Server

   TCP connection → Port 21


# 2. Login

   USER username
   
   PASS password


# 3. Client → Server

   "Mujhe report.pdf chahiye"


# 4. Server → Client

   Data connection establish


# 5. report.pdf

   Server → Client


# 6. Transfer complete

# 5. FTP mein problem kya hai? 🔴

Cybersecurity ke liye sabse important point:

FTP by default encrypted nahi hota.

FTP username aur password ko plaintext mein transmit kar sakta hai.

# Example:

Username: admin

Password: MyPassword123

Network par attacker traffic capture kare aur credentials exposed hon, to account compromise ho sakta hai.
