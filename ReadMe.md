# OnePlus SM8150 Kernel Builds

**ROM:** [YAAP (Yet another AOSP project)](https://yaaprom.org)\
**Version:** Android 16\
**Kernel:** [yaap/kernel_oneplus_sm8150 (linux-4.14/non-gki)](https://github.com/yaap/kernel_oneplus_sm8150)\
**Defconfig:** [Gulch](https://github.com/yaap/kernel_oneplus_sm8150/blob/sixteen/arch/arm64/configs/gulch_defconfig)

Releases are [AnyKernel3](https://github.com/osm0sis/AnyKernel3) ZIPs. Check out the [actions](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/actions) and [workflow file](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/tree/main/.github/workflows) for details.

### Versions

| ℹ️KernelSU version                                                | 🕵️‍♀️Includes a SusFS version? |
| --- | --- |
| #️⃣[KernelSU-Rissu](https://github.com/rsuntk/KernelSU)            | ✅                          |
| ☯️[KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next) | ✅                          |
| 😼[SukiSU-Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra)    | 🚫                          |

Kernel downloads are found under [releases](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/releases).

---
### Install

⚠️***WARNING***⚠️\
Flash at your own risk.

*Completely uninstall [topjohnwu/Magisk](https://github.com/topjohnwu/Magisk) if it's installed.*

**🖥️📱If your kernel is NOT rooted:**
1) On a device capable and connected to USB adb, [download the TWRP IMG file for your model](https://twrp.me/Devices/OnePlus).
    - Use TWRP version 3.6.2 (YAAP is based on OxygenOS 11).
    - Pick FBEv2 (YAAP uses FBEv2).
    - Example: [twrp-3.6.2_11-0-guacamolev2.img](https://dl.twrp.me/guacamolev2/twrp-3.6.2_11-0-guacamolev2.img.html) is the IMG file for YAAP on OnePlus 7 Pro devices.
2) Reboot to fastboot: `adb reboot bootloader`.
3) Boot TWRP: `fastboot boot <path-to-file>\<twrp.img>`.
    - This temporarily boots TWRP as an alternative recovery since we cannot install unsigned files with YAAP recovery.
4) From recovery, enter adb sideloading mode.
5) Flash the kernel: `adb sideload <path-to-file>\<kernel.zip>`.
6) Reboot.

**📱If you already have a rooted kernel:**
1) Use [capntrips/KernelFlasher](https://github.com/capntrips/KernelFlasher) (or the slightly more functional fork: [fatalcoder524/KernelFlasher](https://github.com/fatalcoder524/KernelFlasher)) to install as an AK3 ZIP.
    - [libxzr/HorizonKernelFlasher](https://github.com/libxzr/HorizonKernelFlasher) may be more reliable.
        - Keep an eye on [CRZX1337/HorizonRevamped](https://github.com/CRZX1337/HorizonRevamped).
2) Reboot.

**📱OTA System Updates WITH a rooted already kernel installed:**
1) Download and install the OTA update, but do **not** reboot.
2) Switch apps to your installed kernel flasher of choice.
3) Install the kernel ZIP file on the partition that is **not** currently being used.
4) Switch apps back to the OTA update and reboot.

---
##### TO-DO

- ~~Try SukiSU Ultra with SusFS.~~
    - WIP.
- Manually backport new SuSFS versions.
- Pure [APatch](https://github.com/bmax121/APatch)/KPM supported kernel ([KernelPatch](https://github.com/bmax121/KernelPatch)).
- [Mountify](https://github.com/backslashxx/mountify) support.

---

*Builds are probably **untested**.*\
*Mainly for my personal use, so flash at your own risk.*
