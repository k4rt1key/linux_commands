
## `tail` Command

**Description**:  
`tail` is used to display the last part of a file. It is commonly used to monitor log files in real-time.

**Syntax**:  
```bash
tail [options] <filename>
```

**Important Flags**:  
- `-n <number>`: Display the last `n` lines (default is 10).
- `-f`: Follow the file in real-time (useful for logs).
- `-c <number>`: Display the last `n` bytes of the file.
- `-F`: Follow the file by name, even if it is rotated.
