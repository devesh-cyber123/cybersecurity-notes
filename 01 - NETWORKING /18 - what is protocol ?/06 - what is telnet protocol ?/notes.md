# what is telnet protocol ?
Telnet (Teletype Network) is an application-layer protocol used to remotely access and manage another computer/device over a network.

[*] Telnet ek remote access protocol hai jiske through hum network par kisi doosre computer/server/device ke command-line interface ko remotely access kar sakte hain.

👉 Telnet generally TCP port 23 use karta hai.

# example-:
maan lo :

Your PC

   |
   
   |  Telnet
   
   ↓
   
Remote Server

   |
   
   └── Command Line

Aap apne PC se remote server par connect karte ho aur commands execute kar sakte ho.

# example: 

</bash>

telnet 192.168.1.10 23

# Yahan:

192.168.1.10 → Remote device ka IP

23 → Telnet ka default port

# cybersecurity mein Telnet dangerous kyun hai?

Sabse important point:

Telnet data ko plaintext mein transmit karta hai.

# Matlab agar aap:

Username: admin

Password: ********

send karte ho, to communication properly encrypted nahi hoti.

# Conceptually:

Client

   |
   
   | Username + Password
   
   |  ---> Plaintext
   
   |
   
   ↓
   
Network

   |
   
   ↓
   
Server

Agar attacker network traffic capture kar raha ho, to sensitive information expose ho sakti hai.

# SOC Analyst ke liye Telnet important kyun hai?

SOC Analyst ko network logs aur alerts analyse karte waqt Telnet traffic mil sakta hai.

# Example:

Source IP       Destination IP       Port

192.168.1.20    192.168.1.50         23

# SOC analyst notice karega:

Internal system is communicating over TCP port 23.

Phir investigate kiya ja sakta hai:

Kya Telnet intentionally enabled hai?

Kya ye legacy device hai?

Kya unauthorized remote access attempt hai?

Kis IP ne connection establish kiya?

Kitni baar connection attempt hua?

Kya login failures ho rahe hain?

Kya unusual external IP se Telnet connection aa raha hai?

