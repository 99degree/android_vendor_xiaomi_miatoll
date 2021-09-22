# android_vendor_xiaomi_miatoll
This repo is for use with LineageOS Xiaomi Vayu POCO X3 Pro ROM to reuse by Miatoll. This is for once LineageOS for miatoll build is not available yet.

The procedure is simple, to download latest vayu rom form LineageOS and modify vendor.img then flash all except boot and dtbo to miatoll device.
It is similar to the Meizu E3 device did. If lengthy procedure is needed, plz refer below for detail:
https://github.com/99degree/android_vendor_meizu_m851q

Procedure:
```
(1)so first thing first is to unzip the vayu rom
(2)brotli -d *.br && rm *.br
(3)sdat2img vendor.transferlist vendor.new.dat vendor.img
(4)apply above for all img
(5)mount vendor.img /mnt/vendor/
(6)cp android_vendor_xiaomi_miatoll/vendor/* /mnt/vendor/
(7)umount /mnt/vendor/
(8)fastboot reboot fastboot
(9)fastboot flash vendor vendor.img
(10)apply all img as step 8 does.
(11)fastboot reboot recovery
(12)recovery wipe data
(13)reboot and all done.
```
Note:
the provided fstab.qcom/fstab.default is unencrypted version so /data is not encrypted.
It is very easy to modify to enable encryption, it is uncomment(remove # sign) the "#/data..." line and toggle the another one else.

And there are three choice for the custom kernel.
```
(1)Look at LineageOS https://github.com/LineageOS/android_kernel_xiaomi_sm6250 repo and build with clang.
(2)Look at my CAF repo at https://github.com/99degree/android_kernel_xiaomi_curtana.git
(3)Download a test-build at below.
```
Procedure for custom kernel:
```
(1)Download the boot.img below
(2)fastboot reboot bootloader
(3)fastboot flash boot boot.img
(4)fastboot erase dtbo
(5)fastboot reboot revovery
(6)wipe data and reboot
```

The custom kernel is (not yet ready) provided in release branch.
https://github.com/99degree/android_vendor_xiaomi_miatoll/releases

