# LineageOS 19.1 For Exynos 7870

Official device manifests and common trees for building LineageOS 19.1 (Android 12L) on Samsung Exynos 7870 devices.

---

## Supported Devices

| Codename | Device |
| :--- | :--- |

| `j7改进` -> `j7velte` | Samsung Galaxy J7 Core / Nxt / Neo (2017) |

---

## How to Build

### 1. Initialize Pixel Expierience Source
```bash
mkdir pe && cd pe
repo init -u https://github.com/PE12-Legacy/manifest -b twelve-plus
```

### 2. Add Local Manifests

```bash
git clone https://github.com/Sideeyecat/android_manifest_samsung_universal7870-common.git -b lineage-19.1 .repo/local_manifests
```


### 3. Sync Repositories
```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune -j16
```

### 4. Apply Platform Patches
If required for your source tree, apply the patches from the `patches/` directory using:
```bash
bash patches/apply_patches.sh
```

### 5. Build
```bash
source build/envsetup.sh
lunch aosp_j7velte-userdebug
m bacon -j16
```

---

## Credits
- @Astrako
- @FlominatorGD
- @Batuhantrkgl
- Exynos7870 Community
