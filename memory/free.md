# Command : free

For display the amount of free and used memory in the system, including physical RAM and swap space. 

```bash
free 
free -h
free -k # kilobytes
free -m # megabytes
free -g # gigabyters
free -t # also shows shared, buffered and cache memory
free -s 3 # re-fetches after 3 seconds
```

### Output will look like 

total | used | free | shared | buff/cache | avilable

- total = total physical mem
- used = used physical mem 
- free = unused physical mem
- shared = physical mem shared between processes
- buff/cache = physical mem used for buff and cache 
- avilable = free + buff/cache mem ( that much mem can be avilable if process needs )
For both memory and swap