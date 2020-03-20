# Hackintosh-Opencore-Asrock_Z390_Phantom_Gaming_ITX

This is the EFI I am using for my Hackintosh computer. Currently based on Opencore 0.5.7.

## System Specs

CPU: Core i5 9600K
Motherboard: Asrock Z390 Phantom Gaming ITX/AC
RAM: G.Skill Ripjaws V DDR4 3200 16Gx2
Graphics card: Sapphire Radeon Pulse 5500 XT
SSD: Western Digital Black SN750 512GB
Wireless + Bluetooth: BCM94360CS2

## Versions

macOS 10.15.3
Opencore 0.5.7

## What works

Discrete graphics for main display and and iGPU for Sidecar
Sleep and wake
Bluetooth
Wi-Fi
Sound:
- Front panel
- Rear panel
- USB sound card
- Display port sound out
Apple stuff:
- iServices
- Handoff
- Clipboard
- Sidecar

## What doesn't work

Thunderbolt probably doesn't. I don't have a TB3 device for testing. Right now I can use it for USB Type-C charging.

## Notes

I replaced the original Intel wireless card, similar to a process like [this](https://icyleaf.com/images/install-boardcom-module-to-motherboard.jpg).

I will try and keep this repo and Readme updated.
