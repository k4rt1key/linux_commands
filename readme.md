# Command Usage Table

## System Monitoring Commands

| **Use Case**                                    | **Primary Command** | **Alternatives**               | **When to Use**                                                                 |
|-------------------------------------------------|---------------------|--------------------------------|---------------------------------------------------------------------------------|
| **Monitor CPU usage and I/O statistics**        | `iostat`            | `mpstat`                       | Use `iostat` to monitor CPU and I/O statistics for devices and partitions.     |
| **View detailed CPU architecture information**  | `lscpu`             | N/A                            | Use `lscpu` to view detailed information about CPU architecture.               |
| **Monitor CPU usage per core**                  | `mpstat`            | `top`                          | Use `mpstat` for per-core CPU usage, ideal for diagnosing CPU bottlenecks.     |
| **Monitor memory usage (free/used)**            | `free`              | `vmstat`                       | Use `free` for a simple view of memory usage, or `vmstat` for detailed stats.  |
| **Monitor overall system performance**          | `vmstat`            | `top`                          | Use `vmstat` for detailed system performance, including CPU, memory, and I/O. |

---

## Disk Monitoring and Management Commands

| **Use Case**                                    | **Primary Command** | **Alternatives**               | **When to Use**                                                                 |
|-------------------------------------------------|---------------------|--------------------------------|---------------------------------------------------------------------------------|
| **Check disk space usage of file systems**      | `df`                | `lsblk`                        | Use `df` to check available and used disk space on mounted file systems.       |
| **Estimate disk space usage of files/folders**  | `du`                | `stat`                         | Use `du` to check space usage for specific files or directories.               |
| **Partition a disk or view partition info**     | `fdisk`             | `lsblk`                        | Use `fdisk` for creating or managing disk partitions.                          |
| **List block devices**                          | `lsblk`             | `fdisk`                        | Use `lsblk` for a detailed tree view of storage devices and their partitions.  |
| **View detailed file information**             | `stat`              | `ls`                           | Use `stat` to get detailed metadata for a file, such as timestamps.            |

---

## Network Monitoring Commands

| **Use Case**                                    | **Primary Command** | **Alternatives**               | **When to Use**                                                                 |
|-------------------------------------------------|---------------------|--------------------------------|---------------------------------------------------------------------------------|
| **View active network connections**            | `netstat`           | `ss`                           | Use `netstat` to view network connections, routing tables, and interface stats.|
| **View detailed socket statistics**            | `ss`                | `netstat`                      | Use `ss` for faster and more detailed socket information than `netstat`.       |

---

## Process Monitoring and Management Commands

| **Use Case**                                    | **Primary Command** | **Alternatives**               | **When to Use**                                                                 |
|-------------------------------------------------|---------------------|--------------------------------|---------------------------------------------------------------------------------|
| **Display process information**                | `ps`                | `top`, `pstree`                | Use `ps` for a snapshot of current processes.                                  |
| **Monitor process resource usage (CPU/memory)** | `pidstat`           | `ps aux`                       | Use `pidstat` to monitor per-process CPU and memory usage over time.           |
| **Monitor processes in real time**             | `top`               | `htop`                         | Use `top` for a real-time view of running processes and resource usage.        |
| **View processes in a tree structure**         | `pstree`            | `ps --forest`                  | Use `pstree` to view parent-child relationships between processes.             |
| **Terminate a process by PID**                 | `kill`              | `pkill`, `xkill`               | Use `kill` to terminate a specific process by its PID.                         |
| **Monitor threads of a process**               | `ps -eLf`           | `top`                          | Use `ps -eLf` to monitor threads and their IDs (LWP).                          |
| **Debug multithreaded applications**           | `ps -eLf`           | N/A                            | Use `ps -eLf` for debugging and analyzing thread-level details.                |

---

## Text Processing Commands

| **Use Case**                                    | **Primary Command** | **Alternatives**               | **When to Use**                                                                 |
|-------------------------------------------------|---------------------|--------------------------------|---------------------------------------------------------------------------------|
| **Search for patterns in files/output**        | `grep`              | `awk`, `sed`                   | Use `grep` for simple pattern matching in text files or command output.        |
| **Extract and process text data**              | `awk`               | `grep`, `sed`                  | Use `awk` for advanced text processing and extracting specific fields.         |
| **Perform text replacements**                  | `sed`               | `awk`, `grep`                  | Use `sed` for stream editing, such as replacing or modifying text patterns.    |

---

## When to Use `ps aux` and `ps -eLf`

| **Use Case**                                    | **`ps aux`**     | **`ps -eLf`**                 | **When to Use**                                                                 |
|-------------------------------------------------|------------------|-------------------------------|---------------------------------------------------------------------------------|
| **Monitor overall process resource usage**      | ✅                | ❌                             | Use `ps aux` to view overall CPU and memory usage of all processes.            |
| **Monitor memory/CPU usage of processes**       | ✅                | ❌                             | Use `ps aux` for a summary of resource usage by processes.                     |
| **Find a specific process by name**             | ✅                | ❌                             | Use `ps aux` with `grep` to locate a process by name.                          |
| **Monitor threads of a process**                | ❌                | ✅                             | Use `ps -eLf` to view all threads of a specific process.                       |
| **Debug multithreaded applications**            | ❌                | ✅                             | Use `ps -eLf` for detailed thread-level monitoring and debugging.              |
| **Track thread IDs (LWP)**                      | ❌                | ✅                             | Use `ps -eLf` to list thread IDs for multithreaded processes.                  |
| **Count threads in a process**                  | ❌                | ✅                             | Use `ps -eLf` to count threads for performance or debugging purposes.          |
