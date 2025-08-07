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

### TODO:
- [SusFS](github.com/kutemeikito/susfs4ksu/tree/kernel-4.14) support.
- Pure [APatch](https://github.com/bmax121/APatch) support ([KernelPatch](https://github.com/bmax121/KernelPatch/)).

---

***Builds are only (if ever) tested on a OnePlus 7 Pro.***\
***Mainly for my personal use, so flash at your own risk.***
