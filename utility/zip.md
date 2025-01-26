# command : zip

**Description:**
zip is used to compress files and directories into a .zip archive.

**Key Flags:**
-r: Recursively compress directories.

-q: Quiet mode (suppress output).

-e: Encrypt the archive with a password.

-u: Update an existing archive.

-d: Delete files from an archive.

**Examples:**
Create a zip archive:
```bash
zip archive.zip file1 file2 dir1
```

Recursively compress a directory:
```bash
zip -r archive.zip dir1
```

Extract a zip archive:
```bash
unzip archive.zip
```

Encrypt a zip archive:
```bash
zip -e secure.zip file1
```

Update an existing zip archive:
```bash
zip -u archive.zip newfile.txt
```