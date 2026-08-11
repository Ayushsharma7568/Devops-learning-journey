# Package Management (dpkg & apt-cache)

## dpkg — Low-Level Package Manager

- `dpkg -i <package.deb>` : Install a `.deb` package.
- `dpkg -r <package>` : Remove an installed package while keeping configuration files.
- `dpkg -P <package>` : Remove a package along with its configuration files.
- `dpkg -l` : List installed packages.
- `dpkg -l <package>` : Check whether a specific package is installed.
- `dpkg -s <package>` : Show information about an installed package.
- `dpkg -L <package>` : List files installed by a package.
- `dpkg -S <file>` : Find which installed package owns a file.
- `dpkg --configure <package>` : Configure an unpacked package.

---

## apt-cache — Package Information

- `apt-cache search <keyword>` : Search for packages using a keyword.
- `apt-cache show <package>` : Display detailed information about a package.
- `apt-cache policy <package>` : Show installed and available versions of a package.
- `apt-cache depends <package>` : Show the dependencies of a package.
- `apt-cache rdepends <package>` : Show packages that depend on the specified package.
- `apt-cache madison <package>` : Display available package versions from repositories.
