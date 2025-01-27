# Practical 1 

Get the number of context switches

```bash
vmstat | awk 'NR == 3 {print "Number of context switches : " $12}'
```

# Practical 2 

Get the number of running processes

```bash
ps aux | awk '$8 ~ /R/ {count++} END {print count}'
```


# Practical 3 

Get CPU used and idle percentage

```bash
mpstat | awk 'NR == 4 {print "Idle: " $13 "\n" "Used: " 100 - $13}'
```


# Practical 4

Get inet address and MAC address

```bash
ifconfig | awk '{ if(NR == 23){print "Ip Address: " $2} if(NR == 19){print "INET Address: " $2} }'
```


# Practical 5 

Get contex switches per second of each process

```bash
pidstat -w | awk '{print "PID: " $4 "\n"  "Context switches/second: " $6 + $7}'
```


# Practical 6 

Get load avg for 1min, 5min and 15min

```bash
uptime | awk '{print "1MIN:"  $8 " 5MIN: "  $9 " 15MIN: "  $10}'
```