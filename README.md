# Lenovo Legion Y700 (TB9707F) ROMs
Repo with all the info about the ROMs available for the Lenovo Legion Y700 2022 model

  
> [!WARNING]  
> Do this at your own risk. This process may brick your devices. You can unbrick using [this method](https://www.youtube.com/watch?v=VaCjtUDoqXA), but I am not responsible for any dagame caused to your device.

</br>

# 📚 Index
* ℹ️ [GSI ROMs working in the Lenovo Legion Y700 2022](#info)
* ⚡ [How to flash a GSI ROM](#flash-gsi)
* How to install Magisk: To Be Done
* 🛠️ Magisk fixes: To Be Done
* 🚀 [Acknowledgements](#acknowledgements)

<br>
<br>
<br>

## ℹ️ GSI ROMs working in the Lenovo Legion Y700 2022: <a name=info></a>
Click on any of the ROMs listed here to see how they look and possible issues
* [CDROID](/roms/cdroid.md)

<br>
<br>

## ⚡ How to flash a GSI ROM: <a name=flash-gsi></a>

> [!TIP]  
> I have recorded the whole process on this [video](https://www.youtube.com/watch?v=zQ0Guo1v9LA). I recommend you to take a look at it before flashing the ROMs.

* Prerequisites:  
  * [Download ADB from the offical source](https://developer.android.com/studio/releases/platform-tools?hl=es-419)
  * You will need the vbmeta.img file from the stock ROM (I have a link to it in [this video](https://www.youtube.com/watch?v=VaCjtUDoqXA&t=0s))
  * A GSI ROM, in this example we will use [CDROID](/roms/cdroid.md)


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
  * In case your device is not recognized in fasboot mode: [How to install bootloader interface drivers](https://droidwin.com/install-google-android-bootloader-interface-drivers/)

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

8. Flash the GSI ROM, for this example we are using [CDROID](/roms/cdroid.md)
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

## 🚀 Acknowledgements <a name=acknowledgements></a>
Thanks to vicenteMartinezY700 for [this post](https://xdaforums.com/t/how-to-install-gsi-with-google-services-on-legion-y700-netflix-problem-solved-games-payment-issue-solved.4651090/) in XDA about the GSI ROMs and his help testing everything in this tablet. 


