Sort installed packages by size
-------------------------------
    dpkg-query -Wf '${Installed-Size}\t${Package}\t${Status}\n' | sort -n


Purge removed packages
----------------------
    dpkg -l | grep ^rc | awk '{print $2}' | xargs dpkg -P


List packages
-------------
    dpkg --get-selections
    apt list --installed


List files installed by a package
---------------------------------
    dpkg-query -L <package_name>


Cleanup
-------
```
sudo apt clean
sudo apt autoclean
sudo apt autoremove
```
