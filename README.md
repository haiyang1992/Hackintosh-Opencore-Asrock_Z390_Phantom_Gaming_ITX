# Hackintosh-Opencore-Asrock_Z390_Phantom_Gaming_ITX

This is the EFI I am using for my Hackintosh computer. Currently based on Opencore 0.7.1.

## System Specs

- CPU: Core i5 9600K
- Motherboard: Asrock Z390 Phantom Gaming ITX/AC
- RAM: G.Skill Ripjaws V DDR4 3200 16Gx2
- Graphics card: Gigabyte Radeon RX 5700 XT Gaming OC
- SSD: Western Digital Black SN750 512GB
- Wireless + Bluetooth: BCM94360CS2

## Versions

- macOS 11.4 Big Sur
- OpenCore 0.7.1

## What works

- Discrete graphics for main display and and iGPU for accelerating
- Sleep and wake
- Bluetooth
- Wi-Fi
- Ethernet
- Sound:
  - Front panel
  - Rear panel
  - USB sound card
  - Display port sound out
- Apple stuff:
  - AirDrop
  - iMessage and FaceTime
  - Handoff
  - Instant Hotspot
  - Universal Clipboard
  - Sidecar
  - Continuity Camera

## What doesn't work

Thunderbolt 3 is finicky. See below.

### Update 2/2/2021
The upgrade to Big Sur was smooth. Although sometimes I will get a blackscreen followed by a kernel panic and system reboot.
This seems to be a bug with Apple's Navi GPU driver and not with WEG or Opencore.

### Update 6/17/2020:
Following the blog post from [fangf2018](https://fangf.cc/2020/05/19/TB3/), the Thunderbolt 3 controller is able to
show up in System Informations. USB-C also works. This involves 1) flashing the BIOS to a specific version, which is
found from a [thread](https://www.tonymacx86.com/threads/success-asrock-z390-phantom-gaming-itx-tb3-igpu-mojave-sff-build.277418/page-81)
on tonymacx86.com and 2) upgrading the Thunderbolt firmware under Windows.

However this method currently has two problems. Booting Windows from Opencore will result in a BSOD with an ACPI error.
This also breaks sleep under macOS. The computer wakes up into a black screen and upon a hard reset a kernel panic
error is generated. This seems to be caused by a bug in the provided `SSDT-TbtOnPch.aml` and AMD Navi graphics cards.
To test out this functionality make sure to enable both `SSDT-TbtOnPch.aml` and `SSDT-DTPG.aml`, disable `SSDT-USBC.aml`
and follow the instructions in the above link to flash the BIOS and firmware.

~~### Update 5/6/2020:~~
~~Added SSDT-TbtOnPch.aml from [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh).
By default this SSDT and IOElectrify.kext are disabled in the config.plist.
Enabling them will turn on support for Thunderbolt 3 and USB-C hotplug.
However this causes a series of ACPI errors and will slow down boot time.
Since I don't use the port on a regular basis I've left them disabled.~~

## Notes

I replaced the original Intel wireless card, similar to a process like [this](https://icyleaf.com/images/install-boardcom-module-to-motherboard.jpg).

I will try and keep this repo and Readme updated.
