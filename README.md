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

