# OnePlus SM8150 Kernel Builds

**ROM:** [YAAP (Yet another AOSP project)](https://mirror.codebucket.de/yaap)\
**Version:** Android 16\
**Kernel:** [yaap/kernel_oneplus_sm8150](https://github.com/yaap/kernel_oneplus_sm8150)\
**Defconfig:** [Gulch](https://github.com/yaap/kernel_oneplus_sm8150/blob/sixteen/arch/arm64/configs/gulch_defconfig)

Releases are [AnyKernel3](https://github.com/osm0sis/AnyKernel3) ZIPs. Check out the [actions](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/actions) and [workflow files](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/tree/main/.github/workflows) for details.

## Versions

- #️⃣[KernelSU](https://github.com/rsuntk/KernelSU)
    - Including 🕵️‍♀️[SusFS v1.5.5](https://gitlab.com/simonpunk/susfs4ksu/-/tree/kernel-4.14)
    - Also includes the older, non-forked [version 0.9.5](https://github.com/tiann/KernelSU/tree/v0.9.5) with 🕵️‍♀️SusFS
- ☯️[KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)
- 😼[SukiSU-Ultra](https://github.com/SukiSU-Ultra/SukiSU-Ultra)

Kernel downloads are found under [releases](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/releases).

## Technical Info

| Kernel version       |
|----------------------|
| 5.10+ (GKI 2.0)      |
| 4.19 – 5.4 (GKI 1.0) |

The OnePlus-SM8150 Android kernel is based on Linux 4.14, meaning it is non-GKI based.\
The [path_umount.patch](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/blob/main/path_umount.patch) file is applied to the kernel in order to [backport path_umount](https://kernelsu.org/guide/how-to-integrate-for-non-gki.html#how-to-backport-path-umount) for [non-GKI kernels](https://source.android.com/docs/core/architecture/kernel/generic-kernel-image).

## Install

⚠️⚠️⚠️**WARNING**\
This is no doubt a workaround to unofficially flash a kernel. Follow and install at your own risk.

*I recommend completely uninstalling [Magisk](https://github.com/topjohnwu/Magisk) if it's installed.*

***If your kernel is NOT rooted:***
1) On a device capable and connected to USB adb, [download the TWRP IMG file for your model](https://twrp.me/Devices/OnePlus).
    - Use TWRP version 3.6.2 (YAAP is based on OxygenOS 11)
    - Pick FBEv2 (YAAP uses FBEv2)
    - Example: [twrp-3.6.2_11-0-guacamolev2.img](https://dl.twrp.me/guacamolev2/twrp-3.6.2_11-0-guacamolev2.img.html) is the IMG file for YAAP on OnePlus 7 Pro devices.
2) Reboot to fastboot: `adb reboot bootloader`
3) Boot TWRP: `fastboot boot <path-to-file>\<twrp.img>`
    - This will temporarily boot TWRP as an alternative recovery.
        - Do not Flash Current TWRP.
    - Default recovery is not possible since the files are unsigned.
        - ~~[Lineage Recovery](https://download.lineageos.org/devices/guacamole/builds) (boot.img) also probably works in place of TWRP~~
            - Actually, I am second guessing this since Lineage is based on OOS 12.
4) From recovery, enter adb sideloading mode.
5) Flash the kernel (and hope nothing explodes): `adb sideload <path-to-file>\<kernel.zip>`

***If you already have a rooted kernel:***
1) Use [capntrips/KernelFlasher](https://github.com/capntrips/KernelFlasher) (or [fatalcoder524/KernelFlasher](https://github.com/fatalcoder524/KernelFlasher)) to install as an AK3 ZIP.

## TODO

- ~~[SusFS](https://gitlab.com/simonpunk/susfs4ksu/-/tree/kernel-4.14) support.~~
    - ~~Update SusFS to 1.5.5.~~
    - ~~SusFS with [rsuntk/KernelSU](https://github.com/rsuntk/KernelSU).~~
    - Dare to smash susfs and KSU-Next/SukiSU together.
- Pure [APatch](https://github.com/bmax121/APatch)/KPM support ([KernelPatch](https://github.com/bmax121/KernelPatch)).
- Fix release/tag mess.
- Refine workflows.

---

*Builds are only (if ever) tested on a OnePlus 7 Pro.*\
*Mainly for my personal use, so flash at your own risk.*
