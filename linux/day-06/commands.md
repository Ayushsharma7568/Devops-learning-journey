# Package Management (APT)

## APT — High-Level Package Manager

- `sudo apt update` : Refresh the local package index from configured repositories.
- `sudo apt upgrade` : Upgrade installed packages to their latest available versions.
- `sudo apt install <pkg>` : Install a package along with its dependencies.
- `sudo apt remove <pkg>` : Uninstall a package while keeping its configuration files.
- `sudo apt purge <pkg>` : Uninstall a package and remove its configuration files.
- `sudo apt autoremove` : Remove packages that are no longer required.
- `apt search <keyword>` : Search for packages by name or description.
- `apt show <pkg>` : Display detailed information about a package.
- `apt list --installed` : List all currently installed packages.

---

## Additional APT Commands

- `sudo apt install <pkg1> <pkg2>` : Install multiple packages at once.
- `sudo apt reinstall <pkg>` : Reinstall an already installed package.
- `sudo apt --fix-broken install` : Fix broken package dependencies.
- `sudo apt full-upgrade` : Upgrade packages while allowing package removals or new installations when required.
- `apt list --upgradable` : List installed packages that have available upgrades.
- `apt policy <pkg>` : Show installed and available package versions and repository information.
- `apt depends <pkg>` : Show the dependencies of a package.
- `apt rdepends <pkg>` : Show packages that depend on the specified package.
