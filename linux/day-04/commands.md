# Permissions & Ownership

## Understanding Permissions

- `ls -l <file>` : Show file permissions, owner, group, size, and modified date.
- `chmod 755 <file>` : Change file permissions using numeric (octal) mode.
- `chmod u+x <file>` : Add execute permission to the owner (symbolic mode).
- `chown user:group <file>` : Change the owner and/or group of a file.
- `chgrp group <file>` : Change the group ownership of a file.
- `umask` : Show or set the default permission mask for newly created files.

---

## Superuser Access

- `sudo <command>` : Execute a command with superuser (root) privileges.
- `su <username>` : Switch to another user account.
- `sudo -i` : Open an interactive root shell.
- `visudo` : Safely edit the sudoers file.
