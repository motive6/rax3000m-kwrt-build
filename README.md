# RAX3000M NAND Kwrt Build

Private reproducible ImageBuilder project for:

- Device: CMCC RAX3000M NAND
- Target: `mediatek/filogic`
- Source builder: Kwrt 25.12 ImageBuilder
- OpenClash: local `luci-app-openclash_1.0.0-1_all.ipk`
- Kernel: ARM64 Mihomo Ninja UPX build

The build produces a sysupgrade image and does not include or modify
bootloader/preloader/FIP images.

## Layout

- `custom/`: local OpenClash IPK
- `files/`: persistent core, regions and OpenClash start patch
- `config/packages.list`: packages added to the target profile
- `.github/workflows/build.yml`: GitHub Actions build

## Safety

Only use the generated `*sysupgrade.bin` from the OpenWrt/LuCI upgrade page.
Do not flash `bl31`, `fip`, `preloader`, or `factory` images unless recovering
with the appropriate hardware-specific procedure.
