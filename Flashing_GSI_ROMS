# Flashing GSI ROMs



## Preface
I tried 2 different GSI ROMS, "BestGSI" and "Restless OS".

[https://github.com/amintum/BestGSI](https://github.com/amintum/BestGSI)

[https://github.com/cawilliamson/treble_restlessos](https://github.com/cawilliamson/treble_restlessos)

Restless OS is a fork of Graphene OS; and while it will not give you all of the security features of Graphene OS, it will give you some of the most important ones IMHO. You get a built-in firewall (no need for Shizuku and Shizuwall, AFWall and root, etc.), sandboxed Google Play Services, and the duress pin/password system.

For the full feature set of Graphene OS, you need to have very specific hardware requirements... which most phones do not meet, hence this GSI fork will work for other devices.

When looking for GSI ROMs, look for ones that are ARM64 A/B Partition Style. You can read more here: https://github.com/amintum/BeginnerGuidetoFlashingGSI
*Note: The above guide is a generic guide to flash GSI images. You can (and maybe should) use my guide for the Ulefone Armor 30 Pro, as it contains additional information particular to this phone.*

The guide below gives you some of the steps needed to flash a GSI ROM to the Ulefone Armor 30 Pro. Note: this guide is not entirely complete. It's enough to get a GSI ROM running on the device, but any additional configuration (such as to get all the non-working features working if it's possible) is not something I found yet, nor have instructions for.

Note: I may provide the firmware for the Ulefone Armor 30 Pro later, but I'll have to find a good, reliable place to upload it to for y'all. 
I've had terrible experiences with Mega.NZ. They love screwing people over with all sorts of limitations, so any firmware uploaded there may not be a reliable source for years to come. 
Anyone wanting to share their firmware files should probably consider other cloud storage options. 
It's too bad Ulefone decided to just delete all their firmware from their site. :(



## The Guide

You will need to enable developer mode (tap the build number several times quickly in settings) and enable the ability to unlock the bootloader.

I'd recommend using platform-tools_r34.0.4 on Windows for adb/fastboot. Newer builds have some bugs that cause some commands to give errors.

[https://dl.google.com/android/repository/platform-tools_r34.0.4-windows.zip](https://dl.google.com/android/repository/platform-tools_r34.0.4-windows.zip)

You will need some files from your stock firmware to flash a GSI ROM, or vb-meta/dm-verity will put your phone into a bootload. Of course you will also need your stock firmware for your device, in case things go wrong or you decide to return to stock anyway. Again, I may provide a link for these later... but if you have the stock firmware you may proceed.

Substitute "RestlessOS-arm64-ab-16.0.0-202606230923.img" as needed for your particular GSI ROM.

The codeblocks below provide all the commands for flashing the GSI ROM.

`fastboot flashing unlock`

`fastboot --disable-verity --disable-verification flash vbmeta_a vbmeta.img`

`fastboot --disable-verity --disable-verification flash vbmeta_b vbmeta.img`

`fastboot --disable-verity --disable-verification flash vbmeta_system_a vbmeta_system.img`

`fastboot --disable-verity --disable-verification flash vbmeta_system_b vbmeta_system.img`

`fastboot --disable-verity --disable-verification flash vbmeta_vendor_a vbmeta_vendor.img`

`fastboot --disable-verity --disable-verification flash vbmeta_vendor_b vbmeta_vendor.img`

`fastboot reboot fastboot`

`fastboot delete-logical-partition product_a`

`fastboot delete-logical-partition product_b`

`fastboot flash system_a RestlessOS-arm64-ab-16.0.0-202606230923.img`

`fastboot flash system_b RestlessOS-arm64-ab-16.0.0-202606230923.img`

`fastboot -w`

`fastboot reboot`



### What does not work:

- The 2 Extra Hardware Shortcut Buttons

- The Macro and Nightvision Cameras/IR LEDs

- Full Dual Display Control (The display is mirrored on both sides, with touch controls active on both sides.)

- The Speaker/Notification Ring Light

- Headphone Jack

- WiFi Calling/VOLTE/Dual SIM? (Need more testing.)

- Various Ulefone System Apps (I made a backup with Swift Backup and did a restore on Restless OS. Many of those apps won't work, but some will. This was mostly an attempt to get the above features working; I did not restore/test every app though.)

- Google's fking endless bloatware/spyware! :) (Depending on which GSI ROM you pick OFC, I chose Restless OS which sandboxes Google Play Services. I abhor Google and the fked up decisions they chose to make; bloating Android, all while removing useful features. [https://keepandroidopen.org](https://keepandroidopen.org/))



### *What will never work:*

- Relocking the bootloader. (GSI ROMs require you to unlock the bootloader, and vb-meta/dm-verity will most likely brick your device if you attempt to relock the bootloader! Buy a Pixel I guess... and then mourn the loss of many cool and useful hardware features, as well as your money if you want to have a decent amount of storage! Pixel devices do not have microSD slots, so what you get is what you get - no upgrading storage later... and Google charges a huge premium for more on-device storage. They do this to push you into paying for cloud storage and a more expensive data plan.)
