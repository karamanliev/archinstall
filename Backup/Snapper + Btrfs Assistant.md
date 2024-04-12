Install packages:
```
yay snapper btrf-assistant
```

Delete `.snapshots/` folder created  by archinstall:
```
sudo umount /.snapshots/
sudo rm - r /.snapshots/
```

Create new config to backup `/`
![[Pasted image 20240411030712.png]]

#TODO: 
- btrfs subvolume delete @.snapshots and rename it to @snapshots
- move /boot to /efi (need to update `/etc/mkinitcpio.d/linux.preset` & `/etc/fstab`), check `efibootmgr` also but I think there's no need to change. Regenerate UKI with `mkinitcpio -P`

#DONE: 
- renamed @.snapshots to @snapshots!
- removed subvolid from `/etc/fstab`

### References:
- [BTRFS snapshots and system rollbacks on Arch Linux](https://www.dwarmstrong.org/btrfs-snapshots-rollbacks/)
- [Arch Wiki BTRFS] (https://wiki.archlinux.org/title/btrfs)
- [Arch Wiki Snapper](https://wiki.archlinux.org/title/Snapper#Suggested_filesystem_layout)