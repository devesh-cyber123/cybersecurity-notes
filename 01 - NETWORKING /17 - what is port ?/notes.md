# what is port ?
A port is a logical communication endpoint used by a computer to identify and manage network services and applications.

[*] Port ek logical number hota hai jo computer ke andar different network services/applications ko identify karta hai.

IP address batata hai kaunsa computer/device, aur port batata hai us device par kaunsi service/application se communication karni hai.

# example -:
Maan lo:

IP Address: 192.168.1.10

Port: 22

Iska matlab roughly:

192.168.1.10  → kaunsa device?

Port 22       → SSH service

## 🔐 Important Ports for Cybersecurity

| Port & Protocol / Service & Common Use |
|---|
| **20/21 – FTP – File Transfer** |
| **22 – SSH – Secure Remote Login** |
| **23 – Telnet – Remote Login** |
| **25 – SMTP – Email Sending** |
| **53 – DNS – Domain Name Resolution** |
| **80 – HTTP – Web Traffic** |
| **110 – POP3 – Email Receiving** |
| **143 – IMAP – Email Access** |
| **443 – HTTPS – Secure Web Traffic** |
| **445 – SMB – Windows File/Printer Sharing** |
| **3306 – MySQL – Database** |
| **3389 – RDP – Windows Remote Desktop** |
# Example-:

Agar tum browser mein:

https://example.com

open karte ho, generally HTTPS communication TCP port 443 par hoti hai.

🔥 Open, Closed aur Filtered Port

# Cybersecurity mein ye concepts bahut important hain.

# 1. Open Port

Agar kisi port par service listen kar rahi hai:

Port 22 → OPEN

SSH     → Listening

Matlab device SSH connections accept kar sakta hai.

# 2. Closed Port

Port reachable hai, lekin us port par koi service listening nahi kar rahi.

Port 22 → CLOSED

  # 3. Filtered Port

Firewall/security device traffic ko block ya filter kar raha hai.

Attacker → Firewall → ❌ Port 22

Isliye scanner clearly determine nahi kar pata ki port open hai ya closed.

# Cybersecurity mein Port ka importance

SOC Analyst ke liye ports important hain kyunki network traffic ko understand karne ke liye IP + Port + Protocol ko dekhna padta hai.

Example:

Source IP       Destination IP

192.168.1.20 →  10.0.0.5


Source Port     Destination Port

51543       →   443


Protocol: TCP

# SOC analyst dekh sakta hai:

Kis machine ne connection banaya?

Kis machine se connection hua?

Kaunsa port use hua?

TCP ya UDP?

Kaunsi service involved ho sakti hai?
Connection normal hai ya suspicious?
🔍 Nmap mein Ports
