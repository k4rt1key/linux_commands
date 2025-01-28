# Command : vmstat

Reports information about a computer system's memory, processes, and performance

```bash
vmstat [options] [delay] [count]
```

### Output 

```
 procs    -----------memory----------   --swap--   -----io----  --system-- ------cpu-----
 r  b   swpd   free    buff   cache     si   so    bi    bo     in   cs    us sy id wa st
 3  0    0    7774156 280176 4341828    0    0     12    22     19  120    5  1  94  0  0
```

### Metrics Details

#### Procs Metrics

| Metric | Description                                  | Unit  |
|--------|----------------------------------------------|-------|
| `r`    | Number of processes waiting for CPU time     | Count |
| `b`    | Number of processes in uninterruptible sleep | Count |

- **Uninterruptible sleep**
A process state where a program is waiting for a specific resource (like a disk operation to complete) and cannot be interrupted by any signals or events until that resource becomes available

#### Memory Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| `swpd` | Amount of virtual memory used | KB |
| `free` | Amount of idle memory | KB |
| `buff` | Memory used as buffers | KB |
| `cache` | Memory used as cache | KB |
| `inact` | Inactive memory (Linux-specific) | KB |
| `active` | Active memory (Linux-specific) | KB |

- **Buffered v/s cached memory**
Buffer memory is used to temporarily store data during transfers, while cache memory stores frequently accessed data and instructions. 

- **Active v/s Inactive memory**
"Active memory" refers to memory that is currently being actively used by running processes, while "Inactive memory" refers to memory that has not been accessed recently and can be readily reclaimed by the system if needed

- **Inactive v/s Free memory**
"Inactive memory" is considered **reserved** for a potential future use by a process that may need it again, while "Free memory" is truly available to be **allocated to any process right away.** 


### Swap Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| `si`   | Amount of memory swapped in from disk | KB/s |
| `so`   | Amount of memory swapped out to disk | KB/s |

### IO Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| `bi`   | Blocks received from a block device | KB/s |
| `bo`   | Blocks sent to a block device | KB/s |

### System Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| `in`   | Number of interrupts, including the clock | Count/sec |
| `cs`   | Number of context switches | Count/sec |

### CPU Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| `us` | Time spent on user processes (non-kernel) | Percentage (%) |
| `sy` | Time spent on system (kernel) processes | Percentage (%) |
| `id` | Time spent idle | Percentage (%) |
| `wa` | Time spent waiting for I/O | Percentage (%) |
| `st` | Time stolen from a virtual machine | Percentage (%) |

## Special Commands

### Memory Statistics Since Boot

Displays information about memory since system is booted 

```bash 
vmstat -s
```


### Disk Information

Displays information about disk 

```bash
vmstat -d
```

#### Disk Metrics

| Metric | Description | Unit |
|--------|-------------|------|
| **total** | Total number of read operations completed by the disk | Operations |
| **merged** | Number of adjacent read requests merged into a single request | Requests |
| **sectors** | Total number of sectors read | Sectors |
| **ms** | Total time spent on read operations | Milliseconds |

**Note:** A sector is typically 512 bytes or 1 KB, depending on the disk configuration.



### Per second updatation

```bash
vmstat 2 # appends updated metrics after every 1 second