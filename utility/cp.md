## cp Command
**Description:**

The cp command is used to copy files or directories from one location to another.

**Syntax:**
```bash
cp [options] <source> <destination>
```

**Important Flags:**

-r: Copy directories recursively (required for copying directories).

-i: Interactive mode (prompt before overwriting files).

-v: Verbose mode (display detailed output of the copying process).

-u: Update (copy only if the source is newer than the destination or if the destination is missing).

-p: Preserve file attributes (e.g., ownership, timestamps).

**Common Usage:**
```
cp file.txt /backup/            # Copy file to a directory
cp -r dir1/ dir2/               # Copy a directory recursively
cp -i file.txt backup/file.txt  # Prompt before overwriting
cp -u file.txt backup/          # Copy only if source is newer
```