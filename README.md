## A30 local manifest for Pixelify-AOSP Android 17

Initialize the platform tree:

```sh
repo init -u https://github.com/Pixelify-AOSP/platform_manifest -b 17 --git-lfs
git clone -b lineage-24.0 \
    https://github.com/Roynas-Android-Playground/local_manifests.git \
    .repo/local_manifests
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune
```

Build the user variant:

```sh
source build/envsetup.sh
lunch lineage_a30-cp2a-user
mka bacon
```

The A30 kernel is intentionally pinned to `EurekaV3`; all other Royna projects
track `lineage-24.0`.
