# ps

The ps command is used to display information about active processes in terminal
```bash 
ps [options]
```

```bash
ps -e 
```
Shows all processes active in terminal


```bash
ps -ef
```

Shows detailed information about processes
Output :

```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 Jan22 ?        00:00:03 /sbin/init splash
root           2       0  0 Jan22 ?        00:00:00 [kthreadd]
root           3       2  0 Jan22 ?        00:00:00 [rcu_gp]
```

PPID = Parent PID
STIME = Start time


Show processes for the current user:

```bash
ps -u <username>
```

Displays processes for a specific user.

Show processes with a specific PID:

```bash
ps -p <pid>
```

Displays information for the process with the specified PID.

Show processes in a tree format:

```bash
ps -ejH
```


Show processes with memory usage:


```bash
ps aux 
```

```bash
ps aux --sort=-%cpu
ps aux --sort=-%mem
```

```
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0 169808 13112 ?        Ss   Jan22   0:03 /sbin/init splash
root           2  0.0  0.0      0     0 ?        S    Jan22   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   Jan22   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   Jan22   0:00 [rcu_par_gp]
```

