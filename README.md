# Hackintosh-Opencore-Asrock_Z390_Phantom_Gaming_ITX

This is the EFI I am using for my Hackintosh computer. Currently based on Opencore 0.5.8.

## System Specs

- CPU: Core i5 9600K
- Motherboard: Asrock Z390 Phantom Gaming ITX/AC
- RAM: G.Skill Ripjaws V DDR4 3200 16Gx2
- Graphics card: Sapphire Radeon RX 5500 XT Pulse
- SSD: Western Digital Black SN750 512GB
- Wireless + Bluetooth: BCM94360CS2

## Versions

- macOS 10.15.4
- OpenCore 0.5.8

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

Thunderbolt probably doesn't. I don't have a TB3 device for testing. Right now I can use it for USB Type-C charging.

### Update 5/6/2020:
Added SSDT-TbtOnPch.aml from [fangf2018](https://github.com/fangf2018/ASRock-Z390-Phantom-ITX-OpenCore-Hackintosh). By default this SSDT and IOElectrify.kext are disabled in the config.plist. Enabling them will turn on support for Thunderbolt 3 and USB-C hotplug. However this causes a series of ACPI errors and will slow down boot time. Since I don't use the port on a regular basis I've left them disabled.

## Notes

I replaced the original Intel wireless card, similar to a process like [this](https://icyleaf.com/images/install-boardcom-module-to-motherboard.jpg).

I will try and keep this repo and Readme updated.
