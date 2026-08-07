# Text Processing & Filters

## Searching Text

- `grep "pattern" <file>` : Search for lines matching a pattern in a file.
- `grep -i "pattern" <file>` : Perform a case-insensitive search.
- `grep -r "pattern" <directory>` : Search recursively in all files of a directory.
- `grep -v "pattern" <file>` : Show lines that do not match the pattern.
- `grep -n "pattern" <file>` : Display matching lines with line numbers.
- `grep -c "pattern" <file>` : Count the number of matching lines.

---

## Sorting, Filtering & Transforming

- `sort <file>` : Sort lines alphabetically (or numerically with options).
- `sort -r <file>` : Sort lines in reverse order.
- `uniq <file>` : Remove adjacent duplicate lines.
- `uniq -c <file>` : Count occurrences of each unique line.
- `cut -d: -f1 <file>` : Extract specific fields using a delimiter.
- `tr 'a-z' 'A-Z'` : Translate or replace characters.
- `sed 's/old/new/g' <file>` : Find and replace text in a file or stream.
- `awk '{print $1}' <file>` : Process and print selected fields from a file.
- `xargs <command>` : Build and execute commands from standard input.

---

## Comparing & Counting

- `wc -l <file>` : Count the number of lines in a file.
- `comm <file1> <file2>` : Compare two sorted files line by line.
