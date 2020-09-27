# Disclaimer
Do not flash it on your personal phone as it may formate all your data or reset settings or may put you in an unwanted trouble.

These roots are only for specific versions of android and for specific devices.
## Root Images
In this directory we have placed root images which we have used for our target devices (Nexus5, Nexus 6p, Nexus 5x)

### How to root a devices
To root your device, you have to download zip file to your local system and then extract it.

Now move your working directory to the extracted image directory.

Now unlock OEM in your developers option to flash root image.

then reboot your device in the bootloader mode by running:
```
$ adb reboot bootloader
```
now unlock bootloader by running:
```
$ fastboot oem unlock
```
If you have a newer Nexus, such as the Nexus 5X or 6P, the command will be slightly different:
```
$ fastboot flashing unlock
```
Here you have to select Yes and then go back to bootloader mode.

Now its time to flash root on your device by running:
```
$ chmod a+x root-linux.sh
$ ./root-linux.sh
Press enter when it requires
```
when all set then reboot you device:
```
$ fastboot reboot
```
