# command : ps

The ps command is used to display information about active processes 

```bash 
ps [options]
```

```bash
ps -e # Shows all processes active in terminal
```

```bash
ps -ef # Shows detailed information aboutthat processes
```


Output :

```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 Jan22 ?        00:00:03 /sbin/init splash
root           2       0  0 Jan22 ?        00:00:00 [kthreadd]
root           3       2  0 Jan22 ?        00:00:00 [rcu_gp]
```

- PPID = Parent PID
- STIME = Start time
- TTY = Terminal Type
- C = CPU utilization

### Show processes for the particular user:

```bash
ps -u <username>
```

### Show processes with a specific PID:

```bash
ps -p <pid>
```

### Show processes in a tree format:

```bash
ps -ejH
```


### Show processes with memory usage:


```bash
ps aux 
```

```bash
ps aux --sort=-%cpu
ps aux --sort=-%mem
```

#### Output : 
```
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0 169808 13112 ?        Ss   Jan22   0:03 /sbin/init splash
root           2  0.0  0.0      0     0 ?        S    Jan22   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   Jan22   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   Jan22   0:00 [rcu_par_gp]
```

### Show processes with threads 

```bash 
ps -eLf
```

#### Output 
- LWP = The LWP column shows the thread ID (TID) of individual threads within a process.
- NLWP = Number of LWP

### When to use ps aux and when ps -eLf

| **Use Case**                           | **`ps aux`** | **`ps -eLf`** |
|----------------------------------------|--------------|---------------|
| **Monitor overall process resource usage** | ✅            | ❌             |
| **Monitor memory/CPU usage of processes** | ✅            | ❌             |
| **Find a specific process by name**     | ✅            | ❌             |
| **Monitor threads of a process**        | ❌            | ✅             |
| **Debug multithreaded applications**    | ❌            | ✅             |
| **Track thread IDs (LWP)**              | ❌            | ✅             |
| **Count threads in a process**          | ❌            | ✅             |
