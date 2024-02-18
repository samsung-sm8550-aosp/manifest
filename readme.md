repo init -u https://github.com/Evolution-X/manifest -b udc
git clone https://github.com/samsung-sm8550-aosp/manifest -b main .repo/local_manifests
repo sync

export USE_CCACHE=1
export CCACHE_EXEC=/usr/bin/ccache

source build/envsetup.sh

breakfast lineage_dm3q-userdebug
croot
brunch lineage_dm3q-userdebug