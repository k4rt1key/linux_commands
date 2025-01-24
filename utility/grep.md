# `grep` Command with Regular Expressions

The `grep` command is used to search for patterns within files. It supports regular expressions to enable advanced pattern matching.

## Basic Usage
```bash
# Syntax:
grep [options] 'pattern' file
```

## Examples with Regular Expressions

### 1. Simple String Matching
```bash
# Search for the word "hello" in file.txt
grep 'hello' file.txt
```

### 2. Case-Insensitive Search
```bash
# Search for "hello" in file.txt, ignoring case
grep -i 'hello' file.txt
```

### 3. Matching Whole Words
```bash
# Search for the whole word "hello"
grep -w 'hello' file.txt
```

### 4. Matching Lines Starting with a Pattern
```bash
# Match lines starting with "start"
grep '^start' file.txt
```

### 5. Matching Lines Ending with a Pattern
```bash
# Match lines ending with "end"
grep 'end$' file.txt
```

### 6. Match Any Single Character
```bash
# Match lines with "h.llo" (e.g., hello, hillo)
grep 'h.llo' file.txt
```

### 7. Match Zero or More of the Previous Character
```bash
# Match lines with "ho*" (e.g., ho, hoo, hooo)
grep 'ho*' file.txt
```

### 8. Match One or More of the Previous Character
```bash
# Match lines with "ho+" (e.g., hoo, hooo but not ho)
grep 'ho+' file.txt
```

### 9. Match Zero or One of the Previous Character
```bash
# Match lines with "colou?r" (e.g., color, colour)
grep 'colou?r' file.txt
```

### 10. Match Any of a Set of Characters
```bash
# Match lines with "gr[aeiou]p" (e.g., grap, grep, grip)
grep 'gr[aeiou]p' file.txt
```

### 11. Match Any Character Except a Set
```bash
# Match lines with "gr[^aeiou]p" (e.g., grp, grtp but not grap)
grep 'gr[^aeiou]p' file.txt
```

### 12. Match a Range of Characters
```bash
# Match lines with "[a-z]" (any lowercase letter)
grep '[a-z]' file.txt
```

### 13. Escape Special Characters
```bash
# Match lines with "a+b" (literal plus sign)
grep 'a\+b' file.txt
```

### 14. Match Lines Containing a Word Boundry
```bash
# Match lines containing "word" as a whole word
grep '\<word\>' file.txt
```

### 15. Use Extended Regular Expressions
```bash
# Match lines with "(foo|bar)" (either foo or bar)
grep -E '(foo|bar)' file.txt
```

### 16. Count Matching Lines
```bash
# Count the number of lines matching "pattern"
grep -c 'pattern' file.txt
```

### 17. Display Line Numbers
```bash
# Display line numbers of matches
grep -n 'pattern' file.txt
```

### 18. Recursive Search in Directories
```bash
# Search for "pattern" in all files in a directory
grep -r 'pattern' /path/to/dir
```

### 19. Invert Match
```bash
# Display lines that do not match "pattern"
grep -v 'pattern' file.txt
```

### 20. Display Only Matching Parts
```bash
# Show only the matching parts of lines
grep -o 'pattern' file.txt
```

### 21. Match Lines with Specific Length
```bash
# Match lines with exactly 5 characters
grep '^.{5}$' file.txt
```

### 22. Exclude Binary Files
```bash
# Ignore binary files while searching
grep --binary-files=without-match 'pattern' file.txt
```

### 23. Highlight Matches
```bash
# Highlight matches in the output
grep --color=always 'pattern' file.txt
```

### 24. Suppress Error Messages
```bash
# Suppress error messages for nonexistent or unreadable files
grep -s 'pattern' file.txt
```

### 25. Search in Multiple Files
```bash
# Search for "pattern" in multiple files
grep 'pattern' file1.txt file2.txt
