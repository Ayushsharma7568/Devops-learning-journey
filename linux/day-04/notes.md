# Day 04 - Permissions & Ownership

## Overview

Linux permissions control who can read, write, and execute files or directories. Every file has an owner, a group, and a set of permissions that determine who can access it.

---

# Understanding Permissions

## Permission String

A typical permission string looks like:

```text
-rwxr-xr--
```

It consists of:

- First character → File type (`-` for file, `d` for directory)
- Next three characters → Owner permissions
- Next three characters → Group permissions
- Last three characters → Others permissions

Permission letters:

- `r` → Read
- `w` → Write
- `x` → Execute
- `-` → Permission not granted

---

## Numeric (Octal) Permissions

Each permission has a numeric value:

| Permission | Value |
|------------|------:|
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |

Examples:

| Permission | Value |
|------------|------:|
| `rwx` | 7 |
| `rw-` | 6 |
| `r-x` | 5 |
| `r--` | 4 |
| `---` | 0 |

Example:

```bash
chmod 755 script.sh
```

Meaning:

- Owner → `7` = `rwx`
- Group → `5` = `r-x`
- Others → `5` = `r-x`

---

## ls -l

Displays detailed information about a file.

```bash
ls -l <file>
```

Shows:

- Permissions
- Owner
- Group
- File size
- Last modified date

---

## chmod (Numeric Mode)

Changes file permissions using numeric values.

```bash
chmod 755 <file>
```

Common permissions:

| Permission | Meaning |
|------------|---------|
| `777` | Everyone has full access |
| `755` | Owner: rwx, Group/Others: r-x |
| `644` | Owner: rw-, Group/Others: r-- |
| `600` | Owner only can read and write |

---

## chmod (Symbolic Mode)

Changes permissions using symbols.

Syntax

```bash
chmod u+x <file>
```

Symbols:

- `u` → User (Owner)
- `g` → Group
- `o` → Others
- `a` → All users

Operators:

- `+` → Add permission
- `-` → Remove permission
- `=` → Set exact permission

Examples

```bash
chmod u+x script.sh
chmod g-w file.txt
chmod o+r notes.txt
```

---

## chown

Changes the owner and/or group of a file.

```bash
chown user:group <file>
```

Example

```bash
sudo chown ayush:developers script.sh
```

---

## chgrp

Changes only the group ownership.

```bash
chgrp developers script.sh
```

---

## umask

Displays or changes the default permission mask.

```bash
umask
```

A lower umask value gives more default permissions to newly created files.

---

# Superuser Access

## sudo

Runs a command with root privileges.

```bash
sudo <command>
```

Example

```bash
sudo apt update
```

---

## su

Switches to another user.

```bash
su <username>
```

Example

```bash
su ayush
```

Using only `su` switches to the root user (if permitted).

---

## sudo -i

Opens an interactive root shell.

```bash
sudo -i
```

Exit using:

```bash
exit
```

---

## visudo

Safely edits the `sudoers` configuration file.

```bash
sudo visudo
```

Always use `visudo` instead of editing the file directly because it checks for syntax errors before saving.

---

# Important Points

- Every file has an owner, group, and permission set.
- `r = 4`, `w = 2`, `x = 1`.
- `755` and `644` are the most commonly used permission values.
- `chmod` changes permissions.
- `chown` changes the owner.
- `chgrp` changes the group.
- `umask` controls default permissions for new files.
- Use `sudo` only when administrative privileges are required.
- Always use `visudo` to edit the sudoers file.
