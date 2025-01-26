## mv Command
**Description:**
The mv command is used to move or rename files or directories.

**Syntax:**

```bash
mv [options] <source> <destination>
```

**Important Flags:**

```bash
-i: Interactive mode (prompt before overwriting files).

-v: Verbose mode (display detailed output of the moving process).

-u: Update (move only if the source is newer than the destination or if the destination is missing).

-f: Force (overwrite without prompting).
```

**Common Usage:**

```bash
mv file.txt /backup/            # Move file to a directory
mv oldname.txt newname.txt      # Rename a file
mv -i file.txt backup/file.txt  # Prompt before overwriting
mv -u file.txt backup/          # Move only if source is newer
```