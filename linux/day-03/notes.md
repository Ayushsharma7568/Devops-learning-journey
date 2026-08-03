# Day 03 - Viewing Files, Searching Text & Operators

## Overview

Day 3 covers commands for viewing file contents, searching text, using wildcards, and performing comparisons in shell scripts.

---

# Viewing Files

## cat

Displays the contents of a file.

```bash
cat <file>
```

---

## cat -n

Displays file contents with line numbers.

```bash
cat -n <file>
```

---

## more

Views a file one page at a time.

```bash
more <file>
```

- `Space` → Next page
- `Enter` → Next line
- `q` → Quit

---

## less

Views a file with forward/backward navigation.

```bash
less <file>
```

Useful shortcuts:

- `/text` → Search
- `n` → Next match
- `Shift + N` → Previous match
- `q` → Quit

---

## head

Displays the first few lines of a file.

```bash
head -n 10 <file>
```

---

## tail

Displays the last few lines of a file.

```bash
tail -n 10 <file>
```

---

## tail -f

Monitors a file in real time.

```bash
tail -f <file>
```

Press **Ctrl + C** to stop.

---

## wc

Counts lines, words, and characters.

```bash
wc <file>
```

---

## sed

Prints selected lines from a file.

```bash
sed -n "5,10p" <file>
```

---

## diff

Compares two files.

```bash
diff -u file1 file2
```

---

# Searching Text

## grep

Searches for text inside files.

```bash
grep "text" <file>
```

Common options:

- `-i` → Ignore case
- `-n` → Show line numbers
- `-r` → Search recursively

Example:

```bash
grep -in "linux" notes.txt
```

---

# Wildcards

Wildcards match multiple filenames.

## `*`

Matches zero or more characters.

```bash
ls *.txt
```

---

## `?`

Matches exactly one character.

```bash
ls file?.txt
```

---

## `[]`

Matches one character from a set.

```bash
ls file[123].txt
```

---

# Numerical Comparison Operators

Used to compare integer values.

| Operator | Meaning |
|----------|---------|
| `-eq` | Equal to |
| `-ne` | Not equal to |
| `-gt` | Greater than |
| `-lt` | Less than |
| `-ge` | Greater than or equal to |
| `-le` | Less than or equal to |

Example:

```bash
if [ "$a" -gt "$b" ]; then
    echo "a is greater"
fi
```

---

# String Comparison Operators

Used to compare strings.

| Operator | Meaning |
|----------|---------|
| `=` | Equal |
| `!=` | Not equal |
| `-z` | String is empty |
| `-n` | String is not empty |

Example:

```bash
if [ "$name" = "Ayush" ]; then
    echo "Match found"
fi
```

---

# Logical Operators

## AND (`&&`)

Executes the second command only if the first succeeds.

```bash
command1 && command2
```

---

## OR (`||`)

Executes the second command only if the first fails.

```bash
command1 || command2
```

---

## NOT (`!`)

Reverses the result of a command or condition.

```bash
if ! grep "error" logfile.txt
```

---

# Important Points

- `less` is more powerful than `more`.
- `tail -f` is commonly used to monitor log files.
- `grep` is one of the most frequently used Linux commands.
- `*` matches multiple characters, while `?` matches exactly one.
- Numerical operators compare integers.
- String operators compare text.
- Logical operators combine or negate conditions in shell scripts.
