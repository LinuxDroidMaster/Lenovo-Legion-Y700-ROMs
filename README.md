# Lenovo-Legion-Y700-ROMs
Repo with all the info about the ROMs available for the Lenovo Legion Y700 2022 model

  
> [!WARNING]  
> Do this at your own risk. This process may brick your devices. You can unbrick using [this method](https://www.youtube.com/watch?v=VaCjtUDoqXA), but I am not responsible for any dagame caused to your device.

Thanks to vicenteMartinezY700 for [this post](https://xdaforums.com/t/how-to-install-gsi-with-google-services-on-legion-y700-netflix-problem-solved-games-payment-issue-solved.4651090/) in XDA about the GSI ROMs. 


# 1. Steps to flash a GSI ROM: 
> [!CAUTION]
> Work in progress. Do not use yet (I will publish a Video when everything its ready and tested).

Commands in bulk (copied from XDA): 
```
adb devices
adb reboot bootloader
fastboot devices
fastboot --disable-verification flash vbmeta vbmeta.img
fastboot reboot fastboot
fastboot getvar is-userspace
fastboot erase system
fastboot delete-logical-partition product_b
fastboot flash system crDroid\crDroid-10.0-arm64_bgN-Unofficial.img
```

* In case your device is not recognized in fasboot mode: [How to install bootloader interface drivers](https://droidwin.com/install-google-android-bootloader-interface-drivers/)


