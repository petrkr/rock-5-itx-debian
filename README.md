# Radxa Rock 5 ITX Debian 13

How to install native Debian 13 on Rock 5 ITX on NVMe with RAID and UEFI support.


## Preparation

 - Flash SPI to EDK2 UEFI BIOS
   - You can do that from Armbian on SD card or oficial Desktop KDE system
   - download SPI image for Rock 5 ITX
   - flash it by using dd if=image.img of=/dev/mtdblock0 (TODO: check right command)

 - Download ARM64 Debian 13 ISO and put it somewhere Flash/CD/NanoKVM/RpiKVM
 - in time of writing NanoKVM HID with ISO does not works in ACPI/UEFI mode, use native keyboard or use native Flash drive and then use NanoKVM in HID-Only mode
 - Switch in UEFI firmware to ACPI only mode, because in time of writing mainline kernel does not supports DTD or Both

## Instalation
 - Boot from ISO (or flash)
 - Install debian 13 as you wish
 - ....TODO about vendor kernel....

 - Add armbian sources, it contains vendor kernel
   - deb [signed-by=/usr/share/keyrings/armbian-archive-keyring.gpg] https://repo.armbian.com/apt trixie main
 - create /etc/armbian-grub-with-dtb with payload BOOT_FDT_FILE=rockchip/rk3588-rock-5-itx.dtb


## GRUB
 - install new linux discovery with DTB support
 - wget https://raw.githubusercontent.com/armbian/build/refs/heads/main/packages/blobs/grub/09_linux_with_dtb.sh
 - remove old 10_linux and 20_linux_xen
 - create kernel post install hook
 - manually run hook with actuall kernel version


## Known problems
 - in ACPI mode internal eMMC (talking about ITX+) is not visible
 - Keyboard of NanoKVM in multimode does not work, you must use HID-Only mode
 - Mainline kernel DOES not have drivers for GPU, so MMP does not works (at jellyfin for example)

