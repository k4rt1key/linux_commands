# Practical 7

Watch any files for continues modification

```bash

```

# Practical 8

Get Used and free memory

```bash
free -h --total | awk 'NR == 4 {print "Used = " $2 "\nFree = " $3}'
```

# Practical 9 

Get used cpu and context switches per process

```bash
pidstat -w | awk '{print "PID=" $4 " CS = " $6 "-" $5}'
pidstat | awk 'NR > 2 {print "PID=" $4 " CPU=" $9}'
```


# Practical 10

Get disk read write stat

```bash
iostat -x  | grep "nvme0n1" | awk '{print "device = " $1  "\nread/sec = " $2 "\nwrite/sec : " $8 "\nreadbytes/sec: " $2 * 1000 "\nwritebyte/sec: " $9 * 1000 "\nUtilization :" $21}' 
```

# Practical 11

TCP and UDP connections

```bash
netstat -s | awk 'NR > 29 && NR < 49 {print}'
```

# Practical 12 

Total Running threads 

```bash
pidstat -t | awk '{ if($4 != "-"){count++;} } END {print count;} '
ps -eLf | awk '{count++} END {print count}'

# both is giving diff results
```

# Practical 13 

Running processes

```bash
ps aux | awk '$8 ~ /R/ {print "PID = " $2 " RUNNING"}'
```
