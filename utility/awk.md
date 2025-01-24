# `awk` Command with Actions

The `awk` command is a powerful text processing tool that allows advanced actions and manipulations on data in files.

## Basic Usage
```bash
# Syntax:
awk 'pattern { action }' file
```

## Examples with Actions

### 1. Print All Lines
```bash
# Print all lines in file.txt
awk '{ print $0 }' file.txt
```

### 2. Print Specific Columns
```bash
# Print the first and third columns
awk '{ print $1, $3 }' file.txt
```

### 3. Perform Arithmetic Operations
```bash
# Add the values in the first and second columns
awk '{ print $1 + $2 }' file.txt
```

### 4. Append Text to Each Line
```bash
# Append " - processed" to each line
awk '{ print $0 " - processed" }' file.txt
```

### 5. Convert Text to Uppercase
```bash
# Convert the second column to uppercase
awk '{ $2 = toupper($2); print $0 }' file.txt
```

### 6. Convert Text to Lowercase
```bash
# Convert the second column to lowercase
awk '{ $2 = tolower($2); print $0 }' file.txt
```

### 7. Sum Values in a Column
```bash
# Sum all values in the second column
awk '{ sum += $2 } END { print "Total:", sum }' file.txt
```

### 8. Calculate Average of a Column
```bash
# Calculate the average of the second column
awk '{ sum += $2; count++ } END { print "Average:", sum / count }' file.txt
```

### 9. Replace a Field Value
```bash
# Replace the value in the second column with "new_value"
awk '{ $2 = "new_value"; print $0 }' file.txt
```

### 10. Add a New Column
```bash
# Add a new column with the sum of the first and second columns
awk '{ $NF = $1 + $2; print $0 }' file.txt
```

### 11. Print Line Numbers
```bash
# Print line numbers with each line
awk '{ print NR, $0 }' file.txt
```

### 12. Print Lines in Reverse Order
```bash
# Print lines in reverse order
awk '{ lines[NR] = $0 } END { for (i = NR; i > 0; i--) print lines[i] }' file.txt
```

### 13. Filter and Modify Lines
```bash
# Print lines where the second column is greater than 100 and double its value
awk '$2 > 100 { $2 *= 2; print $0 }' file.txt
```

### 14. Highlight Specific Fields
```bash
# Highlight the second column in red
awk '{ $2 = "\033[1;31m" $2 "\033[0m"; print $0 }' file.txt
```

### 15. Delete Specific Lines
```bash
# Delete lines where the second column is "delete"
awk '$2 != "delete" { print $0 }' file.txt
```

### 16. Extract and Format Data
```bash
# Format output as "Column1: value, Column2: value"
awk '{ print "Column1: "$1", Column2: "$2 }' file.txt
```

### 17. Process Multiple Files
```bash
# Print the filename and line number with each line
awk '{ print FILENAME, NR, $0 }' file1.txt file2.txt
```

### 18. Conditional Field Addition
```bash
# Add a new column with "PASS" or "FAIL" based on the third column
awk '{ $NF = ($3 >= 50) ? "PASS" : "FAIL"; print $0 }' file.txt
```

### 19. Extract Unique Values
```bash
# Extract unique values from the second column
awk '!seen[$2]++ { print $2 }' file.txt
```

### 20. Transpose Rows and Columns
```bash
# Transpose rows into columns
awk '{ for (i = 1; i <= NF; i++) { a[NR,i] = $i } } END { for (i = 1; i <= NF; i++) { for (j = 1; j <= NR; j++) printf a[j,i] " "; print "" } }' file.txt
```

### 21. Generate a Summary Report
```bash
# Generate a report of counts by a specific field (e.g., second column)
awk '{ counts[$2]++ } END { for (value in counts) print value, counts[value] }' file.txt
```

### 22. Print Lines Based on Length
```bash
# Print lines with more than 50 characters
awk 'length > 50 { print $0 }' file.txt
```

### 23. Combine Lines into One
```bash
# Combine all lines into a single line
awk '{ printf $0 " " } END { print "" }' file.txt
```

### 24. Skip Blank Lines
```bash
# Print only non-blank lines
awk 'NF > 0 { print $0 }' file.txt
```

### 25. Extract Fields with Delimiters
```bash
# Use "," as a field separator and print the second field
awk -F, '{ print $2 }' file.csv
```
