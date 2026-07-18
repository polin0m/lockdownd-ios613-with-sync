# lockdownd with pc sync

A tool to bypass activation on iOS 6.1.3 while maintaining full PC sync functionality.

## Important

This repository contains only the necessary lockdownd file. The full guide is provided below.

## What this file does

- Bypasses activation on devices running iOS 6.1.3
- Preserves PC synchronization (at least iTunes syncs music unlike iPh0ne4s's file)
- Allows using the device without unlocking with Apple ID or using valid SIM

## Repository contents

- lockdownd - the main executable file required for the bypass

## Installation Guide

Prerequisites:
- A device running iOS 6.1.3 (or any iOS 6 i didn't test for now)
- Legacy iOS Kit installed on your PC

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

## Disclaimer

Use this tool at your own risk. The author is not responsible for any damage to your device.

## Credits

- [Sn0wbreeze](https://github.com/iH8sn0w/sn0wbreeze/) and its developers for the original method
- [iOS 5-6 Hacktivation](https://github.com/iPh0ne4s/iOS-5-6-Hacktivation) for my first bypass and giving me the idea to fix pc sync
