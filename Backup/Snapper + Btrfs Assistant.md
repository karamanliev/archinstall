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
Need to fix problem with double `@snapshots` and `@/.snapshots` subvolumes and remove `subvolid` from volumes

### References:
- [BTRFS snapshots and system rollbacks on Arch Linux](https://www.dwarmstrong.org/btrfs-snapshots-rollbacks/)
- [Arch Wiki BTRFS] (https://wiki.archlinux.org/title/btrfs)
- [Arch Wiki Snapper](https://wiki.archlinux.org/title/Snapper#Suggested_filesystem_layout)