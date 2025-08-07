
tool: fuff

```
 ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://MACHINE_IP/FUZZ
```


`ffuf -u http://{MachineIp}/ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-words.txt -H 'Host: FUZZ.futurevera.thm' -fs {size}`

- This command gave me two subdomains and both of them had a message on the screen saying  
    `{subdomain}.futurevera.thm is only availiable via internal VPN`
- Got nothing important while enumerating directories or files.





```
ffuf -u 'http://10.10.74.25/assets/index.php?FUZZ=id' -mc all -ic -t 100 -w /usr/share/seclists/Discovery/Web-Content/raft-small-words-lowercase.txt -fs 0
```
### **Command Breakdown**

| Option                                                                        | Explanation                                                                                                                                                                                      |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `ffuf`                                                                        | Starts the Fast Web Fuzzer.                                                                                                                                                                      |
| `-u 'http://10.10.74.25/assets/index.php?FUZZ=id'`                            | URL to fuzz. The word `FUZZ` is the placeholder that will be replaced by each word from the wordlist. So this means you are fuzzing the **parameter name**, like `?username=id`, `?cmd=id`, etc. |
| `-mc all`                                                                     | Match **all** HTTP status codes (default is usually 200 only). Useful to catch unusual responses (like 302, 403, etc.).                                                                          |
| `-ic`                                                                         | Makes the matching **case-insensitive**. Useful when parameter names might have varying capitalization.                                                                                          |
| `-t 100`                                                                      | Run 100 concurrent threads (faster but heavier on the server).                                                                                                                                   |
| `-w /usr/share/seclists/Discovery/Web-Content/raft-small-words-lowercase.txt` | Wordlist to use for the fuzzing — common lowercase web-related words.                                                                                                                            |
| `-fs 0`                                                                       | Filter out responses with **0 bytes** in size (usually means empty or invalid responses).                                                                                                        |


# Fuzzing a live subdomain for common sensitive files/directories  
###### -w: wordlist of common paths (e.g., from SecLists)  
###### -u: target URL, FUZZ is where the wordlist items go  
###### -e: extensions to try (.git, .env, .bak, .zip, .yml, .json)  
# -mc: match status codes (200 OK is a hit, 403 Forbidden might mean a directory exists)  
# -recursion: go deeper into found directories  
ffuf -w /path/to/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt -u https://dev.example.com/FUZZ \  
    -e .git,.env,.bak,.zip,.yml,.json -mc 200,403 -recursion -rate 50 -of json -o dev_leaks.json  
  
# For API-specific endpoints (e.g., /v1/users, /graphql)  
# Build a custom wordlist by extracting from JS files (LinkFinder) or GitHub searches.  
ffuf -w my_api_wordlist.txt -u https://api.example.com/FUZZ -mc 200 -H "Content-Type: application/json"