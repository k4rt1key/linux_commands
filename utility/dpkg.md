# dpkg

- To add, remove, purge .deb packages

```bash
sudo dpkg -i package_name.deb # to install .deb package
sudo dpkg -r package_name     # to remove some package
sudo dpkg -P package_name     # purge ( to remove package and it's config )
sudo dpkg -l                  # list packages
sudo dpkg -c package_name.deb # to query contents of that package
```