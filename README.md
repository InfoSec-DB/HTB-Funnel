# Funnel Exploit - HTB

## Description

This is an **automated Python exploit** for the Hack The Box machine **"Funnel"**.  
It performs:
- **FTP Enumeration & File Extraction**
- **Username Extraction from Emails**
- **SSH Password Spraying**
- **Port Forwarding via SSH Tunneling**
- **PostgreSQL Exploitation & Flag Extraction**

---

## **Usage**

### 1️⃣ Install Dependencies

Ensure you have the required packages installed:

```bash
pip install paramiko psycopg2 nmap
```

### 2️⃣ Run the Exploit

```bash
python3 funnel_exploit.py
```

---

## **Exploit Details**

1. **Enumerates FTP (Anonymous Access)**
2. **Extracts Usernames & Default Password**
3. **Attempts SSH Login via Password Spraying**
4. **Sets Up SSH Tunnel to Access PostgreSQL**
5. **Queries PostgreSQL for Flag**

---

## **Sample Output**

```bash
$ python3 funnel_exploit.py

▗▄▄▖                ▝▜  ▗▄▄                                                                                                                                                                                                                                                                       
▐   ▗ ▗ ▗▗▖ ▗▗▖  ▄▖  ▐  ▐ ▝▌▖  ▖▗▗▖                                                                                                                                                                                                                                                               
▐▄▄▖▐ ▐ ▐▘▐ ▐▘▐ ▐▘▐  ▐  ▐▄▟▘▚▗▗▘▐▘▐                                                                                                                                                                                                                                                               
▐   ▐ ▐ ▐ ▐ ▐ ▐ ▐▀▀  ▐  ▐   ▐▟▟ ▐ ▐                                                                                                                                                                                                                                                               
▐   ▝▄▜ ▐ ▐ ▐ ▐ ▝▙▞  ▝▄ ▐    ▌▌ ▐ ▐                                                                                                                                                                                                                                                               
                                     

[+] Running Nmap Scan...
[+] Open Ports: [21, 22]

[+] Checking FTP anonymous access...
[+] Downloading welcome_28112022
[+] Downloading password_policy.pdf
[+] FTP files retrieved.

[+] Extracting usernames...
[+] Users found: ['christine', 'albert', 'maria']

[+] Testing SSH logins...
[+] SSH login successful for christine.

[+] Establishing SSH connection...
[+] SSH Connected.

[+] Setting SSH Tunnel...
[+] SSH Tunnel established.

[+] Querying PostgreSQL...
📌 [FLAG] cf277664b1771217d7006acdea006db1

[+] Cleanup complete.
```

---

## **Legal Disclaimer**

> This tool is for **educational purposes only**.  
> Unauthorized use against live systems is strictly prohibited.

---
