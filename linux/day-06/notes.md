# Day 06 - Package Management (APT)

## Overview

APT (Advanced Package Tool) is the high-level package manager used on Debian/Ubuntu systems to install, update, upgrade, search, and remove software packages.

---

# Package Repositories

Linux packages are downloaded from configured repositories.

APT uses a local **package index** to know which packages and versions are available.

---

## apt update

Refreshes the local package index.

```bash
sudo apt update
```

It checks the configured repositories for updated package information.

> `apt update` does **not** upgrade installed packages.

---

## apt upgrade

Upgrades installed packages to their available newer versions.

```bash
sudo apt upgrade
```

Common workflow:

```bash
sudo apt update
sudo apt upgrade
```

---

# Installing Packages

## apt install

Installs a package and its required dependencies.

```bash
sudo apt install <pkg>
```

Example:

```bash
sudo apt install nginx
```

Multiple packages can be installed together:

```bash
sudo apt install git curl wget
```

---

## apt reinstall

Reinstalls an already installed package.

```bash
sudo apt reinstall <pkg>
```

Useful when package files are damaged or need to be restored.

---

# Removing Packages

## apt remove

Removes the package but keeps its configuration files.

```bash
sudo apt remove <pkg>
```

---

## apt purge

Removes the package along with its configuration files.

```bash
sudo apt purge <pkg>
```

### Difference

```text
remove → package removed, configuration kept
purge  → package + configuration removed
```

---

## apt autoremove

Removes packages that were installed as dependencies but are no longer required.

```bash
sudo apt autoremove
```

---

# Searching & Package Information

## apt search

Searches for packages by name or description.

```bash
apt search <keyword>
```

Example:

```bash
apt search docker
```

---

## apt show

Displays detailed information about a package.

```bash
apt show <pkg>
```

Information can include:

- Package version
- Description
- Dependencies
- Package size
- Repository information

---

## apt list

Lists packages.

Show all installed packages:

```bash
apt list --installed
```

Show packages that can be upgraded:

```bash
apt list --upgradable
```

---

# Fixing Package Problems

## --fix-broken

Attempts to fix broken package dependencies.

```bash
sudo apt --fix-broken install
```

Useful when package installation or dependency configuration has failed.

---

# Full Upgrade

## apt full-upgrade

Upgrades the system while allowing APT to install or remove packages when required to complete the upgrade.

```bash
sudo apt full-upgrade
```

It is more flexible than a normal `apt upgrade`.

---

# Package Information

## apt policy

Shows installed and available package versions and repository information.

```bash
apt policy <pkg>
```

---

## apt depends

Shows the dependencies required by a package.

```bash
apt depends <pkg>
```

---

## apt rdepends

Shows packages that depend on the specified package.

```bash
apt rdepends <pkg>
```

---

# Important Points

- `apt update` → Updates the package index.
- `apt upgrade` → Upgrades installed packages.
- `apt install` → Installs packages.
- `apt remove` → Removes packages but keeps configuration files.
- `apt purge` → Removes packages and configuration files.
- `apt autoremove` → Removes unused dependencies.
- `apt search` → Searches for packages.
- `apt show` → Shows package information.
- `apt list --installed` → Lists installed packages.
- `apt list --upgradable` → Lists packages with available upgrades.
- `apt --fix-broken install` → Attempts to fix broken dependencies.
- `apt full-upgrade` → Performs a more flexible system upgrade.

### Common Workflow

```bash
sudo apt update
sudo apt upgrade
sudo apt install <pkg>
```
