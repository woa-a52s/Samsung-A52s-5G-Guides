# Uninstall Windows and revert your Galaxy A52s 5G to stock

This guide will help you go back to a normal Galaxy A52s 5G, with Android™ only.

Just like you had it before installing Windows.

Android™ will have access to the whole memory back again.

Your data will be erased, please make backups if you need it before proceeding!

This guide works if you haven't broke anything else in the meantime.

If you broke anything, this guide wont help you and will likely make things worse.

Contact us instead for help!

## Files/Tools Needed

- TWRP image
- Stock Android boot.img, or a backup of it

## Disclaimers

> [!IMPORTANT]
> **THIS WILL WIPE ALL YOUR ANDROID™ DATA**
>
> We don't take any responsibility for any damage done to your phone. By following this guide, you agree to take full responsibility of your actions. We have done some testing,
>
> but this is **STILL IN PREVIEW** and things can go wrong.

**PLEASE READ AND BE SURE TO UNDERSTAND THE ENTIRE GUIDE BEFORE STARTING**

If you caused modifications to Android™ system partitions and are not knowingly using Custom Trusted Boot certificates or do not know what we're talking about here but flashed a dual boot image onto your device, you need to revert this. Please see the dual boot guide for assistance first and foremost. Otherwise below's steps will brick your device.

# Steps

## Acquiring all files

[SDK Platform Tools](https://developer.android.com/tools/releases/platform-tools)

This guide assumes the target device already has TWRP recovery flashed. If needed, please consult the [Flashing TWRP and UEFI](../Flash-UEFI-TWRP.md) guide for flashing TWRP.

If the Android boot image backup was not done prior to installing Windows, a stock boot image will need to be extracted from the device firmware.

To acquire a stock boot image, please download the Galaxy A52s 5G stock AP firmware tarball. You can achieve this using websites like [samfw.com](https://samfw.com)

## Restoring the partition table

- Enter the TWRP recovery environment by holding the volume up and power buttons on the device (with USB cable plugged in)

- Either in adb shell, or in the TWRP recovery UI terminal enter this command:

```batch
restore-gpt
```

The following command will flash the stock LUN0 GPT table which will restore all partitions and the GPT table to OEM's.

- Format userdata partition to F2FS in TWRP menu: Wipe > Format Data > yes

## Restoring boot

**Option 1**

If you have made a backup of the boot image to an SD Card with TWRP, simply use the "Restore" feature of the custom recovery.

**Option 2**

If you have made a backup of the boot image on your computer:

Make sure that either adb is on PATH in your terminal, or you are in the same directory where adb.exe exists.

Open the command prompt on your PC and execute the following command to push the backed up boot image to the device:

```batch
adb push C:\Path\To\boot.img /sdcard
```

After pushing the file, in TWRP recovery menu open the "Install" page, at the bottom-right corner press the "Image" button,
find boot.img file in the /sdcard directory and flash it to `Boot` slot.

**Option 3**

If you don't have an Android boot image backup, download stock Galaxy A52s 5G AP firmware tarball (from the same firmware build you currently have!) from [samfw.com](https://samfw.com).

Use compression utilities like 7-zip or WinRAR to extract the boot.img file from the AP .tar.md5 archive.

Then consult the "Option 2" boot image flashing process detailed above.
