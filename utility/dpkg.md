# command: dpkg

**Key Features of dpkg:**
- Install: It installs .deb packages from local files or repositories.
- Remove: It removes installed packages.
- Query: It allows you to query information about installed packages.
- Manage Dependencies: While dpkg itself doesn't handle dependencies, it can work with other tools like apt (Advanced Packaging Tool) to manage them.

```bash
sudo dpkg -i package_name.deb # to install .deb
sudo dpkg -r package_name # to remove 
sudo dpkg -P package_name # purge ( remove package and it's config )
sudo dpkg -l # list packages
dpkg -c package_name.deb # to query contents of that package

```