# MiraCLO-OS 1.0 (Android 17) for POCO X7 and Redmi Note 14 Pro 5G (malachite)

MiraCLO-OS 1.0 (Android 17, Liquid Glass) for the POCO X7 and the Redmi Note 14 Pro 5G (codename malachite, MediaTek MT6878 / Dimensity 7300).
First MiraCLO-OS build for these phones. MiraCLO-OS has no MediaTek support upstream, this is our own port. Made by HUNTER[RKJAAT].
Support group: https://t.me/Malachite_Pro

Only for malachite. Check Settings > About phone before flashing. Other Redmi Note 14 or POCO phones are different devices, do not flash this on them.

## Status

Tested: everything we tried works. No known bugs right now. If you find one, tell us in the support group.

Google Play Store and Google Play services are included (see "Google apps" below).

## Download

- ROM package (fastboot): https://t.me/Malachite_Pro/36
- Firmware fix package (OS2.0.208 firmware, needed under the ROM): https://t.me/Malachite_Pro/34
- boot.img, vendor_boot.img, init_boot.img and checksums.txt: in the Releases of this repo.

SHA-256 of the zip: 6a2d43205acc3097de647f0593ebc6870fca6b53ab997c6f9a774c4cf3b3ac7c

## How to install

Bootloader must be unlocked. This wipes your data, take a backup first.

This ROM does not carry its own firmware (preloader, modem, tee, ...). It is built on the OS2.0.208.0.VOOMIXM (Android 15) firmware. **The firmware on the phone must be this one.** If you flash it over another firmware (we tried tested babe), it does not work.


 If the phone is not already on OS2.0.208, flash the firmware first. The package has it, unmodified, from the official Xiaomi OS2.0.208 package:

        bash ./flash_firmware_208.sh

   It checks the phone model and the anti-rollback version first and stops if it is not safe. If you flashed the full official OS2.0.208 fastboot ROM before, you can skip this step.
4. Flash the ROM:

        bash ./flash_miraclo.sh

5. The phone reboots by itself. The first boot takes 2 to 3 minutes.

`flash_miraclo.sh` wipes the phone (data and metadata). The storage is formatted on the first boot, at its full size.



Check your download against `checksums.txt` before flashing.

You do all this at your own risk. We are not responsible for a bricked phone.

## Google apps

Google Play Store, Google Play services and Google Services Framework are built in (from MindTheGapps 17.0.0 arm64). Nothing else from Google is included (no Google app, no Gboard, no TalkBack).

## Things to know

- Updates: for now only the fastboot package. OTA updates from inside the phone do not work yet.
- Window blur is off by default so the control center opens smoothly. The Liquid Glass look stays on. You can turn blur on in Developer options ("Disable window blurs").
- Back gesture sensitivity: Settings > System > Gestures > System navigation > Back sensitivity.


## Source

- MiraCLO-OS: https://github.com/MiraCLO-OS (branch calcite)
- Device tree: https://github.com/MalachitePro/android_device_xiaomi_malachite
- Vendor blobs: https://github.com/MalachitePro/proprietary_vendor_xiaomi_malachite
- Hardware: https://github.com/MalachitePro/android_hardware_xiaomi

## Credits

- MiraCLO-OS team for the ROM, and the AOSPA (Paranoid Android) team it is based on.
- The LineageOS team for the base parts (hardware interfaces, sepolicy).
- MindTheGapps team for the Google apps package.
- The Android 16 (LineageOS 23.2) device tree for malachite is from malachite-project (noamtu123), puhboo, mt6878-devs and cmdr-chara. Thanks to them.
- Android 17 port, fixes and this build: HUNTER[RKJAAT].

## Kernel

Prebuilt Linux 6.1 kernel from malachite-project (GPLv2). Source: https://github.com/malachite-project/kernel_manifest-6.1
