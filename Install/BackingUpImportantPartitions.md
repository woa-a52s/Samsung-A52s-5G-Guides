# Backing up Important Partitions

This guide will help you back up important partitions which are unique to each device.

It is strongly recommended to backup these partitions. If your device bricks or if the partitions get corrupted, without having backups you will
not be able to restore them. Side effects of losing such partitions can include: Loss of IMEI, broken cellular, etc.

Table of Contents:

* [Backing up Important Partitions)](#backing-up-Important-Partitions)
   * [Files/Tools Needed](#filestools-needed)
* [Steps](#steps)
   * [Booting to TWRP](#booting-to-twrp)
   * [Backing up partitions](#backing-up-partitions)
   * [The End](#the-end)

## Files/Tools Needed

- A Galaxy A52s 5G
- UEFI and TWRP images
- SDK platform tools
- A Windows PC to work with the device

## Disclaimers

> [!WARNING]
> - If you see a warning and/or error during the process, it is not normal. Contact us on telegram if you see anything odd, but do not continue or proceed on your own, you will break things further.
>
> - We don't take any responsibility for any damage done to your phone. By following this guide, you agree to take full responsibility of your actions. We have done some testing,
> but this is **STILL IN PREVIEW** and things can go wrong.

**PLEASE READ AND BE SURE TO UNDERSTAND THE ENTIRE GUIDE BEFORE STARTING**

# Steps

## Booting to TWRP

If you don't currently have TWRP flashed on your device, please follow the [Flashing TWRP and UEFI on Galaxy A52s 5G](Flash-UEFI-TWRP.md) guide first.

You can boot to TWRP recovery by doing these steps:

- Power off the device
- Connect your device to the PC with a USB cable
- Hold Power + Volume up buttons



## Backing up partitions

- Open a Terminal / Command prompt on your Windows computer (make sure that ADB executable is on PATH)

- Enter the TWRP shell

```bash
adb shell
```

- Run these commands to back up the partitions

```bash
mkdir backup

dd if=/dev/block/by-name/efs of=/backup/efs.img
dd if=/dev/block/by-name/fsc of=/backup/fsc.img
dd if=/dev/block/by-name/modem of=/backup/modem.img
dd if=/dev/block/by-name/modemst1 of=/backup/modemst1.img
dd if=/dev/block/by-name/modemst2 of=/backup/modemst2.img
dd if=/dev/block/by-name/sec_efs of=/backup/sec_efs.img
dd if=/dev/block/by-name/fsg of=/backup/fsg.img

exit
```

- Now use the adb pull command to fetch the backed up partitions to your computer

```bash
adb pull /backup .
```

The above command will fetch all the backed up partitions from your device to the current directory on your PC.

## The End

And we're done, please keep the backed up partitions in a safe place on your computer.
