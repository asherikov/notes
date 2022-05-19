'Verbose' boot
--------------
Disable "quiet" & "splash" options in grub config
- `sudo vi /etc/default/grub`
- `sudo update-grub`


Fast login
----------
Disable message of the day in `/etc/pam.d/login` and `/etc/pam.d/sshd`:
```
#session    optional    pam_motd.so motd=/run/motd.dynamic
#session    optional    pam_motd.so noupdate
```


standby drive mode
------------------
```
hdparm -y /dev/sdX
```
