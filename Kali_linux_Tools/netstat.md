

### netstat

Following an initial check for existing interfaces and network routes, it is worth looking into existing communications. The `netstat` command can be used with several different options to gather information on existing connections.

  

- `netstat -a`: shows all listening ports and established connections.
- `netstat -at` or `netstat -au` can also be used to list TCP or UDP protocols respectively.
- `netstat -l`: list ports in “listening” mode. These ports are open and ready to accept incoming connections. This can be used with the “t” option to list only ports that are listening using the TCP protocol (below)

  

![](https://i.imgur.com/BbLdyrr.png)

  

- `netstat -s`: list network usage statistics by protocol (below) This can also be used with the `-t` or `-u` options to limit the output to a specific protocol.

  

![](https://i.imgur.com/mc8OWP0.png)

  

- `netstat -tp`: list connections with the service name and PID information.

  

![](https://i.imgur.com/fDYQwbW.png)

  

This can also be used with the `-l` option to list listening ports (below)

  

![](https://i.imgur.com/JK7DNv0.png)

  

We can see the “PID/Program name” column is empty as this process is owned by another user.

Below is the same command run with root privileges and reveals this information as 2641/nc (netcat)

![](https://i.imgur.com/FjZHqlY.png)`   `

- `netstat -i`: Shows interface statistics. We see below that “eth0” and “tun0” are more active than “tun1”.

![](https://i.imgur.com/r6IjpmZ.png)

  

  

The `netstat` usage you will probably see most often in blog posts, write-ups, and courses is `netstat -ano` which could be broken down as follows;

- `-a`: Display all sockets
- `-n`: Do not resolve names
- `-o`: Display timers

  

![](https://i.imgur.com/UxzLBRw.png)