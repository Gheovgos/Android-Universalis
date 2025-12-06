# Android-Universalis
This repository is intended to be a collection of guides/tips/utilities for running Paradox titles on Android smartphones.

Table

# State of the Art

At the moment, there is no emulator/official/unofficial port of any of Paradox title. You can stream them by using Moonlight, GeForce Now or xCloud (only for Crusader Kings III afaik). But I'm not an huge fan of game streaming and I think our devices are strong enough to run those titles. So, at the moment I suggest to use the best "emulator": Winlator, in particular the cmod fork. Why?

Paradox titles do not require graphics power, but only a lot of computational power (CPU bound): therefore, the goal is to minimize any bottlenecks/waste of resources with unnecessary additional computations: the cmod version has a unique advantage (at the moment, November 2025): you can use both FEX and Box64 with its bionic variant (which, in simple terms, is “native” Android). This way, we ensure that any additional CPU computation costs are minimized.

Unfortunately, it is currently difficult to run Paradox titles in the Linux version. It is possible via Termux and in particular with a proot distribution, but the performance is almost identical (tested with EU4). If you have root privileges and a lot of patience, I recommend trying the chroot version for Linux versions in order to get the best performance.

Furthermore, with Android 16, it is theoretically possible to run Linux programs natively on Android. However, it does not work on all devices: for example, a limitation has been placed on this feature on Samsung phones, and there is currently no way to circumvent it (November 2025).

I'm using Samsung S23 (Snapdragon 8 Gen2, 8 GB), performance may vary depending on the device. 

# Useful Links
[Winlator Cmod](https://github.com/coffincolors/winlator)

[7zip](https://7-zip.org/download.html)

[WCPs](https://github.com/Arihany/WinlatorWCPHub) 
WCPs are add-ons that can be installed via Winlator. They may contain different versions of FEX, Box64, DXVK, and so on.

[AdrenoToolsDriver](https://github.com/K11MCH1/AdrenoToolsDrivers)
It contains drivers for Qualcomm users. You can install them via Winlator

[UniversalChecksumPatcher](https://github.com/IlliaYalovoi/universal-checksum-patcher) 
A universal tool (EU4, HOI4, and EU5) for patching the main executable. Essentially, it prevents the checksum calculation from being verified during loading.

[Project-Alice](https://github.com/schombert/Project-Alice) 
Project Alice is an open source engine reimplementation of Victoria II engine.

[Comet](https://github.com/imLinguin/comet?tab=readme-ov-file)

[Heroic](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher)

# General Tips

This section contains general advice that is independent of the game you want to emulate. First of all, although it is considered unnecessary, I strongly recommend using virtual RAM (on some devices this option is called RAM+ or something similar). Enabling this option can prevent OOM crashes and, in my experience, has greatly helped in running more demanding titles (for example, HOI4 was very unstable in my case. Enabling 8GB of virtual RAM made it perfectly playable).


Paradox titles can be divided into three macro categories: Europa Engine (from the first Europa Universalis to Hearts of Iron II/Darkest Hour, circa 2000-2005), Clausewitz Engine (from Europa Universalis 3 to Hearts of Iron IV, approximately 2007-2016), Improved Clausewitz (from Imperator: Rome to Europa Universalis 5, 2019-present). You can get full list [here](https://en.wikipedia.org/wiki/Paradox_Development_Studio#Game_engines)

Europa Engine will probably not start on the first attempt. This is because only 16-bit colors are supported: to get around this problem, you need to use CnC-DDraw (slow) as the Glide Wrapper. At the moment, I am not aware of any other solutions. Otherwise, it should work fine.
The second engine, on the other hand, works without any special modifications. It supports the use of different DirectX versions (at least for HOI4 and EU4), supports command line arguments, and mods as zipped files. Finally, the last one should be an improvement but heavier to run, but I have not tested it much yet (only with Imperator Rome). 

A general benefit, valid for everyone, is to move the game to the C:\ drive: this significantly reduces loading times

To further reduce loading times (only valid for the second engine), you can zip the vanilla content and treat it as a mod (this was a suggestion found on the Paradox forum for CK2; I can no longer find the original source, but it seems to be valid for all Clausewitz Engine titles). Below is a short guide on how to set this up.

Using 7zip (or another similar tool), zip the following folders from a title of your choice: common, decisions, events, history, interface, localisation, map (the zipped file must NOT contain any roots). You can then use the .mod file from this repository as a template, as long as it contains the name of your zip file (I use vanilla as the name). Finally, to load it, go to Documents\Paradox Interactive\YourGame\ create the “mod” folder and insert both the .mod file and the .zip file, while outside (inside \Your Game\) insert the dlc_load.json file and insert the name of the .mod file of your choice in “enabled_mods”, also inserting the name of the parent folder. You can find a sample file in this repository. Some titles (such as EU3) also support loading the mod via command line: just run
```
eu3.exe --mod ModName.mod
```
to load it.

# Paradox Launcher

At present, the official launcher does not run completely. The only way to try to start it is to modify the settings contained in the launcher-settings.json file and remove the exe parameters (last record of the file, in exeArgs). This allows you to start the launcher, but in my experience, I have never achieved anything concrete. The installer also does not seem to work properly.

# Modding

As for modding, the process is very similar to the “Vanilla” mod described in the previous two sections: simply place the zipped file/mod folder and the corresponding file in the Documents\Paradox Interactive\YourGame\mod folder, then enter the name of the .mod file in dlc_load.json, at least as far as the Clausewitz Engine is concerned. For the Europa Engine, just find the settings.txt file and explicitly declare the mod you want to load. The game usually comes with lots of useful and self-explanatory readme files. I have not tried yet with new engine

# Winlator Settings (FEX, Box64)

# Game Specific Settings

# Multiplayer and achievements

It is possible to unlock achievements and play multiplayer, although the configuration is quite lengthy (for now, I have only tested it with the GOG versions. It should also be possible with Steam through emulators such as GameHub and GameNative).


First of all, you need to have:

1. The version of the game downloaded via GOG (the “offline” version is fine)
2. Comet
3. Heroic configuration file

Heroic is an alternative launcher for GOG and Epic Games, but it doesn't currently work on Winlator. But you don't need to launch it: you actually need to find and zip the “heroic” folder located in AppData/Roaming. At the moment, you will need an external computer, run heroic at least once, and then log in to obtain this folder, but I think I will upload the customizable heroic folder to this repository in the future. Once you have copied and pasted the “heroic” folder in C:\users\x-user\AppData\Roaming into the container, you need to download the comet.exe. Then, open the Windows cmd and run this command:

`comet.exe --from-heroic --username YOUR_USERNAME`

Finally, launch the game exe.
At the moment, only tested with EU4.
To create a shortcut that automatically launches comet, simply create the shortcut as normal (right click on your .exe, then create shortcut, while you are in your container). Then, in the app settings, select “Use secondary Executable,” indicate the path to “comet.bat” (note: the path to the .vbs script must be specified within the bat file; this script must be placed together with comet.exe in the game folder). Also, I noticed that Winlator cannot locate the second executable file within the C: drive, so I recommend placing it in D:. I don't know if it also works with Z: and E:), indicate the delay time (with 0 it will not start, any other integer value will, 5 ms should be fine) and you're done. You should now be able to run the game + comet and unlock the related achievements.

With the GOG version installed, you can also connect to a server and play multiplayer. I haven't tested this yet, though. 
Note that you can also run comet in other ways by providing the access token. Unfortunately, I haven't found any other ways to do this, so the “heroic” solution seems to be the fastest and easiest. If I find any, I'll let you know here.

# Thanks
