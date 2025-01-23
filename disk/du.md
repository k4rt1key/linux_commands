# Command : du

For display **disk usage** of files and directories

```bash
du
du -h # human readable
du -sh <PATH> # human readable disk usage for particular directory 
du -ah <PATH> # human readable disk usage for particular directory and files
du -h <PATH> --exclude="*.txt" # human readable disk usage for all sub dirs and files  
du -m <PATH> # in mb
```

### Output will be in this format 

Size | File/Dir Name