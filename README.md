# yet-another-note10-lineage-install-tuto

Install tuto for Lineage 18.1 on a **Samsung Note 10** (tested on _N970F_)

# N970F LineageOS 18.1 install note WITH ROOT #

(this post cost 15 hours of research starting from 2021/05/30 04:00 AM GMT+02:00 so its in context)

## DISCLAIMER ##

NOT legally responsible, but STILL **morally** responsible of any blablabla I can put in this tuto

Warranty void and all that, you know the drill.

And more seriously, **TAKE YOUR TIME, DON'T PUT DEADLINES ON YOURSELF, EAT, SLEEP, DRINK WELL WHILE DOING THIS, THIS REQUIRES *PATIENCE* TO MAKE IT WORK, IF ANY SALT, DO A BREAK AND REEEAAAD TUTOS**


## BENEFITS

You'll get a lean and safer Note 10 :smile:

The goal here is to save the battery/screen life of the phone by having a clean Lineage rom that isn't bloated in every kind of way, and by bringing down frequencies of both CPU and GPU with ThundeRStormS Kernel.

The Samsung Galaxy Note 10 provide a strong hardware, 3 CPUs, for a total of 8 core, ranging from 1.5Ghz to 2.4Ghz, and the GPU is clocked at 729Mhz, for a total of 652 GFLOPS, **this is 4 times the processing power of a undocked Nintendo Switch**.

I **think** a phone shouldn't be capable of more than 1 Ghz without its user being aware, **this is litterally the kind of bad design that brings the phone to explode in your pocket and make you disabled for life (even if Samsung has a strong security, a battery is very expensive to the Earth).**

