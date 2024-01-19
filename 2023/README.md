# Lenovo Legion Y700 2023 ROMs

Repo with all the info about the ROMs available for the Lenovo Legion Y700 2022 model

> [!WARNING]
> Do this at your own risk. This process may brick your devices. You can unbrick using [this method](https://www.youtube.com/watch?v=VaCjtUDoqXA), but I am not responsible for any damage caused to your device.

</br>

# 📚 Index

ROMs:

- ⚡ [How to flash unofficial global rom](#global-rom)

<br>

Utilities:

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
1. Go to general settings
1. Enable usb debugging
1. Enable oem unlocking
1. Install [motorola drivers](https://en-us.support.motorola.com/app/answers/detail/a_id/88481/)
1. Copy [setup-tools](https://developer.android.com/studio/releases/platform-tools?hl=es-419) after unzipping
1. Set device to fastboot
   - Hold volume up button and then power button until fastboot screen appears
1. Plug in device in on the long side usb
1. Open command prompt in the file explorer
1. Run `fastboot devices`
1. Should see a device listed
1. Run `fastboot oem unlock-go`
1. Device will restart

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

### 🚧 Under Construction 🚧

## 🚀 Acknowledgements <a name=acknowledgements></a>

Thanks to vicenteMartinezY700 for [this post](https://xdaforums.com/t/how-to-install-gsi-with-google-services-on-legion-y700-netflix-problem-solved-games-payment-issue-solved.4651090/) in XDA about the GSI ROMs and his help testing everything in this tablet.
