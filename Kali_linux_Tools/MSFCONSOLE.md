

OFFsec: all metasploit payload and intro
https://www.offsec.com/metasploit-unleashed/msfcli/


## 📦 **8. List All Modules (brute-force method)**

**8. List All Modules (brute-force method)**
```
show auxiliary
show payloads
show exploits
show encoders
show nops
```


Search for Exploits by Service or Port:
```
search port:445
search name:samba
search name:apache
```

Search by OS / Platform:
```
search platform:linux
search platform:windows
search platform:android
search platform:osx
```

Specific category:
```
search auxiliary/scanner/smb
```

General auxiliary modules:
```
search type:auxiliary
```

Search Syntax Format:
```
search auxiliary:ftp
search payload:windows
search os:android
```


Search version or login something:
```
search type:auxiliary name:version
```