![](https://github.com/Adrenesis/yet-another-note10-lineage-install-tuto/blob/main/battery_benchmark.png?raw=true)

## CREDITS

My parents

- devs of me
- offered me the Galaxy Note 10

[Ivan Meler from XDA-dev](https://forum.xda-developers.com/t/rom-signature-spoofing-lineageos-18-1-for-note10-5g-note10-note10-exynos.4189503/)
- dev of them rom
- dev of the magisk kernel
- provider of tutorials to install LineageOS on Galaxy Note 10

[NALAS from XDA-dev](https://forum.xda-developers.com/t/kernel-thunderstorms-kernel-for-samsung-galaxy-s10-n10-family-only-exynos.4154863/)
- dev of the kernel
- provider of tutorials to install ThunderStormS on Galaxy Note 10
- provider of the "go back to lineage kernel before" explaination too

and more like the magisk individual, the Lineage team, Joker and Anand from a/the? Lineage Telegram, they both helped me with LesserAudioSwitch...

**A pleasure to have them doing the work Samsung didn't**

## BEFORE YOU START ANY OF THAT

- Save EFS to avoid accidental IMEI lost (or maybe loose your IMEI)
- ***Unlock bootloader !!!*** (or brick your hardware)
- **backup your internal storage/SMS/Contact/Calendar/... because you will erase everything**

> todo: add the actual steps to do that


## PREFACE

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


## PROCEDURE

### Make your Stock Magisk ROM

- Download your stock Android **11** (make sure it is 11 or you will lose A LOT of time) ROM
- Extract BL + AP + CP + CSC (not HOME_CSC)
- Copy AP to your phone with `adb push /path/to/local/AP.tar.md5 /sdcard/download/AP.tar.md5`
- Install Magisk from the github's APK (v23.0 at the time)
- Start Magisk
- patch your AP file (under install tick recovery)
- then choose your AP file to patch it
- Copy patched AP to your phone with `adb pull /sdcard/download/magisk_patched-23000_xxxxx.tar.md5 /path/to/local/AP_patched.tar`

### Install your magisk stock ROM

- Run Odin v3.14 on your PC
- Reboot the phone into download mode (`Volume Up` + `Volume Down` + Plug USB-C to PC)
- In Odin load BL + patched_AP + CP + CSC (not HOME_CSC)
- Untick "Auto-reboot" (or get ready between both next steps)
- Click "Start in Odin"
- Boot the phone in magisk mode (Maintain pressed `Volume Up` + `Side/Power Button` until you see the unofficial bootloader splashscreen)
- Setup the phone
- Install Magisk from the github's APK (v23.0 at the time)
- Start Magisk
- It will ask for more setup and a reboot
- Accept and prepare yourself to boot in magisk mode when the phone reboots

### Check Magisk State (and backup EFS if you need it and you still can u_u)

1. Restart Magisk
2. Check that "Uninstall Magisk" is there, it means magisk and root are OK on your OS
3. (backup EFS here if it's not too late)

### get needed files

- get [the last TWRP for your Note 10 variant](https://forum.xda-developers.com/t/recovery-official-3-5-0-x-twrp-for-galaxy-note-10-5g-exynos.4198413/) (for N970F, we use the d1 version)
- get [lineage18.1 for Note 10](https://forum.xda-developers.com/t/rom-signature-spoofing-lineageos-18-1-for-note10-5g-note10-note10-exynos.4189503/)
- get [Magisk boot image for your N10 variant](https://forum.xda-developers.com/t/rom-signature-spoofing-lineageos-18-1-for-note10-5g-note10-note10-exynos.4189503/post-83911107) (for N970F, we use the d1 version)

### Install Lineage 

(this is a one shot, if it fails anywhere, a safe point to restart is from **Install your magisk stock ROM**)

- Go Back to Odin, click "Reset"
- Reboot the phone into download mode (Vol Up + Vol Down + Plug USB-C to PC)
- put twrp's tar into AP
- click "Start" (and prepare yourself for next step)
- hold `Volume Up` + Plug to your PC + `Side/Power Button` all the way to boot into twrp
- click "Wipe"
- then "Format Data"
- input "yes"
- go back to twrp's home screen
- click "mount"
- untick everything
- tick "Data"
- Enable MTP with your phone plug to PC
- copy ``lineage-18.1-\[random build string\].zip`` to your phone
- (copy GAPPS here if you need it) to your phone
- copy the right magisk boot img to your phone
- Disable MTP (probably useless but I'm in the old Android 1.6 way)
- go back to twrp home
- Click "Wipe"
- tick "Davilk / ART Cache", "System", "Data", "Cache" (And make sure "Internal Storage" is unticked)
- Swipe to wipe =)
- Click "Install"
- Click your lineage-18.1 zipfile
- Swipe to confirm flash
- go back to zip selection (under "Install")
- (do the same for GAPPS here if you need it)
- go back to zip selection (under "Install")
- Click "Install Image"
- Click the the magisk boot img you copied
- Restart the Phone to system (no magisk boot, it's auto now)
- Setup the phone
- Install Magisk from the github's APK (v23.0 at the time)
- Check that "Uninstall Magisk" is there, it means magisk and root are OK on your OS
- Download and install fdroid
- Start fdroid
- Update repositories (swipe down)
- Search and install Root Verifier
- Start Root Verifier
- Check if root is actually working
- Enjoy =)

### Backup your working partitions OS/kernel/DTB (before messing with kernels and DTB/DTBO (device tree blob))

- Restart in recovery (Vol Up + Plug to PC + Power/Side Button)
- go to "Backup"
- tick every partitions
- Swipe to backup

## Installing ThundeRStormS Kernel

### Get your old lineage kernel (or ThundeRStormS will not work on your phone)

- Open your LineageOS zipfile
- Uncompress boot.img and rename it los-boot.img
- Enable MTP under "Mount" (with only "Data" ticked)
- copy los-boot.img to your phone

### Get ThundeRStormS Kernel

- Download the last AOSP CLANG Kernel from [here](https://androidfilehost.com/?w=files&flid=324562)
- Enable MTP under "Mount" (with only "Data" ticked)
- copy ThundeRStormS-Kernel-vx.x.x-AOSP-R...CLANG..zip

### Install ThundeRStormS Kernel

- In recovery go to "Install"
- Click 'Install Image'
- Choose "los-boot.img"
- Go back to zip selection (under "Install")
- Choose "ThundeRStormS-Kernel-vx.x.x-AOSP-R...CLANG...zip"
- :warning: **Actually read the Terms of Use[^warning_tos]** :warning:
- If you Agree click, "I agree"
- Then "Next"
- Then "Next"
- Tick "Thunder Tweaks"
- Tick "Install Kernel"
- Tick "Backup DTB/DTBO"
- Either:
    - a: **do not use DTB/DTBO if you don't know what it is, YOU CAN BRICK YOUR PHONE**
    - b: **READ A LOT ABOUT DTB/DTBO TO UNDERSTAND WHAT IT IS** then tick "INSTALL DTB/DTBO"
- Then "Next"
- Swipe to flash ? (I don't remember)
- when back to the recovery wipe Cache/davilk
- Restart the phone

[^warning_tos]: It explains you the limit of what you are using, and some dos and donts about the kernel

### Setting up a low performance profile

**This will underclock the phone, this is a low energy profile for people searching for phone and bettery life, THIS will probably make your phone LAAAG, a lot, it's been tested on simple tasks which are described below**

> todo: battery performance screenshot here

**also, don't mess with these settings if you don't know what you are doing, especially if I don't talk about them here, kernel setup is not a friendy territory to mess with**

- Once the phone restarted
- go to your favorite file manager
- go in internal storage/ThunderTweaks
- Install ThunderTweaks.apk
- Open it
- Click the menu button (top left of the screen)
- Click Profile
- Click the "+"
- Click "Create"
- Click "Current Settings"
- Tick "CPU"
- Tick "GPU"
- Name it "high performance"
- Click the menu button (top left of the screen)
- Click CPU
- Click "Apply on Boot" at the top
- Under "Big Frequencies", change the "Max Frequency" to "936Mhz"
- Under "Middle Frequencies", change the "Max Frequency" to "962Mhz"
- Under "Little Frequencies", change the "Max Frequency" to "949Mhz"
- (for DTB/DTBO users: Under "Little Frequencies", change the "Min Frequency" to "247Mhz", not tested in the benchmark beause discovered after)
- Click the menu button (top left of the screen)
- Click GPU
- Click "Apply on Boot" at the top
- Under "GPU Governor", change the "GPU Highspeed Clock" to "260Mhz" (thisis a hack should be max frequency, but then you would need a reboot to temporarly unlock it because of a bug)
- Under "GPU Thermal Control"
- For "GPU LEVEL 1 Throttling freq", put 260Mhz
- For "GPU LEVEL 2 Throttling freq", put 260Mhz
- For "GPU LEVEL 3 Throttling freq", put 260Mhz
- For "GPU LEVEL 4 Throttling freq", put 200Mhz
- For "GPU LEVEL 5 Throttling freq", put 200Mhz
- For "GPU LEVEL tripping Throttling freq", (I don't know what is it but) put 200Mhz (If you want to know, read about GPUs tripping state)
- Click the menu button (top left of the screen)
- Click "On Boot"
- You can see what you edited (check if everything looks in order)
- Reboot the phone
- Open ThunderTweaks
- Check all the settings are right (you don' want those setting being set wrong, believe me, and check for some later boots, and YES I'm paranoid with frequencies, but you don't want your CPU going 3Ghz without your awareness, and **even 1Ghz in the pocket is A LOT, don't fall for samsung's stupidity**)
- Click the menu button (top left of the screen)
- Click Profile
- Click the "+"
- Click "Create"
- Click "Current Settings"
- Tick "CPU"
- Tick "GPU"
- Name it "low performance"

### Switching between low and high performance

- Start ThunderTweaks
- Click the menu button (top left of the screen)
- Click Profile
- double click the wanted profile
- Apply

### Usage

- Let the phone in low performance **all the time**
- Put it in high perf whan you want to game, or do complicated things with your phone
- **go back in low performance when your are done**

### Backup everything up (so you can go back to this paradise whenever you mess with things)

- Restart in recovery (Vol Up + Plug to PC + Power/Side Button)
- go to "Backup"
- tick every partitions
- Swipe to backup

## Cool Packages to install (as FLOSS I could do)

- Silence
- AdAway (say goodbye to AdWares)
- T.E.A.M. Battery Bar (not open T_T, submit a Libre alternative in the issues or PR if you know one)
- LesserAudioSwitch (not open, but saved my ability to use the phone, it lets you manage the phone's sound cards on Android 1, and use a USB-DAC for headphones and the internal mic at the same time)
