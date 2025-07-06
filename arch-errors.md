# Errors Encounter in Arch

## Nvidia Firmaware Error

This error happened in doing a pacman update

```
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad103 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad104 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad106 exists in filesystem
linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad107 exists in filesystem
```

Run this command to update 

```
# pacman -Rdd linux-firmware
# pacman -Syu linux-firmware
```
