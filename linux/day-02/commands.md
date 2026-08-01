\# File \& Directory Operations



\## Commands



| Command | Description |

|---------|-------------|

| `touch` | Create an empty file |

| `mkdir` | Create a directory |

| `mkdir -p` | Create nested directories |

| `cp source dest` | Copy a file |

| `cp -r srcdir destdir` | Copy a directory recursively |

| `mv source dest` | Move or rename a file/directory |

| `rm <file>` | Remove a file |

| `rm -r <dir>` | Remove a directory recursively |

| `rm -f <file>` | Force remove a file |

| `rmdir <dir>` | Remove empty directories |



\---



\## Finding Files \& Links



| Command | Description |

|---------|-------------|

| `find <path> -name "pattern"` | Find files and directories by name |

| `find . -type {f,d,l,c,b}` | Search for files or directories by type |

| `locate <name>` | Quickly find files using the prebuilt index |

| `which <command>` | Show the full path of an executable command |

| `ln source\_file hardlink\_name` | Create a hard link |

| `ln -s source link` | Create a symbolic (soft) link to a file or directory |

| `ln -sf target linkname` | Force overwrite an existing symbolic link |



