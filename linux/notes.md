# Day 07 - Package Management (dpkg & apt-cache)

## Overview

Day 7 covers `dpkg`, the low-level Debian package manager, and `apt-cache`, which is used to view and search package information.

---

# dpkg

`dpkg` is the low-level package management tool used by Debian and Ubuntu systems.

It mainly works with `.deb` packages.

Unlike APT, `dpkg` does not automatically resolve dependencies.

---

## Installing a .deb Package

```bash
dpkg -i <package.deb>
```

Installs a local `.deb` package.

Example:

```bash
sudo dpkg -i package.deb
```

---

## Removing a Package

```bash
sudo dpkg -r <package>
```

Removes the package but keeps its configuration files.

---

## Purging a Package

```bash
sudo dpkg -P <package>
```

Removes the package and its configuration files.

---

## Listing Installed Packages

```bash
dpkg -l
```

Displays installed packages and their status.

To check a specific package:

```bash
dpkg -l <package>
```

---

## Package Information

```bash
dpkg -s <package>
```

Shows information about an installed package.

---

## List Files Installed by a Package

```bash
dpkg -L <package>
```

Shows all files installed by a package.

Example:

```bash
dpkg -L nginx
```

---

## Find Package Owning a File

```bash
dpkg -S <file>
```

Shows which installed package owns a particular file.

Example:

```bash
dpkg -S /usr/bin/curl
```

---

## Configure a Package

```bash
sudo dpkg --configure <package>
```

Configures a package that has been unpacked but not completely configured.

---

# apt-cache

`apt-cache` is used to query information from the APT package cache.

It does not install or remove packages.

---

## Search Packages

```bash
apt-cache search <keyword>
```

Searches available packages using a keyword.

Example:

```bash
apt-cache search docker
```

---

## Show Package Information

```bash
apt-cache show <package>
```

Displays package information such as version, description, and dependencies.

---

## Check Package Versions

```bash
apt-cache policy <package>
```

Shows installed and available versions and repository information.

---

## Show Dependencies

```bash
apt-cache depends <package>
```

Shows the packages required by a package.

---

## Show Reverse Dependencies

```bash
apt-cache rdepends <package>
```

Shows packages that depend on the specified package.

---

## Show Available Versions

```bash
apt-cache madison <package>
```

Displays available versions of a package from configured repositories.

---

# APT vs dpkg

| APT | dpkg |
|-----|------|
| High-level package manager | Low-level package manager |
| Handles dependencies | Does not automatically handle dependencies |
| Works with repositories | Mainly works with `.deb` files |
| Used for normal package management | Used for direct `.deb` management |

Example:

```bash
sudo apt install nginx
```

vs.

```bash
sudo dpkg -i package.deb
```

---

# Important Points

- `dpkg` is the low-level package manager for Debian-based systems.
- `dpkg -i` installs a local `.deb` package.
- `dpkg -r` removes a package.
- `dpkg -P` removes a package and its configuration.
- `dpkg -L` shows files installed by a package.
- `dpkg -S` identifies which package owns a file.
- `apt-cache` is mainly used to query package information.
- `apt-cache search` searches for packages.
- `apt-cache policy` shows package versions and repository information.
- `dpkg` does not automatically resolve dependencies like APT.
