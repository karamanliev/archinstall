1. boot from usb drive

2. update repo db
```bash
pacman -Sy
```

3. update `archinstall`
```bash
pacman -Sy archinstall
```

4.  Find the fastest mirrors to download from and verify output
```bash
sudo reflector --latest 20 --protocol https --sort rate --save /etc/pacman.d/mirrorlist

cat /etc/pacman.d/mirrorlist
```

6. run `archinstall` with the following config:
```json
{
  "__separator__": null,
  "additional-repositories": [
    "multilib"
  ],
  "archinstall-language": "English",
  "audio_config": {
    "audio": "pipewire"
  },
  "bootloader": "Efistub",
  "config_version": "2.7.2",
  "debug": false,
  "disk_config": {
    "config_type": "default_layout",
    "device_modifications": [
      {
        "device": "/dev/sdc",
        "partitions": [
          {
            "btrfs": [],
            "dev_path": null,
            "flags": [
              "Boot",
              "ESP"
            ],
            "fs_type": "fat32",
            "mount_options": [],
            "mountpoint": "/boot",
            "obj_id": "a181c386-d7ec-4ef8-be4c-b73a1c07263c",
            "size": {
              "sector_size": {
                "unit": "B",
                "value": 512
              },
              "unit": "MiB",
              "value": 512
            },
            "start": {
              "sector_size": {
                "unit": "B",
                "value": 512
              },
              "unit": "MiB",
              "value": 1
            },
            "status": "create",
            "type": "primary"
          },
          {
            "btrfs": [
              {
                "compress": false,
                "mountpoint": "/",
                "name": "@",
                "nodatacow": false
              },
              {
                "compress": false,
                "mountpoint": "/home",
                "name": "@home",
                "nodatacow": false
              },
              {
                "compress": false,
                "mountpoint": "/var/log",
                "name": "@log",
                "nodatacow": false
              },
              {
                "compress": false,
                "mountpoint": "/var/cache/pacman/pkg",
                "name": "@pkg",
                "nodatacow": false
              },
              {
                "compress": false,
                "mountpoint": "/.snapshots",
                "name": "@.snapshots",
                "nodatacow": false
              }
            ],
            "dev_path": null,
            "flags": [],
            "fs_type": "btrfs",
            "mount_options": [
              "compress=zstd"
            ],
            "mountpoint": null,
            "obj_id": "fd836999-ba8b-405b-965b-67beb7e23c7d",
            "size": {
              "sector_size": {
                "unit": "B",
                "value": 512
              },
              "unit": "B",
              "value": 249520381952
            },
            "start": {
              "sector_size": {
                "unit": "B",
                "value": 512
              },
              "unit": "B",
              "value": 537919488
            },
            "status": "create",
            "type": "primary"
          }
        ],
        "wipe": true
      }
    ]
  },
  "disk_encryption": null,
  "hostname": "karamanliev",
  "kernels": [
    "linux"
  ],
  "locale_config": {
    "kb_layout": "us",
    "sys_enc": "UTF-8",
    "sys_lang": "en_US"
  },
  "mirror_config": null,
  "network_config": {
    "type": "nm"
  },
  "no_pkg_lookups": false,
  "ntp": true,
  "offline": false,
  "packages": [
    "git",
    "vim",
    "nano",
    "firefox",
    "neofetch",
    "htop",
    "zsh",
    "telegram-desktop",
    "tldr",
    "man-db",
    "man-pages",
    "timeshift"
  ],
  "parallel downloads": 0,
  "profile_config": {
    "gfx_driver": "Nvidia (proprietary)",
    "greeter": "sddm",
    "profile": {
      "custom_settings": {
        "Gnome": {},
        "Hyprland": {
          "seat_access": "polkit"
        }
      },
      "details": [
        "Gnome",
        "Hyprland"
      ],
      "main": "Desktop"
    }
  },
  "save_config": null,
  "script": "guided",
  "silent": false,
  "skip_ntp": false,
  "skip_version_check": false,
  "swap": true,
  "timezone": "Europe/Sofia",
  "uki": true,
  "version": "2.7.2"
}
```

7. exit chroot and `shutdown now` to remove the usb from PC