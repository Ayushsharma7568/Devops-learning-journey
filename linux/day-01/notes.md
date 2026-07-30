# Linux Day 1 - Terminal Basics & Navigation

## Topics Covered
- Terminal basics
- Directory navigation
- Listing directory contents
- Viewing command history
- Getting command help

---

## Key Concepts

### Linux File System
- Linux uses a hierarchical directory structure.
- Everything starts from the root directory (`/`).
- Every file and directory exists somewhere under the root.

### Current Working Directory
- Every terminal session has a current working directory.
- Most commands operate relative to the current directory.

### Hidden Files
- Files and directories beginning with `.` are hidden.
- Use `ls -a` to display hidden files.

### Home Directory
- Every user has a home directory.
- `~` represents the current user's home directory.

### Relative vs Absolute Path
- Absolute path starts from `/`.
- Relative path starts from the current directory.

Example:
```
Absolute : /home/ayush/Documents
Relative : Documents
```

---

## Things I Practiced
- Navigated between directories.
- Listed files using different `ls` options.
- Switched to parent, home and previous directories.
- Viewed command history.
- Used `man` and `--help` to learn command usage.

---

## Important Points
- Linux is case-sensitive.
- Spaces in file names should be avoided when possible.
- Most Linux commands follow this format:

Command → Option → Argument

Example:
```
ls -la Documents
```

---

## Revision
- Root directory: `/`
- Home directory: `~`
- Parent directory: `..`
- Current directory: `.`
