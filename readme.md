```bash
sudo apt install -y git python-is-python3
git clone https://github.com/akhilnarang/scripts; cd scripts; sudo bash setup/android_build_env.sh; cd ..; mkdir PE; cd PE
repo init -u https://github.com/PixelExperience/manifest -b fourteen
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

git clone https://github.com/samsung-sm8550-aosp/manifest -b PE-14 .repo/local_manifests
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

. build/envsetup.sh
cd device/samsung/dm3q; ./extract-files.sh; cd ../../..
lunch aosp_dm3q-userdebug
mka bacon
```
