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
- removed /boot from /dev/sdc2
- basically used this guide to do the rest: - [Arch Linux installation with unified kernel image (UKI), full disk encryption, secure boot, btrfs snapshots, and common setups](https://wiki.archlinux.org/title/User:Bai-Chiang/Arch_Linux_installation_with_unified_kernel_image_(UKI),_full_disk_encryption,_secure_boot,_btrfs_snapshots,_and_common_setups#zram)

### References:
- [BTRFS snapshots and system rollbacks on Arch Linux](https://www.dwarmstrong.org/btrfs-snapshots-rollbacks/)
- [Arch Wiki BTRFS] (https://wiki.archlinux.org/title/btrfs)
- [Arch Wiki Snapper](https://wiki.archlinux.org/title/Snapper#Suggested_filesystem_layout)
- [https://www.dwarmstrong.org/btrfs-snapshots-rollbacks/](https://www.dwarmstrong.org/btrfs-snapshots-rollbacks/)