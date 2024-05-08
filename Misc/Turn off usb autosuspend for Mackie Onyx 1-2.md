Caused me trouble by turning off sometimes after sleep:
`$ lsusb`:
```
***
Bus 005 Device 011: ID 0a73:001e Mackie Designs Onyx Artist 1-2
***
```

Then add this:
```
# /etc/udev/rules.d/50-usb_power_save.rules
# blacklist for usb autosuspend
ACTION=="add", SUBSYSTEM=="usb", ATTR{idVendor}=="0a73", ATTR{idProduct}=="001e", GOTO="power_usb_rules_end"

ACTION=="add", SUBSYSTEM=="usb", TEST=="power/control", ATTR{power/control}="auto"
LABEL="power_usb_rules_end"
```

This one caused me problems, other thing I tried is adding `usbcore.autosuspend=-1` to kernel commands:
```
# /etc/kernel/cmdline
root=PARTUUID=277934fa-dabb-4194-89d4-28223f482be0 zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs quiet loglevel=3 usbcore.autosuspend=-1 nvidia_drm.modeset=1 nvidia_drm.fbdev=1
```

The second one worked.