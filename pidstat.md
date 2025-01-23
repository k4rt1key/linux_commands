# pidstat

## Basic Usage
```bash
pidstat
```

### Sample Output
```
Linux 5.15.0-130-generic (kartikey)     01/23/2025      _x86_64_        (8 CPU)

12:26:15 PM   UID       PID    %usr %system  %guest   %wait    %CPU   CPU  Command
12:26:15 PM     0         1    0.00    0.00    0.00    0.00    0.00     7  systemd
12:26:15 PM     0         2    0.00    0.00    0.00    0.00    0.00     1  kthreadd
```

## Command Options

### Human Readable Format
```bash
pidstat --human
```

### I/O Information
```bash
pidstat -d 
```

### Memory Information
```bash
pidstat -r
```

### Memory Information Output
```
12:29:27 PM   UID       PID  minflt/s  majflt/s     VSZ     RSS   %MEM  Command
12:29:27 PM     0         1      0.62      0.00  169808   13112   0.08  systemd
12:29:27 PM     0       306      0.02      0.49   84516   47216   0.30  systemd-journal
12:29:27 PM     0       337      0.13      0.00   25292    7868   0.05  systemd-udevd
```

### Memory Metrics Explanation

| Metric | Description |
|--------|-------------|
| `minflt/s` | Minor page fault per second |
| `majflt/s` | Major page fault per second |
| `VSZ` | Virtual memory size |
| `RSS` | Resident set size |
| `%MEM` | Percentage of physical memory process is using |

### Thread Information
```bash
pidstat -t
```

### Thread Information Output
```
Linux 5.15.0-130-generic (kartikey)     01/23/2025      _x86_64_        (8 CPU)

12:36:40 PM   UID      TGID       TID    %usr %system  %guest   %wait    %CPU   CPU  Command
12:36:40 PM     0         1         -    0.00    0.00    0.00    0.00    0.00     0  systemd
12:36:40 PM     0         -         1    0.00    0.00    0.00    0.00    0.00     0  |__systemd
12:36:40 PM     0         2         -    0.00    0.00    0.00    0.00    0.00     1  kthreadd
12:36:40 PM     0         -         2    0.00    0.00    0.00    0.00    0.00     1  |__kthreadd
```

### Thread Metrics Explanation

| Metric | Description |
|--------|-------------|
| `TGID` | Thread group ID |
| `TID` | Thread ID |