# Command : df 

For displaying **disk space usage** on mounted filesystems 

```bash
df

-h # human readable
-i # includes index nodes ( index nodes which contains metadata )
-k # display in 1K Blocks
-B 512 # display in 512 Bytes blocks 
-T # display filesystem types

-a # summary of all file systems
--total # total disk usage 
```

### Output will be in this format 
Filesystem | 1K-blocks | Used | Avilable | % Used | Mounted on