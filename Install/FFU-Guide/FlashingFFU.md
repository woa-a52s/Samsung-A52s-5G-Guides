# Flashing a Full Flash Update Image (.FFU) on Galaxy A52s 5G

This guide will help you flash an FFU file containing Windows on your Galaxy A52s 5G.

You will end up with both Android™ and Windows on your Galaxy A52s 5G.

Android™ and Windows will both split the internal storage according to the configuration contained within the FFU file.

Windows FFU images for Galaxy A52s 5G also flash corrected GPT tables to LUNs 1-5. For this reason fixing the GPT manually
is not needed anymore (for avoiding Windows 24H2 issues).


Table of Contents:

* [Flashing a Full Flash Update Image (.FFU) on Galaxy A52s 5G](#flashing-a-full-flash-update-image-ffu-on-galaxy-a52s-5g)
   * [Files/Tools Needed](#filestools-needed)
* [Steps](#steps)
   * [Unlocking the Bootloader](#unlocking-the-bootloader)
   * [Flashing UEFI](#flashing-uefi)
   * [Acquiring all files](#acquiring-all-files)
   * [Booting to UFP mode](#booting-to-ufp-mode)
   * [Flashing the Windows FFU Image](#flashing-the-windows-ffu-image)
   * [Boot Windows](#boot-windows)

## Files/Tools Needed

- A Galaxy A52s 5G
- [An FFU file for your Galaxy A52s 5G](https://nextcloud.ver.lt/s/PLYTQbWoXA3jQ4C)
- [imageutility.zip](../../Files/imageutility.zip)
- A Windows PC to flash the device

## Disclaimers

> [!WARNING]
> - If you see a warning and/or error during the process, it is not normal. Contact us on telegram if you see anything odd, but do not continue or proceed on your own, you will break things further.

> [!IMPORTANT]
> **THIS WILL WIPE ALL YOUR ANDROID™ DATA AND WINDOWS DATA!**
>
> We don't take any responsibility for any damage done to your phone. By following this guide, you agree to take full responsibility of your actions. We have done some testing,
>
> but this is **STILL IN PREVIEW** and things can go wrong.

**PLEASE READ AND BE SURE TO UNDERSTAND THE ENTIRE GUIDE BEFORE STARTING**

# Steps

## Unlocking the Bootloader

If not already done, please first proceed with the [Unlocking the Bootloader](../UnlockingBootloader.md) guide for Galaxy A52s 5G. Come back once you're done. If the device's bootloader is already unlocked, please skip the unlocking section.

## Flashing UEFI

If not already done, please first proceed with the [Flashing TWRP and UEFI](../Flash-UEFI-TWRP.md) guide for Galaxy A52s 5G. Come back once you're done. Keep in mind that you need to have matching UEFI
image and Windows drivers from the same release version.

## Acquiring all files

- Download the imageutility.zip archive and extract it on your computer.
- Once you have acquired an .FFU file, place it in the extracted **imageutility** folder.

## Booting to UFP mode

FFU file needs to be flashed in the UFP mode in UEFI. To enter UFP mode, folow these steps:

- Reboot the phone to UEFI
- When UEFI starts to load, hold the volume up button until this shows up on your device:

<img src="../images/A52s-FFU.png" width="280">

## Flashing the Windows FFU Image

On your Windows computer, open command prompt or terminal in the **imageutility** directory.

Enter this command to flash the Windows FFU file on your device:

```
.\imageutility.exe FlashDevice -Path Samsung_Galaxy_A52s_5G_128GB_HalfSplit-vX.X.X.ffu
```

The FFU flashing process will start. If the flash is successful, you should see this on your device:

<img src="../images/FFU-flash-success.png" width="280">

After a successful flash, reboot the device to Windows with this command:

```
.\imageutility.exe RebootDevice
```

## Boot Windows

If you did everything right, Windows will now boot! Enjoy!

Let Windows set itself up, it is normal for Windows to reboot in the installation process.
