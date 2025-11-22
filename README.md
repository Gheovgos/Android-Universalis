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

# General Tips

This section contains general advice that is independent of the game you want to emulate. First of all, although it is considered unnecessary, I strongly recommend using virtual RAM (on some devices this option is called RAM+ or something similar). Enabling this option can prevent OOM crashes and, in my experience, has greatly helped in running more demanding titles (for example, HOI4 was very unstable in my case. Enabling 8GB of virtual RAM made it perfectly playable).


Paradox titles can be divided into three macro categories: Europa Engine (from the first Europa Universalis to Hearts of Iron II/Darkest Hour, circa 2000-2005), Clausewitz Engine (from Europa Universalis 3 to Hearts of Iron IV, approximately 2007-2016), Improved Clausewitz (from Imperator: Rome to Europa Universalis 5, 2019-present). You can get full list [here](https://en.wikipedia.org/wiki/Paradox_Development_Studio#Game_engines)

WIP

# Paradox Launcher

# Modding & Loading Times

# Winlator Settings (FEX, Box64)

# Game Specific Settings

# Multiplayer and achievements
