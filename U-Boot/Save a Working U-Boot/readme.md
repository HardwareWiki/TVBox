# This explains how to Save & Restore a Workign U-Boot!
https://forum.libreelec.tv/thread/20823-unofficial-le-for-rk356x-rk3328-rk3399-3288-3188/

>**Add u-boot to SD card**
>
>If you have any working system on the SD card that starts normally, you will be able to check the LE. You need to try to replace the u-boot in LE, on the version with a working SD card. You need to perform a few additional steps when preparing an SD card.
>
>1. Remove from working SD card u-boot. This can be done with this command on a Linux PC.
>
>```
>dd if=/dev/<name_you_SD_works_card> of=u-boot-rockpro.img bs=1M count=16
>```
>
>2. Write LE to SD card, configure DTB and replace u-boot with taken from working SD card. U-boot replacement is performed by two commands.
>
>```
>dd if=u-boot-rockpro.img of=/dev/<new_SD_card_LE> conv=fsync bs=1 count=442
>dd if=u-boot-rockpro.img of=/dev/<new_SD_card_LE> conv=fsync bs=512 skip=1 seek=1
>```
>
>After that, you can try running LE on RockPro. The last two commands write a working u-boot and save the existing partition table for the system written to the SD card. By the way, in the same way you can replace u-boot for Armbian system and check the start of any image.
