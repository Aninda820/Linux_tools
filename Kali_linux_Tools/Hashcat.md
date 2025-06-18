
Hashcat use for identify the hash type
Step: 1
```
This is use for identify the hash type 

Installation command:-
sudo apt install hash-identifier   --- to identify the hash type


Command for use tool:-
sudo hash-identifire <Enter>
hash: <paste the hash>
```


Step: 2
```
This is use to get hash ID number

Installation command:-
sudo apt install hashid

Command for use tool:-
sudo hashid -m "CBFDAC6008F9CAB4083784CBD1874F76618D2A97"

```


Step: 3
```
This tool use for crack the hash using wordlists

Installation command:-
sudo apt install hashcat  --- crack hashes 


Command for use tool:
sudo hashcat -m 3200 "CBFDAC6008F9CAB4083784CBD1874F76618D2A97" /usr/share/wordlists/rockyou.txt
```


```
Browser online tools: 

https://hashes.com/en/decrypt/hash

https://crackstation.net/

https://gchq.github.io/CyberChef/

https://hashkiller.io/listmanager
```


```
HASHCAT website for hash type check:-
https://hashcat.net/wiki/doku.php?id=example_hashes

then type <ctrl + f> for search
type the hash type you find from <hashid/ hash-identifire>
```


```
Command for crack SALT-HASH 
	hashcat -m <mode id> "<hash value>:<salt>" wordlists 

Ex:
hashcat -m 110 "e5d8870e5bdd26602cab8dbe07a942c8669e56d6:tryhackme" /usr/share/wordlists/rockyou.txt
```
