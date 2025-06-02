

1. *==**Install ssh2john:**==* 
```
install john ssh2john.py:-

link:-
https://github.com/openwall/john/blob/bleeding-jumbo/run/ssh2john.py

steps:-
wget https://github.com/openwall/john/blob/bleeding-jumbo/run/ssh2john.py
chmod +x ssh2john.py
./ssh2john.py

convert the hash to binary formate for john:-
./ssh2john.py (file_name) > output.txt
```


```
Crack a hash file using wordlist:-
	john forJohn.txt --wordlist=/usr/share/wordlists/rockyou.txt
```


gpg2john tryhackme.asc > hash

john --wordlist=/usr/share/wordlists/rockyou.txt hash