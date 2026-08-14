# what is firewall ?
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predefined security rules.

[*] Firewall ek security system hai jo network ke andar aur bahar jaane wale traffic ko monitor aur control karta hai.\

# example-:
Socho ek company ka office hai.

Office ke entrance par security guard hai.

                    INTERNET
                       │
                       ▼
                ┌─────────────┐
                │   FIREWALL  │
                │   Security  
                │   Gateway   │
                └──────┬──────┘
                       │
                 ┌─────▼─────┐
                 │  COMPANY  │
                 │  NETWORK  │
                 └───────────┘

# Security guard check karega:

"Kisko andar aane dena hai?"

"Kisko bahar jaane dena hai?"

Exactly isi tarah firewall network traffic ko rules ke according control karta hai.

# Firewall ka main kaam-:

Firewall mainly network traffic filtering karta hai.

Internet

   │
   
   │ Traffic
   
   ▼
Firewall

   │
   
   ├── ✅ Allowed Traffic → Internal Network
   
   │
   
   └── ❌ Blocked Traffic → Dropped/Denied

  # Firewall traffic ko different information ke basis par inspect kar sakta hai:

Source IP

Destination IP

Source Port

Destination Port

Protocol

Connection state

Application/URL, depending on firewall type

# Firewall Cybersecurity mein kyun important hai?

Firewall organization ke network ko unauthorized network access se protect karne mein important role play karta hai.

# Example-:

              INTERNET
                  │
          ┌───────▼───────┐
          │   FIREWALL    │
          │      🛡️       │
          └───────┬───────┘
                  │
        ┌─────────▼─────────┐
        │ Internal Network  │
        │                   │
        │ PC  Server  DB    │
        └───────────────────┘

Firewall unwanted traffic ko block kar sakta hai aur legitimate traffic ko allow kar sakta hai.     

# Firewall ke main types

Cybersecurity/SOC ke liye in types ko samajhna important hai.

# 1. Packet Filtering Firewall

Ye packet ke basic information ko check karta hai:

Source IP

Destination IP

Port

Protocol

# Example:
Source IP: 192.168.1.10

Destination Port: 80

Protocol: TCP

Firewall → Rule check → ALLOW ✅

# 2. Stateful Firewall

Ye sirf individual packet nahi dekhta, balki connection ki state bhi track karta hai.

# Example:

Client ───────► Server

       Connection
       
          │
          ▼
          
      Firewall

Ye determine kar sakta hai ki packet kisi established connection ka part hai ya nahi.

# 3. Proxy Firewall

Proxy firewall client aur destination server ke beech intermediary ki tarah work karta hai.

Client

  │
  
  ▼
Proxy Firewall

  │
  ▼
  
Internet Server
      
      
          │
          
    State Tracking
    
  Firewall unwanted traffic ko block kar sakta hai aur legitimate traffic ko allow kar sakta hai.

#  4. Next-Generation Firewall (NGFW)

Modern enterprise environments mein NGFW kaafi important hai.

Ye traditional firewall rules ke saath additional security capabilities provide kar sakta hai, jaise:

Deep Packet Inspection

Application awareness

User awareness

Intrusion Prevention

Threat intelligence integration

Advanced traffic filtering
