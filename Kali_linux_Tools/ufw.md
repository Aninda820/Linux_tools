
```
sudo apt update && sudo apt install ufw

sudo systemctl start ufw
sudo ufw enable
sudo systemctl status ufw
```


### **Basic UFW Commands**

✅ **Enable UFW** (activate firewall):
```
sudo ufw enable
```

✅ **Disable UFW** (turn off firewall):
```
sudo ufw disable
```

✅ **Check UFW Status** (list rules and status):
```
sudo ufw status
```

✅ **Check detailed UFW status**:
```
sudo ufw status verbose
```

✅ **Reset UFW to default settings**:
```
sudo ufw reset
```

✅ **Reset UFW to default settings**:
```
sudo ufw reset
```

### **Allow & Deny Traffic**

🚀 **Allow incoming traffic on a specific port (e.g., SSH on port 22):**
```
sudo ufw allow 22
```

🚀 **Allow a specific service (e.g., OpenSSH):**
```
sudo ufw allow OpenSSH
```

🚀 **Allow a port with a specific protocol (TCP or UDP):**
```
sudo ufw allow 443/tcp
```

🚀 **Allow a port range (e.g., 5000-5500):**
```
sudo ufw allow 5000:5500/tcp
```

🚀 **Allow traffic from a specific IP (e.g., allow only 192.168.1.100 to access SSH):**
```
sudo ufw allow from 192.168.1.100 to any port 22
```

🚀 **Allow traffic from a specific subnet:**
```
sudo ufw allow from 192.168.1.0/24
```

🚀 **Deny incoming traffic on a port (e.g., block SSH):**
```
sudo ufw deny 22
```

🚀 **Deny traffic from a specific IP:**
```
sudo ufw deny from 203.0.113.5
```

🚀 **Deny traffic from a subnet:**
```
sudo ufw deny from 203.0.113.0/24
```


### **Advanced UFW Rules**

🔥 **Allow outgoing traffic (default is to allow all, but you can control it):**
```
sudo ufw default allow outgoing
```

🔥 **Deny outgoing traffic (e.g., block all outbound connections except allowed ones):**
```
sudo ufw default deny outgoing
```

🔥 **Allow a specific outgoing connection (e.g., allow HTTP/HTTPS out):**
```
sudo ufw allow out 80/tcp
sudo ufw allow out 443/tcp
```

🔥 **Rate limit connections (prevent brute force attacks, e.g., SSH on port 22):**
```
sudo ufw limit 22/tcp
```

🔥 **Allow all traffic for a specific interface (e.g., allow eth0):**
```
sudo ufw allow in on eth0
```

🔥 **Deny all incoming traffic and allow only specific rules:**
```
sudo ufw default deny incoming
```

### **Deleting UFW Rules**

❌ **Delete a specific rule (e.g., remove SSH allow rule):**
```
sudo ufw delete allow 22
```

❌ **Delete rule by rule number (first check with `sudo ufw status numbered`):**
```
sudo ufw delete 3
```

❌ **Disable logging:**
```
sudo ufw logging off
```


### **Logging & Monitoring**

🔍 **Enable UFW logging:**
```
sudo ufw logging on/off
```

🔍 **Check UFW logs in real time:**
```
sudo tail -f /var/log/ufw.log
```

🔍 **List all active rules:**
```
sudo ufw show added
```