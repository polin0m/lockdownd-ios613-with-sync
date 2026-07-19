# lockdownd with pc sync

A tool to bypass activation on iOS 6.1.3 while maintaining PC sync functionality.

## Important

This repository contains only the necessary lockdownd file. The full guide is provided below.

The reason I made this repo - [this](https://github.com/iPh0ne4s/iOS-5-6-Hacktivation) lockdownd wasn't working very well with 3utools and at all with iTunes or Finder. I know it works on nearly every device with iOS 5.0-6.1.6 and hacktivates them, but not iPT5, so here we are :)

This lockdownd was made by [sn0wbreeze](https://github.com/iH8sn0w/sn0wbreeze/), iPhone3,2 6.1.3 ipsw, lockdownd taken from ipsw/048-2727-005.dmg/private/var/stash/lockdownd

## Working on

- iPhone 4S 6.1.3 (maybe was working just fine with [this](https://github.com/iPh0ne4s/iOS-5-6-Hacktivation) but i don't really know don't have 4s and can't test)
- iPod Touch 5 6.1.3

## What this file does

- Bypasses activation on devices running iOS 6.1.3
- Preserves Windows-iTunes synchronization (at least iTunes syncs music unlike iPh0ne4s's file, for some reason on macOS it works whenever it wants to)
- Allows using the device without unlocking with Apple ID or using valid SIM

## Repository contents

- lockdownd - the main executable file required for the bypass

# Installation Guide

Prerequisites:
- A device running iOS 6.1.3 (or any iOS 6 i didn't test for now)
- Legacy iOS Kit

Step-by-step instructions:

1. Restore the device with jailbreak\
   Use Legacy iOS Kit to restore your device with a jailbreak enabled.

2. Connect via SSH and SFTP\
   Use Legacy iOS Kit to connect via SSH and SFTP connection to your device.

3. Complete the setup process to the iCloud entering screen

4. Replace the lockdownd file\
   Navigate to the following path on your device:
```
/usr/libexec/lockdownd
```
   Replace the existing file with the lockdownd file from this repository.

6. You DON'T need to remove/move Setup.app\
   The setup process goes as normal after file change

7. Set proper permissions\
   Run the following command via SSH:

```
chmod 755 /usr/libexec/lockdownd
```
   
   OR you can set permissions with SFTP program (e.g. MobaXTerm, FileZilla, etc.)
   
9. Apply changes\
   Either run:
   
```
ldrestart
```
   
   OR simply reboot your device.

## After installation

Your device should now have activation bypassed while retaining the ability to sync with your PC via USB cable.

## Todo list

- Automated script ([феникс активатор ака легаси активатор](https://github.com/maksimka539/legacyactivator/) привет)
- Test more devices idk

## Disclaimer

Use this tool at your own risk. The author is not responsible for any damage to your device.

## Credits

- [Sn0wbreeze](https://github.com/iH8sn0w/sn0wbreeze/) and its developers for the original method
- [iOS 5-6 Hacktivation](https://github.com/iPh0ne4s/iOS-5-6-Hacktivation) for my first bypass and giving me the idea to fix pc sync
