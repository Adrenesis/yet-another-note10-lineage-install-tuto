# yet-another-note10-lineage-install-tuto
Install tuto for Lineage 18.1 on Note 10 (tested on N970F)


#N970F LineageOS 18.1 install note WITH ROOT#

(this post cost 15 hours of research starting from 2021/05/30 04:00 AM GMT+02:00 so its in context)

##DISCLAIMER: ##

NOT legally responsible, but STILL **morally** responsible of any blablabla I can put in this tuto

Warranty void and all that, you know the stuff

And more seriously, **TAKE YOUR TIME, DON'T PUT DEADLINES ON YOURSELF, EAT, SLEEP, DRINK WELL WHILE DOING THIS, THIS REQUIRES *PATIENCE* TO MAKE IT WORK, IF ANY SALT, DO A BREAK AND REEEAAAD TUTOS**

BEFORE YOU START ANY OF THAT:
-Save EFS to avoid accidental IMEI lost (or maybe loose your IMEI)
-***Unlock bootloader !!!*** (or brick your hardware)

todo: add the actual steps to do that

##Preface:##
A little attention to detail, that you may need to understand even if you never seen it
When using Android 10 and less on Note 10 (on the N970F at least)
the bootloader is kind of glitched

Android 10- Note 10 unlocked bootloader screens:
- "GALAXY NOTE 10" Screen
- A splash screens that ask for a power button press
- "GALAXY NOTE 10" Screen

That second step is when you will release buttons to magisk boot (Vol Up + Power/Side Button)

Android 11(+?) Note 10 unlocked bootloader screens:
- "GALAXY NOTE 10" Screen
- A splash screens that ask for a power button press
- A splash screens that ask for a power button press ACTUALLY FROZEN

This is normal and doesn't change anything to magisk boot manip




- Download your stock Android **11** (make sure it is 11 or you will lose A LOT of time) ROM
- Extract BL + AP + CP + CSC (not HOME_CSC)
- Copy AP to your phone with `adb push /path/to/local/AP.tar.md5 /sdcard/download/AP.tar.md5`
- Install Magisk from the github's APK (v23.0 at the time)
- Start Magisk
- patch your AP file (under install tick recovery)
- then choose your AP file to patch it
- Copy patched AP to your phone with `adb pull /sdcard/download/magisk_patched-23000_xxxxx.tar.md5 /path/to/local/AP_patched.tar`
- Run Odin v3.14 on your PC
- Reboot the phone into download mode (Vol Up + Vol Down + Plug USB-C to PC)
- In Odin load BL + patched_AP + CP + CSC (not HOME_CSC)
- Boot the phone in magisk mode ( Vol Up + Side/Power Button until unofficial bootload splashscreen)
- Setup the phone
- Install Magisk from the github's APK (v23.0 at the time)
- Start Magisk
- It will ask for more setup and a reboot
- Accept and let (and prepare yourself to noot in magisk mode when) the phone reboots
- Restart Magisk
- Check that "Uninstall Magisk" is there, it means magisk and root are OK on your OS
- get the last TWRP for your Note 10 variant (for N970F, we use the d1 version)
- Go Back to Odin, click "Reset"
- Reboot the phone into download mode (Vol Up + Vol Down + Plug USB-C to PC)
- put twrp's tar into AP
- click "Start" (and prepare yourself for next step)
- hold Vol Up + Side/Power Button all the way to boot into twrp
- click "Wipe"
- then "Format Data"
- input "yes"
- go back to twrp's home screen
- click "mount"
- untick everything
- tick "Data"
- Enable MTP with your phone plug to PC
- copy "lineage-18.1-[random build string].zip to your phone
- (copy GAPPS here if you need it) to your phone
- copy the right magisk boot img from post #3 to your phone
- Disable MTP (probably useless but I'm in the old Android 1.6 way)
- go back to twrp home
- Click "Wipe"
- tick "Davilk / ART Cache", "System", "Data", "Cache" (And make sure "Internal Storage" is unticked)
- Swipe to wipe =)
- Click "Install"
- Click your lineage-18.1 zipfile
- Swipe to confirm flash
- go back
- (do the same for GAPPS here if you need it)
- go back to zip selection (under "Install")
- Click "Install Image"
- Click the the magisk boot img you copied
- Restart the Phone to system (no magisk boot, it's auto now)
- Setup the phone
- Install Magisk from the github's APK (v23.0 at the time)
- Check that "Uninstall Magisk" is there, it means magisk and root are OK on your OS
- Download and install fdroid
- Start Root Verifier
- Check if root is actually working
- Enjoy =)
