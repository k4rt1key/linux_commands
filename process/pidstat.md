# Command : pidstat

Used to monitor every individual task currently being managed by the Linux kernel on the Linux system. 

```bash
pidstat
```

### Output information

```
Linux 5.15.0-130-generic (kartikey)     01/23/2025     _x86_64_        (8 CPU)

12:26:15 PM   UID       PID    %usr %system   %guest   %wait    %CPU   CPU  Command
12:26:15 PM     0         1    0.00    0.00    0.00    0.00    0.00     7   systemd
12:26:15 PM     0         2    0.00    0.00    0.00    0.00    0.00     1   kthreadd
```

### For Human Readable Format
```bash
pidstat --human
```

### For I/O Information
```bash
pidstat -d 
```

### For Memory Information
```bash
pidstat -r
```

### For Memory Information Output

```
12:29:27 PM   UID       PID  minflt/s  majflt/s     VSZ     RSS   %MEM  Command
12:29:27 PM     0         1      0.62      0.00  169808   13112   0.08  systemd
12:29:27 PM     0       306      0.02      0.49   84516   47216   0.30  systemd-journal
12:29:27 PM     0       337      0.13      0.00   25292    7868   0.05  systemd-udevd
```

#### Explanation

| Metric     | Description                                    |
|------------|------------------------------------------------|
| `minflt/s` | Minor page fault per second                    |
| `majflt/s` | Major page fault per second                    |
| `VSZ`      | Virtual memory size                            |
| `RSS`      | Resident set size ( Memory Used by process's stack, text, heap )                             |
| `%MEM`     | Percentage of physical memory process is using |

### For Thread Information

```bash
pidstat -t
```

```bash 
pidstat -p [number] # for particular pid
```


#### Thread Information Output

```
Linux 5.15.0-130-generic (kartikey)     01/23/2025      _x86_64_        (8 CPU)

12:36:40 PM    UID      TGID       TID   %usr  %system  %guest   %wait   %CPU   CPU  Command
12:36:40 PM     0         1         -    0.00    0.00    0.00    0.00    0.00     0  systemd
12:36:40 PM     0         -         1    0.00    0.00    0.00    0.00    0.00     0  |__systemd
12:36:40 PM     0         2         -    0.00    0.00    0.00    0.00    0.00     1  kthreadd
12:36:40 PM     0         -         2    0.00    0.00    0.00    0.00    0.00     1  |__kthreadd
```

#### Explanation

| Metric | Description     |
|--------|-----------------|
| `TGID` | Thread group ID |
| `TID`  | Thread ID       |

### For getting context switches / sec of each processes

```bash
pidstat -w 
```

#### Output 
```
Linux 5.15.0-130-generic (kartikey)     01/23/2025      _x86_64_        (8 CPU)

06:11:11 PM   UID       PID   cswch/s nvcswch/s  Command
06:11:11 PM     0         1      0.60      0.04  systemd
06:11:11 PM     0         2      0.03      0.00  kthreadd
```

- **cswch/s** = Volunteer context switches / sec
- **nvcswch/s** = Forcefully context switches / sec