# Command : mpstat

- Used for getting CPU usage stats
- Can monitor workload distribution across cpus

```bash
mpstat [options] [interval] [count]
```

### Output will look like
```
Linux 5.15.0-130-generic (kartikey)     01/23/2025      _x86_64_        (8 CPU)

10:12:16 AM  CPU    %usr   %nice    %sys  %iowait    %irq   %soft  %steal  %guest  %gnice   %idle
10:12:16 AM  all    4.09    0.01    1.12    0.08    0.00    0.03    0.00    0.00    0.00   94.67
```
| Parameter                            | Description                                                                                         |
|--------------------------------------|-----------------------------------------------------------------------------------------------------|
| Linux 5.15.0-130-generic (kartikey)  | Kernel version & hostname                                                                           |
| _x86_64_                             | Architecture                                                                                        |
| (8 CPU)                              | 8-core CPU                                                                                          |
| CPU all                              | Indicates that values are averaged across all CPUs                                                  |
| %usr                                 | % of CPU time spent on executing user-space processes                                               |
| %nice                                | % of CPU time spent on executing user-space processes of positive nice value (low-priority process) |
| %sys                                 | % of CPU time spent on executing kernel-space or system processes                                   |
| %iowait                              | % of CPU time idle while waiting for I/O operations                                                 |
| %irq                                 | % of CPU time spent servicing hardware interrupts                                                   |
| %soft                                | % of CPU time spent servicing software interrupts                                                   |
| %steal                               | % of time CPU waits while hypervisor services another virtual machine                               |
| %guest                               | % of time spent running guest OS in a virtual environment                                           |
| %gnice                               | % of time spent running nice processes on guest OS                                                  |
| %idle                                | % of time CPU was idle                                                                              |



#### For Specifing which CPU to monitor 

```bash
mpstat -P ALL
mpstat -P 1
mpstat -P 2
```

#### For Display interrupts stats

```bash
mpstat -I CPU
mpstat -I SUM
```

- CPU = Display interrupts for each cpu
- SUM = Display summerized stats


#### For displaying output in json format

```bash
mpstat -o JSON
```

#### For displaying output in particular intervals and particular times

```bash
mpstat -P ALL 5 10
```

5 10 => For interval of **5 sec** & for **10 times**