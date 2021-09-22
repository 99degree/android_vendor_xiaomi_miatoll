# android_vendor_xiaomi_miatoll
This repo is for use with LineageOS Xiaomi Vayu POCO X3 Pro ROM to reuse by Miatoll.

The procedure is simple, to download latest vayu rom form LineageOS and modify vendor.img then flash all to miatoll device.
It is similar to the Meizu E3 device did. If lengthy procedure is needed, plz refer below for detail:
https://github.com/99degree/android_vendor_meizu_m851q

Procedure:
(1)so first thing first is to unzip the vayu rom
(2)brotli -d *.br && rm *.br
(3)sdat2img vendor.transferlist vendor.new.dat vendor.img
(4)apply above for all img
(5)mount vendor.img /mnt/vendor/
(5)cp android_vendor_xiaomi_miatoll/vendor/* /mnt/vendor/
(6)umount /mnt/vendor/
(7)fastboot reboot fastboot
(8)fastboot flash vendor vendor.img
(9)apply all img as step 8 does.
(10)fastboot reboot recovery
(11)recovery wipe data
(12)reboot and all done.

Note:
the provided fstab.qcom/fstab.default is unencrypted version so /data is not encrypted.
