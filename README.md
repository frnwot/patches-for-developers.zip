# Android 16 BPF Patch Set

This repository contains a collection of patches intended for Android 16 (AOSP U) custom ROM builds, focused on **BPF, SELinux compatibility, linker config**, and **device-specific fixes** for smoother in-kernel integration.

## 📁 Patch Structure

Patches are organized by project path, following AOSP conventions. Each folder corresponds to a specific AOSP module:



## 🧩 Included Highlights

Here are a few key patches included:

- `DeviceLock`: Avoid crashes when `DeviceLockManager` is missing.
- `LinkerConfig`: Disable vndklite handling for compatibility.
- `SELinux`: Multiple patches to:
  - Allow mismatched exFAT genfscon
  - Accept RCS service conflicts
  - Allow unknown SELinux classes (common in Moto devices)
  - Fix secilc issues and conflicting SEPolicy rules

## 🛠️ Usage

To apply these patches in your ROM tree:

```bash
cd /path/to/your/aosp/root
unzip patches-for-developers.zip -d ./patches
find ./patches -name '*.patch' | while read patch; do
    echo "Applying $patch"
    patch -p1 < "$patch"
done
# patches-for-developers.zip
