# Practical 14

List all details of file permission, owner, group

```bash
ls -l filename.txt
```

# Practical 15

List File stats file type, block size, time of last data modification, time of last status change

```bash
stat cpu/iostat.md  | awk '{if(NR == 2) {print $8 "\nBlock sizee : " $4} if(NR == 6){print $2 $3 $4} if(NR==7){print $2 $3 $4} }'
# or
stat --format="Type: %F/Block Size: %o/ Modify: %Y/ Change: %Z" cpu/iostat.md 
```

# Practical 16

Maximum number of threads supported by OS Kernel

```bash
cat /proc/sys/kernel/threads-max
```

# Pracical 17 ( DOUBT )

List name of zombie processes & interrupted processes

```bash
ps aux | awk '$8 ~ /I/ {count++} END {print count}'
ps aux | awk '$8 ~ /Z/ {count++} END {print count}'
```

# Practical 18

List all partitions & print sector wise details of each partition

```bash
sudo mdisk -l 
```

# Practical 19

List All device drives available in my system & exclude loop devices from it

```bash
df -h | grep -v 'loop'
# or
iostat -d | grep -v 'loop' | awk 'NR > 3 {print $1}'
```

# Practical 20

List the size occupied by each directory & size occupied by files inside that directory (separate commands for directory & file)

```bash
du -k -a ../
```