Delete snap
-----------
`sudo apt purge snapd ubuntu-core-launcher squashfs-tools`


Necessities
-----------
1. `apt install net-tools`

2. sshd
- `apt install openssh-server`
- `systemctl start sshd`


Disable gdm
-----------
```
systemctl set-default multi-user.target
```


Firefox frem deb
----------------

```
sudo add-apt-repository ppa:mozillateam/ppa
apt install firefox-esr
```


Debug packages
--------------
<https://ubuntu.com/server/docs/debug-symbol-packages>


DNS update
----------
update-systemd-resolved
