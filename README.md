# PixelOS Floral vendor base

Independent snapshot of `Nahida-Prjkt/proprietary_vendor_google_coral`,
`lineage-24.0`, at the commit in [UPSTREAM.json](UPSTREAM.json).
The proprietary blob bytes are preserved. The stock camera prebuilt has a
distinct `-coral` build module name and the original executable `stem`, so Soong
does not merge its AIDL V1 dependency graph with the newer AOSP source service.
Its binary path, init configuration, VINTF declaration and shared libraries
remain unchanged. The device extraction list reproduces this module suffix.

Enhanced Face ID and Motion Sense packages are supplied by the standalone
[Face ID](https://github.com/its-hecker/floral-3D-faceid-plugin) and
[Motion Sense](https://github.com/its-hecker/floral-motionsense-plugin) repositories.
Their product files replace the selected legacy packages after base inheritance.
This vendor repository does not contain the integrated Infinity Face HAL repairs,
OsloFeedback APK or custom wallpaper additions.

Radio images use the upstream Git LFS endpoint retained in `.lfsconfig`.
The LFS pointers reference existing upstream objects; these objects are not
uploaded to a new endpoint. Initialize Repo with `--git-lfs`, install Git LFS,
and run `git -C vendor/google/coral lfs pull` before building. Preparation
checksums apply to plugin binaries; the full source validator also checks every
radio image against the SHA-1 already recorded in `Android.mk`.

Follow [Pixelos-localmanifest](https://github.com/its-hecker/Pixelos-localmanifest)
for the source graph, plugin preparation and PixelOS build command.
Google and the respective upstream authors retain their file/license attribution.
