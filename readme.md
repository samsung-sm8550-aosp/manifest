```bash
repo init -u https://github.com/PixelExperience/manifest -b fourteen
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

git clone https://github.com/samsung-sm8550-aosp/manifest -b PE-14 .repo/local_manifests
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

. build/envsetup.sh
lunch aosp_dm3q-userdebug
mka bacon
```