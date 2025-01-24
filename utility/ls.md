# command : ls

Used for lists files and permissions

```bash
ls 
ls -l # for list files with permissions
ls -a # for list hidden files
```
#### Output will looks like

```
total 16
-rw-rw-r-- 1 kartikey kartikey 5581 Jan 23 17:32 iostat.md
-rw-rw-r-- 1 kartikey kartikey  583 Jan 23 17:43 lscpu.md
-rw-rw-r-- 1 kartikey kartikey 3226 Jan 23 17:44 mpstat.md
```

- total 16 = size of all files 
- - = regular file
- rw- = user permission
- rw- = group permission
- r-- = other permission
- 1 = num of hard links to the file ( A hard link is like giving a file another name. Both names point to the same data on the disk. )
- kartikey = username 
- kartikey = group 
- 5588 = File size in bytes 
- Jan 23 17:32  = Last modified date 

