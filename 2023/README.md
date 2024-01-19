# Lenovo Legion Y700 2023 (TB320FC) ROMs

Repo with all the info about the ROMs available for the Lenovo Legion Y700 2023 model

### 🚧 Under Construction 🚧

> [!WARNING]
> Do this at your own risk. This process may brick your devices. You can use [this video](https://www.youtube.com/watch?v=VaCjtUDoqXA) as a reference (it is for the 2022 model) but I am not responsible for any damage caused to your device.

</br>

# 📚 Index

- ⚡ [How to flash unofficial global rom - NEC](#global-rom)
- 🚀 [Acknowledgements](#acknowledgements)

<br>
<br>

## ⚡ How to flash the NEC global ROM (ZUI 15 Android 13): <a name=global-rom></a>

You can check the process in this [video](https://www.youtube.com/watch?v=VaCjtUDoqXA) or in the [XDA post](https://xdaforums.com/t/guide-unbrick-lenovo-y700-tablet.4509297/)

Links:

- [Download ADB from the offical source](https://developer.android.com/studio/releases/platform-tools?hl=es-419)
- [QFIL - Direct Link](https://qpsttool.com/qpst-tool-v2-7-496)
- [Motorola USB Drivers](https://en-us.support.motorola.com/app/answers/detail/a_id/88481/)
- [Qualcomm 9088 Driver](https://androiddatahost.com/nbyn6)
- [NEC Global Rom](https://mirrors.lolinet.com/firmware/nec/NEC_Lavie_Tab_9QHD1/)
- [NEC Global Rom Discussion](https://xdaforums.com/t/y700-2023-nec-lavie-tab-9qhd1.4642255/)

> [!TIP]
> It's probably easier if you just install all the prerequisite software ahead of time, this way you don't fumble around between steps

### Commands:

#### Unlock Device

1. Toggle developer mode by tapping the version in About many times
2. Go to general settings
3. Enable usb debugging
4. Enable oem unlocking
5. Install [motorola drivers](https://en-us.support.motorola.com/app/answers/detail/a_id/88481/)
6. Copy [setup-tools](https://developer.android.com/studio/releases/platform-tools?hl=es-419) after unzipping
7. Set device to fastboot
   - Hold volume up button and then power button until fastboot screen appears
8. Plug in device in on the long side usb
9. Open command prompt in the file explorer
10. Run
```
fastboot devices
```
11. Should see a device listed
12. Run
```
fastboot oem unlock-go
```
13. Device will restart

#### Flash ROM

1. Install [QFIL](https://qpsttool.com/qpst-tool-v2-7-496)
1. Download the [NEC Global Rom](https://mirrors.lolinet.com/firmware/nec/NEC_Lavie_Tab_9QHD1/) and then extract the contents into the `bin` folder
1. Select file system as `UFS`
1. Load the `contents.xml` file into QFIL
1. Programmer file should auto populate to `xbl_s_devprg_ns.melf`
   - Keep it set to this
1. Install the [Qualcomm 9088 Driver](https://androiddatahost.com/nbyn6)
1. Enter EDL mode
   1. Set device to fastboot
      - Hold volume up button and then power button until fastboot screen appears
   1. Use the volume down button to toggle to the shutdown
   1. When device vibrates, quickly hold volume up until the screen goes black
1. Plug in device in on the long side usb
1. Port should appear in QFIL, if not select it using the "Select Port" button
1. Double check everything appears
1. Click "Download Content"
1. Wait for log to say download completed
1. Once completed you can reboot the device

> [!IMPORTANT]
> If you wait too long between entering EDL mode and clicking "Download Content," then it may fail saying something about a Sahara error

<br>
<br>

## ℹ️ GSI ROMs working in the Lenovo Legion Y700 2023: <a name=info></a>
Feel free to add all the info you know about GSI ROMs working on the Lenovo Legion Y700 2023 :)



## 🚀 Acknowledgements <a name=acknowledgements></a>

Thanks to blueberryapple for his help adding the 2023 model info.
