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
