For normal hash:
```
mkpasswd -m sha-512 hello
```

For salt hash:
```
 mkpasswd -m sha-512 hello --salt="fuckman"
```


```
openssl passwd hello
```