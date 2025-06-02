

### Tool: cron
##### cron bassic command:

```
service cron start
service cron stop
service restart
service cron status
```


```
syntax: 
* * * * * command

1st * --> Every Minute (M) [0-59]
2nd * --> Every Houre (H) [0-23]
3rd * --> Every Day on the month (DOM)[1-31]
4th * --> Every Month (MON) [1-12]
5th * --> Every Day of the Week (DOW (0-6) [0=Sunday]

----------------------------------------------
|Field         |   Allowed Values   |Min|Max |
|--------------|--------------------|---|----|
| Minute       |     0-59           | 0 | 59 |
| Hour         |     0-23           | 0 | 23 |
| Day of Month |     1-31           | 1 | 31 |
| Month        |     1-12           | 1 | 12 |
| Day of Week  | 0-6  ( 0  = Sunday)| 0 | 6  |
----------------------------------------------

### **✅ Examples of Different Cron Jobs**
```



```
For list cronjobs running on my computer we run:
crontab -l

For edit crontab we use this command:
crontab -e

Instead of using crontab -e, you can manually open the crontab file:
nano /var/spool/cron/crontabs/$(whoami)
```


```
* All values: the * is The wild card character that is used to specify for all the occurrence of that parameter it is used for.


-a range of value: The Hyphen (-) is used to specify the range of time in which the script can run.
0-59 0-25 * * * * /home/user/script.sh


/ Divide a value into steps: The slash (/) is used to create specified intervals of time within a range. [Every 10 minutes of every day]


These examples showcase the Different symbols used in chron expression, such as the (*) Representing all values, The comma (,) separating individual values, The - denoting a range of values and the / dividing a value into steps

```


```
Run command after every Reboot:
@reboot echo "Walocme Back to kali"


change user when use crontab:
crontab -u root -e
```