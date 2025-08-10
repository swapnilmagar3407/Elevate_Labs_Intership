# Firewall Configuration on Kali Linux (UFW)

## bjective
Configure and test basic firewall rules to allow or block traffic in Kali Linux using UFW (Uncomplicated Firewall).

## Tools Used
- Kali Linux
- UFW (Uncomplicated Firewall)

---

## Steps

### 1️⃣ Install and Enable UFW
```bash
sudo apt update
sudo apt install ufw -y
sudo ufw enable
```

### 2️⃣ View Current Rules
```bash
sudo ufw status numbered
```

### 3️⃣ Block Inbound Traffic on Port 23 (Telnet)
```bash
sudo ufw deny 23
```

### 4️⃣ Test the Rule
```bash
telnet 127.0.0.1 23
```
Expected: **Connection refused**

### 5️⃣ Allow SSH (Port 22)
```bash
sudo ufw allow 22
```

### 6️⃣ Remove the Test Block Rule
```bash
sudo ufw status numbered
sudo ufw delete <rule_number>
```

### 7️⃣ Final Status
```bash
sudo ufw status numbered
```

---

## 📸 Screenshots
1. UFW enabled
2. Current rules
3. Rule added to block port 23
4. Telnet test failed
5. SSH allowed
6. Rule removed
7. Final configuration

---

##Summary
UFW was used to configure firewall rules in Kali Linux. Port 23 was blocked to deny Telnet access, and Port 22 was allowed for SSH. Rules were tested and removed as required.

---

##Outcome
- Learned to manage firewall rules using UFW.
- Verified blocking and allowing specific ports.
