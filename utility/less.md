# Linux Commands: `less`, `tail`, and `head`

## `less` Command

**Description**:  
`less` is a terminal pager used to view the contents of a file one screen at a time. It allows both forward and backward navigation.

**Syntax**:  
```bash
less [options] <filename>
```

**Important Flags**:  
- `-N`: Display line numbers.
- `-S`: Chop long lines (disable line wrapping).
- `-F`: Exit immediately if the file fits on one screen.
- `-R`: Display raw control characters (useful for colored output).
- `+F`: Follow the file in real-time (similar to `tail -f`).
