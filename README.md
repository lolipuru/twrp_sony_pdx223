# unified twrp for nagara platform

## Features

Works:

- ADB
- Decryption of /data
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup
- Sdcard

## Partially working
- USB OTG
- Vibration (unable to create path for drivers)

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/sony/pdx223" name="lolipuru/android_twrp_device_sony_pdx223" remote="github" revision="android-12.1" />
```

Finally execute these:

## Note: This twrp only build for 1 IV for now

```
. build/envsetup.sh
lunch twrp_pdx223-eng 
mka recoveryimage
```

To test it:

```
fastboot flash out/target/product/pdx223/recovery.img
```

## Other Sources


## Thanks
- [sekaiacg and YuKongA](https://github.com/YuKongA/device_xiaomi_fuxi_TWRP/) for twrp base
