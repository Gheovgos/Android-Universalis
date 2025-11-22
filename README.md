# Android-Universalis
This repository is intended to be a collection of guides/tips/utilities for running Paradox titles on Android smartphones.

# State of the Art

At the moment, there is no emulator/official/unofficial port of any of Paradox title. You can stream them by using Moonlight, GeForce Now or xCloud (only for Crusader Kings III afaik). But I'm not an huge fan of game streaming and I think our devices are strong enough to run those titles. So, at the moment I suggest to use the best "emulator": Winlator, in particular the cmod fork. Why?

Paradox titles do not require graphics power, but only a lot of computational power (CPU bound): therefore, the goal is to minimize any bottlenecks/waste of resources with unnecessary additional computations: the cmod version has a unique advantage (at the moment, November 2025): you can use both FEX and Box64 with its bionic variant (which, in simple terms, is “native” Android). This way, we ensure that any additional CPU computation costs are minimized.

Unfortunately, it is currently difficult to run Paradox titles in the Linux version. It is possible via Termux and in particular with a proot distribution, but the performance is almost identical (tested with EU4). If you have root privileges and a lot of patience, I recommend trying the chroot version for Linux versions in order to get the best performance.

Furthermore, with Android 16, it is theoretically possible to run Linux programs natively on Android. However, it does not work on all devices: for example, a limitation has been placed on this feature on Samsung phones, and there is currently no way to circumvent it (November 2025).

# Useful Links
[Winlator Cmod](https://github.com/coffincolors/winlator)

[7zip](https://7-zip.org/download.html)

[WCPs](https://github.com/Arihany/WinlatorWCPHub) 
WCPs are add-ons that can be installed via Winlator. They may contain different versions of FEX, Box64, DXVK, and so on.

[AdrenoToolsDriver](https://github.com/K11MCH1/AdrenoToolsDrivers)
It contains drivers for Qualcomm users. You can install them via Winlator

[UniversalChecksumPatcher](https://github.com/IlliaYalovoi/universal-checksum-patcher) 
A universal tool (EU4, HOI4, and EU5) for patching the main executable. Essentially, it prevents the checksum calculation from being verified during loading.

# General Tips
