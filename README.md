# 5g_enabler
Universal Modem Fix for 5G enable on Pixel Tensor

### Technical Requirements:
Magisk 20.4+ | Device on SoC Google Tensor ( Pixel: 6, 6P, 6a, 7, 7P, 7a, 8, 8P )
### Description of operation, functionality:
5G activation for unsupported countries and operators.
Improved signal quality and strength in some situations.
Speed up CS fallback in some situations.
Can be used in combination with modules for VoLTE/VoWiFi activation if you need these modes.

### Note: In network settings you may see an additional option “Allow 2G networks”. Be sure to activate this option if you need to ditch to 2G while in use.

### The module is inspired by the following modules and the working principle is taken from them (thanks to the authors):
Universal Modem Fix
Pixel-mdm-patch

The principle of operation is taken from the above modules. However, Universal Modem Fix is not updated by the author for more than a year, and Pixel-mdm-patch on my Pixel 8 stopped catching connection after updating to android 15.
The changes in cfg.db are done using the Displax method:
confnames -> it_iliad -> 2124 -> confmap -> 2124_as_hash -> WILDCARD (0) / PTCRB (20001) / PTCRB_ROW (20005) -> it_iliad_2124_hash
And patching of cfg.db itself is done with sqlite3 (idea like andrew_z1, but he used his own binary and patched only these mcc countries - 250 255 257 400 401 282 283 289).
andrew_z1 @ 05.03.24, 08:03 *
at the moment after the update you need to disable or uninstall the module, reboot the phone, install the module again from the storage (Magisk saves modules in the Downloads folder) and reboot again.
