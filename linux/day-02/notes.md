# Day 02 - File & Directory Operations

## Overview

Linux stores everything as files. Learning how to create, copy, move, delete, search, and link files/directories is one of the most important Linux skills.

---

# Creating Files

## touch

Creates an empty file.

Syntax

```bash
touch filename
```

Example

```bash
touch notes.txt
```

If the file already exists, `touch` updates its timestamp instead of creating a new file.

---

# Creating Directories

## mkdir

Creates a new directory.

Syntax

```bash
mkdir directory_name
```

Example

```bash
mkdir projects
```

---

## mkdir -p

Creates nested directories in one command.

Syntax

```bash
mkdir -p parent/child/grandchild
```

Example

```bash
mkdir -p devops/linux/day02
```

If parent directories don't exist, Linux creates them automatically.

---

# Copying Files & Directories

## cp

Copies files.

Syntax

```bash
cp source destination
```

Example

```bash
cp notes.txt backup.txt
```

The original file remains unchanged.

---

## cp -r

Copies directories recursively.

Syntax

```bash
cp -r source_directory destination_directory
```

Example

```bash
cp -r project project_backup
```

The `-r` (recursive) option copies every file and subdirectory.

---

# Moving & Renaming

## mv

Moves or renames files and directories.

Syntax

```bash
mv source destination
```

Move example

```bash
mv notes.txt Documents/
```

Rename example

```bash
mv notes.txt linux_notes.txt
```

Directory rename

```bash
mv old_folder new_folder
```

The `mv` command can both move and rename.

---

# Removing Files & Directories

## rm

Deletes a file.

Syntax

```bash
rm filename
```

Example

```bash
rm notes.txt
```

Deleted files generally cannot be recovered.

---

## rm -r

Deletes a directory and everything inside it.

Syntax

```bash
rm -r directory_name
```

Example

```bash
rm -r project
```

The `-r` option stands for recursive.

---

## rm -f

Force deletes files without confirmation.

Syntax

```bash
rm -f filename
```

Example

```bash
rm -f notes.txt
```

Useful inside scripts.

---

### Remove directory forcefully

```bash
rm -rf directory_name
```

Example

```bash
rm -rf project
```

This is one of the most dangerous Linux commands because it permanently removes everything recursively without asking for confirmation.

---

## rmdir

Deletes only empty directories.

Syntax

```bash
rmdir directory_name
```

Example

```bash
rmdir empty_folder
```

If the directory contains files, the command fails.

---

# Finding Files

## find

Searches files and directories.

Syntax

```bash
find path -name "pattern"
```

Example

```bash
find . -name "*.txt"
```

Searches for every `.txt` file in the current directory and its subdirectories.

---

## find with -type

Search by object type.

Syntax

```bash
find . -type f
```

Types

| Type | Meaning |
|------|---------|
| f | Regular file |
| d | Directory |
| l | Symbolic link |
| c | Character device |
| b | Block device |

Example

```bash
find . -type d
```

Shows only directories.

---

# locate

Quickly finds files using a prebuilt database.

Syntax

```bash
locate filename
```

Example

```bash
locate notes.txt
```

Unlike `find`, `locate` searches an indexed database, making it much faster.

If a recently created file isn't found, update the database:

```bash
sudo updatedb
```

---

# which

Shows the full path of an executable command.

Syntax

```bash
which command
```

Example

```bash
which python3
```

Output

```text
/usr/bin/python3
```

Useful for checking where Linux executes a command from.

---

# Hard Links

## ln

Creates a hard link.

Syntax

```bash
ln source_file hardlink_name
```

Example

```bash
ln notes.txt backup_notes
```

Characteristics

- Shares the same inode
- Both names refer to the same data
- Deleting one does not delete the data if another hard link exists
- Cannot span different file systems
- Cannot link directories (normally)

---

# Symbolic (Soft) Links

## ln -s

Creates a symbolic link.

Syntax

```bash
ln -s target_file link_name
```

Example

```bash
ln -s notes.txt shortcut
```

Characteristics

- Stores the path to another file
- Has its own inode
- Can point to files or directories
- Can span different file systems
- Becomes broken if the original target is deleted

---

# Force Replace a Symbolic Link

## ln -sf

Creates or overwrites an existing symbolic link.

Syntax

```bash
ln -sf target link_name
```

Example

```bash
ln -sf new_notes.txt shortcut
```

Useful when updating symbolic links in automation scripts.

---

# Hard Link vs Soft Link

| Hard Link | Soft Link |
|------------|-----------|
| Shares same inode | Different inode |
| Points to actual data | Points to file path |
| Cannot cross file systems | Can cross file systems |
| Cannot link directories | Can link directories |
| Works even if original filename is deleted | Breaks if original file is deleted |

---

# Important Points

- `touch` creates an empty file.
- `mkdir -p` creates nested directories.
- `cp` copies files.
- `cp -r` copies directories.
- `mv` moves **and** renames files/directories.
- `rm` removes files.
- `rm -r` removes directories recursively.
- `rm -rf` forcefully removes everything.
- `rmdir` removes only empty directories.
- `find` searches in real time.
- `locate` searches using an index (much faster).
- `which` shows the executable's location.
- `ln` creates hard links.
- `ln -s` creates symbolic links.
- `ln -sf` forcefully updates symbolic links.
