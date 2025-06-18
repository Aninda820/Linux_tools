 
```
  nmap -p 139,445 --script smb-enum-shares <target_ip>
  nmap -p 139,445 --script smb-enum-users <target_ip>


command for smbclient:-
smbclient //<ip>/user

Ex: smnt bclie//10.10.203.63/Anonymous 
```

For download anything from the server we will use (get) command...
Ex: get file.txt

### **Mount an SMB Share Locally (Alternative)**

Instead of using `smbclient`, you can **mount the SMB share** like a normal folder:

```
`sudo mount -t cifs //10.10.11.16/Shared /mnt/smb -o username=user,password=pass`
```

✅ **Use Case**: Allows you to access SMB files **like a normal directory** (`/mnt/smb`).


### **How to Access a Shared Folder?**

If you find an interesting share (e.g., `Anonymous`), you can connect to it like this:

`smbclient \\\\10.10.11.16\\Anonymous -N`


---

### **1. List Available SMB Shares (No Authentication)**

```
smbclient -N -L //10.10.11.16/
```


✅ **Use Case**: Lists all shared folders on the SMB server **without requiring credentials** (`-N` for anonymous login).

---

### **2. Connect to an SMB Share (Anonymous Login)**

```
smbclient //10.10.11.16/Anonymous -N
```

✅ **Use Case**: Connects to the `Anonymous` share if it allows guest access.

---

### **3. Connect to an SMB Share with Username & Password**

```
smbclient //10.10.11.16/Shared -U username
```

It will prompt you for the **password**.

🔹 **Example with password included (not secure but useful for automation)**:

bash

CopyEdit

`smbclient //10.10.11.16/Shared -U username%password`

---

### **4. Browse and Download Files After Connecting**

Once connected, you'll enter an **interactive SMB shell**. You can use:
```
ls             # List files in the share
get file.txt    # Download a file 
put file.txt     # Upload a file 
exit        # Quit smbclient
```



```
smbclient -L //10.10.11.16/ -N  # List shares
smbmap -H 10.10.11.16 -u anonymous  # Check share permissions
```

