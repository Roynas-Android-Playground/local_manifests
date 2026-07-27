## A30 local manifest for LineageOS 24.0

Initialize the platform tree:

```sh
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone -b lineage-24.0 \
    https://github.com/Roynas-Android-Playground/local_manifests.git \
    .repo/local_manifests
repo sync
```

Build the user variant:

```sh
source build/envsetup.sh
breakfast a30 user
mka bacon
```

The A30 kernel is intentionally pinned to `EurekaV3`; all other Royna projects
track `lineage-24.0`.
