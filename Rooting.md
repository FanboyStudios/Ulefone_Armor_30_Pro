# Rooting



## Preface



The guide below gives you some of the steps needed to flash Magisk Root to the Ulefone Armor 30 Pro. 

This guide assumes you're on stock firmware, but the steps are similar for rooting a GSI ROM. 
If you're already on a GSI ROM, you can start from step 5.

Note: I may provide the firmware for the Ulefone Armor 30 Pro later, but I'll have to find a good, reliable place to upload it to for y'all. 
I've had terrible experiences with Mega.NZ. They love screwing people over with all sorts of limitations, so any firmware uploaded there may not be a reliable source for years to come. 
Anyone wanting to share their firmware files should probably consider other cloud storage options. 
It's too bad Ulefone decided to just delete all their firmware from their site. :(



## The Guide

1. Enable Developer Options. Go to Settings > About Device. Tap the Build Number quickly serveral times until you see a popup saying you're a developer.

2. Open Developer Options. Go to System > Developer Options. Enable USB Debugging (this enables usage of ADB) and OEM Unlocking (the enables the ability to unlock the bootloader).

3. Download the Android Platform Tools on your PC.

I'd recommend using platform-tools_r34.0.4 on Windows for adb/fastboot. Newer builds have some bugs that cause some commands to give errors.

[https://dl.google.com/android/repository/platform-tools_r34.0.4-windows.zip](https://dl.google.com/android/repository/platform-tools_r34.0.4-windows.zip)

Extract the platform tools and place them in C:\Windows.

4. Download the Stock Firmware for your phone. Extract it somewhere safe, you can use PeaZip or 7zip for this.

You will need some files (namely init_boot.img) from your stock firmware to flash Magisk. 

*Of course you will also need your stock firmware for your device, in case things go wrong or you decide to return to stock anyway. 
Again, I may provide a link for these later... but if you have the stock firmware you may proceed.*

5. Copy the init_boot.img from your extracted firmware to your Phone/microSD Card.

6. Download and install the Magisk App. You can find it here: https://github.com/topjohnwu/Magisk

7. Open the Magisk App and tap "Install" next to "Magisk", then tap "Select and patch a file". Patch your init_boot.img.

8. Copy the "magisk_patched-init_boot.img" to your PC. You'll find it in your phone's internal storage download folder. 

*It will have a different name with "magisk" in it, but you can rename it after you copy it.* 
*For example: renaming it to "UlefoneArmor30Pro-MagiskPatched-Stock-init_boot.img" (without quotations) might be a good idea; to help you keep track of it, if you have multiple devices/several boot images.*

9. Run the following commands in "Command Prompt" on your PC, accepting the ADB prompt if it shows up. 

*Use the "cd" command to navigate to the proper directory in command prompt. The below command is just an example.* 

`cd C:\Users\Your Username Here\Downloads\A700A5TA_VOTA.GQU.Ulefone.HB.FHJ.LVQGZ1LWQL.20260129.V3.03`

Navigate the the directory you placed your "magisk_patched-init_boot.img" in.

Substitute "magisk_patched-init_boot.img" in the commands as needed for your Magisk Patched Boot Image.

`adb reboot bootloader`

`fastboot flashing unlock`

`fastboot flash init_boot_a magisk_patched-init_boot.img`

`fastboot flash init_boot_b magisk_patched-init_boot.img`

`fastboot reboot`

10. Open the Magisk App, tap "Install" next to "Magisk", then tap "Direct Install (Recommended) and "Let's Go". Reboot and you're device will be rooted.



### *What will never work:*

- Relocking the bootloader. (Flashing anything other than stock will most likely brick your device if you attempt to relock the bootloader! Buy a Pixel I guess... and then mourn the loss of many cool and useful hardware features, as well as your money if you want to have a decent amount of storage! Pixel devices do not have microSD slots, so what you get is what you get - no upgrading storage later... and Google charges a huge premium for more on-device storage. They do this to push you into paying for cloud storage and a more expensive data plan.)
