# local_manifests
Local OnePlus 5(T) device manifests for Ubuntu Touch under Halium 9.

## Instructions
Please check the [Halium documentation](http://docs.halium.org/en/latest/) and [Halium 9 porting notes](https://github.com/ubports/porting-notes/wiki/Halium-9). The basic steps to produce `halium-boot.img` and `system.img` to be used with UBports' Ubuntu Touch rootfs are the following:
```
repo init -u https://github.com/Halium/android.git --platform linux -b halium-9.0 --depth 1
git clone https://github.com/ubports-oneplus5/local_manifests.git -b halium-9.0 .repo/local_manifests
repo sync --no-clone-bundle --no-tags -c -j`nproc`
hybris-patches/apply-patches.sh --mb
source build/envsetup.sh
breakfast <cheeseburger|dumpling>
mka halium-boot systemimage
```
