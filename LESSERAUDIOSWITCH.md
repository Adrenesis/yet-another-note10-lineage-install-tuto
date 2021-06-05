## PREFACE: Android 11 and audio interfaces

Talking about bad design, let's talk about Android's sound card manager. It decide things for you, ask for nothing, and is not configurable...

There is also Samsung that decided, Audio interfaces where optionnal to a phone (sweet move).

We could talk about USB-DAC adapters, nothing is described correctly, half of them work, most of them don't allow to recharge the phone. 

It's just the usual cable cartel you might say, but this is barely usable and for anyone with bad hearing this phone is literraly a right angle oven you use to grind you hear on.

## CREDITS: 

- Roughy aka Mathias Nordskog, dev of LesserAudioSwitch
- Jocker and Anand from LineageOS' Telegram (distributors and testers of LesserAudioSwitch)

## INSTALL (for Android 11)

### Get LesserAudioSwitch

- Find the v2.6.0 of LesserAudioSwitch (while I write my mail to the dev to be able to post a link of this beta version)

### Install (:warning: written for v2.6.0, so this might change :warning:)

- Ensure that you have uninstalled any existing installs of Lesser AudioSwitch and restarted your device.
- Start your phone in recovery (`Volume Up` + Plug USBC to PC + `Power/Side button`)
- unzip from PC
- Go to "Mount" 
- Only tick "Data" 
- Enable MTP
- Copy the apk and XML to your Phone 
- Go back in "Mount"
- Tick "System"
- "Advanced" 
- "File Manager"
- Create a folder in system/priv-app 
- Copy the apk to it. Folder Name does not matter (call it lesser).
- Paste xml file in /system/etc/permissions/ named privapp_lesser.xml
- Restart the Phone
- Start LesserAudioSwitch
- Manage your sound cards =)
