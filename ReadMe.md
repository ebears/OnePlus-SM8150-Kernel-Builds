## OnePlus SM8150 Kernel Builds

Automated weekly releases of the Android kernel with KernelSU, KernelSU Next, and SukiSU Ultra. Check out the [GitHub Actions](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/actions) and [build files](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/tree/main/.github/workflows) for more info.

**ROM:** [YAAP (Yet another AOSP project)](https://github.com/YAAP)\
**Version:** Android 16\
**Kernel:** [yaap/kernel_oneplus_sm8150](https://github.com/yaap/kernel_oneplus_sm8150)\
**Defconfig:** [Galt's Gulch](https://github.com/yaap/kernel_oneplus_sm8150/blob/sixteen/arch/arm64/configs/gulch_defconfig)

---

### Versions:

- #️⃣[KernelSU](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/releases/tag/KernelSU/) - [ℹ️More Info](https://github.com/rsuntk/KernelSU)
- ☯️[KernelSU-Next](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/releases/tag/KernelSU-Next/) - [ℹ️More Info](https://github.com/KernelSU-Next/KernelSU-Next)
- 😼[SukiSU-Ultra](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/releases/tag/SukiSU-Ultra/) - [ℹ️More Info](https://github.com/SukiSU-Ultra/SukiSU-Ultra)

*All versions are for non-GKI kernels since we're working with Linux 4.14 here...*

---

### Technical Info

| Kernel version       |
|----------------------|
| 5.10+ (GKI 2.0)      |
| 4.19 – 5.4 (GKI 1.0) |

The OnePlus-SM8150 Android kernel is based on Linux 4.14, meaning it is non-GKI based. [path_umount.patch](https://github.com/ebears/OnePlus-SM8150-Kernel-Builds/blob/main/path_umount.patch) is applied to the kernel in order to [backport path_umount](https://kernelsu.org/guide/how-to-integrate-for-non-gki.html#how-to-backport-path-umount) for [non-GKI kernels](https://source.android.com/docs/core/architecture/kernel/generic-kernel-image).

---

### My Method

This is no doubt a hacky, work-around way of doing an update. You (and I) should probably find a better way of doing this, but...

I recommend completely uninstalling [Magisk](https://github.com/topjohnwu/Magisk) (and modules) if it's installed.

***If it's your first time flashing and you're NOT rooted:***
- Download the [TWRP](https://twrp.me/Devices/OnePlus/) IMG file for your device (for example, [here](https://dl.twrp.me/guacamolev2/twrp-3.6.2_11-0-guacamolev2.img.html) is a functioning image file for the OnePlus 7 Pro and YAAP).
    - I've personally had better luck using TWRP version 3.6.2 over 3.7.0 and 3.7.1 (probably since 3.6.2 is Android 11 based; YAAP is based on OxygenOS 11.).
    - Opt to use the FBEv2 over FBEv1 (YAAP uses FBEv2; but idk how much this part *really* matters.)
- Put your device in fastboot mode and connect it to another device with adb.
- Boot the TWRP IMG file you downloaded: `fastboot boot <path-to-file>\<twrp-img>`.
- In TWRP, enter adb sideloading mode.
- Flash the kernel (and hope nothing explodes): `adb sideload <path-to-file>\<kernel-zip>`

***If you already have a rooted kernel:***
- Use [KernelFlasher](https://github.com/fatalcoder524/KernelFlasher/releases) to install the zip.

---

### TODO:

- [SusFS](github.com/kutemeikito/susfs4ksu/tree/kernel-4.14) support.
- Pure [APatch](https://github.com/bmax121/APatch) support ([KernelPatch](https://github.com/bmax121/KernelPatch/)).

---

*Builds are only (if ever) tested on a OnePlus 7 Pro.*\
*Mainly for my personal use, so flash at your own risk.*
