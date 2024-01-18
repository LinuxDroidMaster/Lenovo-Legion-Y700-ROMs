# Lenovo Legion Y700 (TB9707F) ROMs
Repo with all the info about the ROMs available for the Lenovo Legion Y700 2022 model

  
> [!WARNING]  
> Do this at your own risk. This process may brick your devices. You can unbrick using [this method](https://www.youtube.com/watch?v=VaCjtUDoqXA), but I am not responsible for any dagame caused to your device.

</br>

# 📚 Index
* ⚡ [How to flash CN Stock ROM](#stock-rom) -> Unbrick device
* ⚡ [How to sideload the Unofficial ZUI 15 OTA with Android 13](#unofficial-ota)
* ⚡ [How to flash a GSI ROM](#flash-gsi)
* ℹ️ [GSI ROMs working in the Lenovo Legion Y700 2022](#info)
* 🦄 [How to install Magisk (Root tablet)](#magisk)
* 🛠️ Magisk fixes: To Be Done
* 🚀 [Acknowledgements](#acknowledgements)

<br>
<br>
<br>

## ⚡ How to flash the CN stock ROM (ZUI 14 Android 12): <a name=stock-rom></a>
You can check the process in this [video](https://www.youtube.com/watch?v=VaCjtUDoqXA) or in the [XDA post](https://xdaforums.com/t/guide-unbrick-lenovo-y700-tablet.4509297/)

Links: 
* [Download ADB from the offical source](https://developer.android.com/studio/releases/platform-tools?hl=es-419)
* [QFIL - Direct Link](https://qpsttool.com/qpst-tool-v2-7-496)
* [ZUI 14 Stock CN ROM (the one I used in the video)](https://drive.google.com/file/d/1P-8sFTtID0StfhNnf1kkROhzv0wHovun/view?usp=sharing)

Other alternatives: 
* [All the above filles needed in 1 zip file - MEGA](https://mega.nz/file/8XU1kLgT#GVKDjBmvmJgXYfxIUEHSxsxSqLjMDmjixbV-W9GYM9w)
* [Other place with OTAs and stock ROMs - Sourceforge](https://sourceforge.net/projects/lenovo-y700/files/TB9707F/) thanks to [terajima-alc](https://terajima-alc.dev/)

<br>
<br>

## ⚡ How to sideload the Unofficial ZUI 15 OTA (ZUI 15 Android 13): <a name=unofficial-ota></a>
You can check the process in this [video](https://www.youtube.com/watch?v=ZN-D9tlXCTM)

* Prerequisites:  
  * [Download ADB from the offical source](https://developer.android.com/studio/releases/platform-tools?hl=es-419)
  * Having the CN stock ROM already installed on your device, explained here: ⚡ [How to flash CN Stock ROM](#stock-rom)
  * The OTA zip file (in the video description you have the links too):
    * [OTA LINK OPTION 1 - MEGA](https://mega.nz/file/lOUxnIYT#EzAg7reYfJ8oy_82OzCtQFi8XbMdhb_2YYjvVIf1P90)
    * [OTA LINK OPTION 2 - Official Lenovo page](https://mobile-ota-cdn.lenovo.com/firmware/2023111110434825-3726.zip&v=ZN-D9tlXCTM)

### Commands: 
1. Check that your PC recognize the device: 
```
adb devices
```
2. Restart the tablet in recovery mode
```
adb reboot recovery
```
3. In the recovery mode select "Apply update from ADB"
4. Start sideloading the OTA update
```
adb sideload OTA_FILENAME.zip
```
5. Select "Reboot system now" in the recovery mode and the tablet will reboot with the new version of ZUI and Android

<br>
<br>

## ℹ️ GSI ROMs working in the Lenovo Legion Y700 2022: <a name=info></a>
Here you can find a [list with all the GSI ROMs](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list). Below I document the ones that I or someone else has already tested and we know they work fine, but if you have used any other ROM that is not in this list but works, please let me know (open an issue on Github, leave a comment on Youtube or send me a Telegram message). 

Click on any of the ROMs listed here to see how they look and possible issues
* [CRDROID](/roms/crdroid.md)

ROMs tested by other users that I have not yet documented: 
* ElixirRom -> boot loop,
* EvolutionX -> working
* Google AOSP -> working
* LeOS U -> working

<br>
<br>

## ⚡ How to flash a GSI ROM: <a name=flash-gsi></a>

> [!TIP]  
> I have recorded the whole process on this [video](https://www.youtube.com/watch?v=zQ0Guo1v9LA). I recommend you to take a look at it before flashing the ROMs.

* Prerequisites:  
  * [Download ADB from the offical source](https://developer.android.com/studio/releases/platform-tools?hl=es-419)
  * You will need the vbmeta.img file from the stock ROM (I have a link to it in [this video](https://www.youtube.com/watch?v=VaCjtUDoqXA&t=0s))
  * A GSI ROM, in this example we will use [CRDROID](/roms/crdroid.md)


### Commands: 
1. Check that your PC recognize the device: 
```
adb devices
```

2. Reboot to booloader
```
adb reboot bootloader
```

3. Check that your PC recognize the device in fastboot mode
```
fastboot devices
```
> [!IMPORTANT]  
> In case your device is not recognised in fasboot mode (device does not appear when you run the above command): [How to install bootloader interface drivers](https://droidwin.com/install-google-android-bootloader-interface-drivers/)

4. Flash the vbmeta.img file (from the stock ROM or you can get it [here](https://xdaforums.com/t/how-to-install-gsi-with-google-services-on-legion-y700-netflix-problem-solved-games-payment-issue-solved.4651090/) too)
```
fastboot --disable-verification flash vbmeta vbmeta.img
```

5. Reboot on fastboot mode
```
fastboot reboot fastboot
```

6. Check you are using a user space
```
fastboot getvar is-userspace
```

6. Erase system
```
fastboot erase system
```

7. Delete logical partition B
```
fastboot delete-logical-partition product_b
```

8. Flash the GSI ROM, for this example we are using [CRDROID](/roms/crdroid.md)
```
fastboot flash system crDroid-10.0-arm64_bgN-Unofficial.img
```

9. Reboot into recovery
```
fastboot reboot recovery
```

10. Select "Wipe Data / Factory Reset" and confirm
11. Select "Reboot System now"

<br>
<br>

## 🦄 How to install Magisk (Root tablet): <a name=magisk></a>

### Long method: 
Patch your own boot.img. The steps are desribed in the following [post](https://xdaforums.com/t/gsi-rom-install-magisk-with-no-root-on-gsi-rom-dsu-method.4651428/)

### Easy method: 
Video pending (I hope having it for next monday)

* Download patched img and magisk from [here](https://drive.google.com/drive/folders/1E5BsgLwW4Yc_2-ajOklnAVocDODDGs2M)
* Follow the commands below

#### Commands easy method: 
1. Check that your device is detected in ADB
```
adb devices
```
2. Install Magisk apk (you can do it by sending the apk to the device or by using the command below)
```
adb install Magisk.apk
```
3. Reboot to bootlaoder
```
adb reboot bootloader
```
4. Check that your device is detected in fastboot mode
```
fastboot devices
```
5. Flash the patched boot.img
```
fastboot flash boot magiskPatchedBootB.img
```
6. Restart to recovery selecting "Restart recovery" (move up/down with vol+/- and confirm with the lock button)
7. Select "Restar system now"
8. Go to Magisk and reboot the device from there
9. Check that the installation has been carried out correctly
![](/images/magisk/magisk.png)

<br>

## 🚀 Acknowledgements <a name=acknowledgements></a>
Thanks to vicenteMartinezY700 for [this post](https://xdaforums.com/t/how-to-install-gsi-with-google-services-on-legion-y700-netflix-problem-solved-games-payment-issue-solved.4651090/) in XDA about the GSI ROMs and his help testing everything in this tablet. 


