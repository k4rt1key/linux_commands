# Command : lsblk

list information about all available block devices on the system, such as hard drives, SSDs, USB drives, partitions, and more

```bash
lsblk
lsblk -f # displays filesystem info
lsblk -o NAME,SIZE # selecting particular cols
lsblk -l # displays in simple list format insted of tree format
```

## Output will look like 

Name | Maj:MIN | RM | SIZE | RO | TYPE | MOUNTPOINT

* Name = Name of the device
* MAJ:MIN = Major and Minor device number 
* RM = 1 if device is removable 0 if not 
* RO = Readonly flag 
* Mountpoint = Directory where device is mounted on