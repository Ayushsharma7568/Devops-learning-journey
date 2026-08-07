# Day 05 - Text Processing & Filters

## Overview

Linux provides powerful text processing tools for searching, filtering, sorting, transforming, and comparing text files. These commands are commonly used in shell scripting, log analysis, and system administration.

---

# Searching Text

## grep

Searches for lines matching a pattern in a file.

```bash
grep "pattern" <file>
```

Common options:

- `-i` → Ignore case.
- `-r` → Search recursively in directories.
- `-v` → Display lines that do not match.
- `-n` → Show line numbers.
- `-c` → Count matching lines.

Examples

```bash
grep "error" logfile.txt
grep -i "linux" notes.txt
grep -r "TODO" project/
```

---

# Sorting, Filtering & Transforming

## sort

Sorts the contents of a file alphabetically.

```bash
sort <file>
```

Reverse sorting:

```bash
sort -r <file>
```

---

## uniq

Removes adjacent duplicate lines.

```bash
uniq <file>
```

Count duplicate occurrences:

```bash
uniq -c <file>
```

> **Note:** `uniq` only removes consecutive duplicate lines. Use it with `sort` for best results.

---

## cut

Extracts specific fields from each line.

```bash
cut -d: -f1 <file>
```

- `-d` → Delimiter
- `-f` → Field number

---

## tr

Translates or replaces characters.

```bash
tr 'a-z' 'A-Z'
```

Example:

```bash
echo "hello" | tr 'a-z' 'A-Z'
```

Output:

```text
HELLO
```

---

## sed

Stream editor used to search and replace text.

```bash
sed 's/old/new/g' <file>
```

Example:

```bash
sed 's/Linux/Ubuntu/g' notes.txt
```

---

## awk

Processes text by fields.

```bash
awk '{print $1}' <file>
```

Example:

```bash
awk '{print $2}' data.txt
```

Useful for extracting columns from structured text.

---

## xargs

Builds and executes commands using input from another command.

```bash
xargs <command>
```

Example:

```bash
find . -name "*.log" | xargs rm
```

---

# Comparing & Counting

## wc -l

Counts the number of lines in a file.

```bash
wc -l <file>
```

---

## comm

Compares two sorted files line by line.

```bash
comm file1 file2
```

Shows:

- Lines unique to the first file
- Lines unique to the second file
- Lines common to both files

---

# Important Points

- `grep` is the most commonly used command for searching text.
- `sort` arranges data alphabetically or numerically.
- `uniq` removes only adjacent duplicate lines.
- `cut` extracts selected fields from text.
- `tr` replaces or converts characters.
- `sed` is mainly used for find-and-replace operations.
- `awk` processes text by columns or fields.
- `xargs` converts standard input into command arguments.
- `wc -l` counts lines in a file.
- `comm` compares two **sorted** files.
