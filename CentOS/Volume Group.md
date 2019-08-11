> 查看Volume Group
```shell
vgdisplay
```

> 修改vgname
```shell
# 改名
vgrename -v oldname newname

# 修改fstab
## vi /etc/fstab
## 将oldname 替换为 newname
# 修改grub
## vi /boot/grub2/grub.cfg
## 将oldname 替换为 newname
# mkinitrd -f -v /boot/initramfs-$(uname -r).img $(uname -r)
# reboot
```