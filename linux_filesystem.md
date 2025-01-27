'''
# Linux Directory Structure

| Directory Name   | Description (To the Point)                          | Examples                                      |
|------------------|----------------------------------------------------|-----------------------------------------------|
| `/`              | Root directory, starting point of the file system  | All other directories are nested under it     |
| `/bin`           | Essential binary executables for basic system functionality | `ls`, `cp`, `mv`, `bash`               |
| `/boot`          | Files required for booting the system              | Kernel, initramfs, bootloader configs         |
| `/dev`           | Device files representing hardware devices         | `/dev/sda` (hard disk), `/dev/tty` (terminal) |
| `/etc`           | System-wide configuration files and scripts        | `/etc/passwd`, `/etc/fstab`                   |
| `/home`          | Personal directories for each user                 | `/home/username`                              |
| `/lib`           | Shared libraries required by system binaries       | `libc.so`, `libpthread.so`                    |
| `/media`         | Mount point for removable media                    | USB drives, CDs, DVDs                         |
| `/mnt`           | Temporary mount points for file systems            | Network shares, additional disks              |
| `/opt`           | Third-party or optional software packages          | Proprietary software, custom apps             |
| `/proc`          | Virtual file system for process and system information | `/proc/cpuinfo`, `/proc/meminfo`          |
| `/root`          | Home directory for the root user                   | Root user's personal files                    |
| `/run`           | Runtime data for running processes                 | PID files, sockets                            |
| `/sbin`          | System administration binaries                     | `fdisk`, `ifconfig`, `init`                   |
| `/srv`           | Data for services provided by the system           | Web server files, FTP data                    |
| `/sys`           | Virtual file system for kernel and hardware information | Kernel parameters, device info            |
| `/tmp`           | Temporary files deleted upon reboot                | Short-lived files                             |
| `/usr`           | User-installed software, libraries, and documentation | `/usr/bin`, `/usr/lib`, `/usr/local`      |
| `/var`           | Variable data such as logs, databases, and spool files | `/var/log`, `/var/cache`, `/var/spool`    |
| `/lost+found`    | Recovered files after a file system check          | Files recovered after a crash                 |
'''