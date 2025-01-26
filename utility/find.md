# command : find

Used for finding files / directories 

```bash
find [PATH] [EXPRESSION]
```

#### find by exact name
```bash
find . -name "free.md"
```

#### case insensitive 
```bash
find . -iname "free.md"
```

#### using regex
```bash
find . -regex "*\.png$"
```

#### for file or directory
```bash
find . -type d
find . -type f 
```

#### by size 
```bash
find . -size +10M # greater than 10 MB
find . -size -1k # less than 1 KB
```

#### by modification and access time
```bash
find . -atime +30 # access time more than 30 days before
find . -mtime -8 # in recent 8 days
```

#### by permissions

```bash
find . -perm 777
```

#### execute a command by on found lines

```bash
find . ".*\.txt$" -exec cat {} \;
# -exec ... \; is syntax
# {} all output files one by one
# cat is command we want to perform
```

#### combine multiple conditions
```bash
find .  \(  -name "*.png" -o -name "*.jpg"  \)
```

#### exclude particular directory 

```bash
find . \( -path "./disk" -prune \) -o -name "*md" -print
```