# ImmortalWrt X30 Builder

Automated ImmortalWrt stable-release builds for the TOTOLINK X30 router on the MediaTek Filogic target.

This repository builds a custom ImmortalWrt image for the TOTOLINK X30 by combining:

- the official ImmortalWrt stable release
- a pinned TOTOLINK X30 board-support patch
- a TOTOLINK X30 FIT sysupgrade compatibility patch
- a reproducible GitHub Actions workflow
- a minimal device-specific ImmortalWrt configuration

The goal is to provide updateable ImmortalWrt `sysupgrade.bin` images for the TOTOLINK X30 without requiring users to compile ImmortalWrt locally.

## Target device

**Device:** TOTOLINK X30  
**Target:** MediaTek Filogic  
**Architecture:** ARM64 / MediaTek MT7981

## ImmortalWrt version

The GitHub Actions workflow automatically detects the latest stable ImmortalWrt release in the `25.12.x` series.

For routine firmware upgrades, **do not flash**:

- `preloader.bin`
- `bl31-uboot.fip`

These files are bootloader-related and are not required for a normal sysupgrade.

The `initramfs-recovery.bin` image is intended for recovery or RAM boot scenarios, not routine upgrades.
