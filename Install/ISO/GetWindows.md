# Get a Windows Installation ISO Image

This guide will show you how to get a Windows Installation Image.

## Supported Windows Versions

First of all, please check the compatibility list for the Galaxy A25s 5G device [here](../../WindowsCompatibility.md)

## Creating a Windows ISO with UUPDump

### Requirements

- Windows PC for generating the ISO

### Steps

Once you have checked the supported Windows builds for the device, visit the [UUPDump](https://uupdump.net/) website.

- In the main UUPDump page you can either choose from the release types, or by searching for the build number manually.

- Select the target architecture as arm64.

- In the "Choose edition" page it is recommended to only select the Windows Pro edition.

- In the "Select your download options" page it is recommended to leave all default options

- Click the "Create download package" button to download the file needed for the ISO creation

- Extract the downloaded archive and run the provided script.

- After the script finishes, you should have the ISO image in the directory where UUP set scripts are contained.

- Finally, mount the converted ISO image by double-clicking on it 2 times, and remember the mounted disk letter for future reference.
