## 1. Hard Links
**What it is:**
A hard link is an additional name for an existing file. It points directly to the inode of the original file.

***How it works:**

- Both the original file and the hard link share the same inode and data blocks.
- The inode has a link count that tracks how many hard links point to it.
- Data is only deleted when the link count drops to 0 (no hard links remain).

**Effect of deleting the original file:**

- Deleting the original file does not affect the hard link because the data is still referenced by the hard link.
- The link count decreases by 1, but the data remains accessible through the hard link.

**Example:**
```bash
ln file.txt hardlink.txt  # Create a hard link
rm file.txt              # Delete the original file
cat hardlink.txt         # Data is still accessible
```

## 2. Soft Links (Symbolic Links)

**What it is:**
A soft link is a shortcut to the original file. It points to the file's path, not its inode.

**How it works:**

- The soft link contains the path to the original file.
- If the original file is deleted, the soft link becomes broken (dangling) because the path no longer points to valid data.
- Effect of deleting the original file: Deleting the original file breaks the soft link. It no longer works and becomes invalid.

**Example:**

```bash
ln -s file.txt symlink.txt  # Create a soft link
rm file.txt                # Delete the original file
cat symlink.txt            # Error: Broken link
```
**Key Differences: Hard Link vs. Soft Link**
| Feature                | Hard Link                     | Soft Link                     |
|------------------------|-------------------------------|-------------------------------|
| **Points to**          | Inode of the file             | Path of the file              |
| **Cross-filesystem**   | No                            | Yes                           |
| **Link directories**   | No                            | Yes                           |
| **If source is deleted** | Data remains accessible     | Link becomes broken           |
| **Command**            | `ln <source> <link>`          | `ln -s <source> <link>`       |