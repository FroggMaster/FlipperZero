# Change the Flipper's Display Name

An overview of which lines to change to modify the display name of your Flipper. Note that this does not change the Flipper's name in the OTP memory as this is linked the serial of the device. However, this will change the name displayed in the firmware. 

## Instructions

**Step 1)** You will want to start by first forking the existing Flipper Zero firmware that you want to modify such as one of the following: 

- [Official FW](https://github.com/flipperdevices/flipperzero-firmware)
- [Unleashed FW](https://github.com/Eng1n33r/flipperzero-firmware)
- [Unleashed/Plugins FW](https://github.com/RogueMaster/flipperzero-firmware-wPlugins)

---

**Step 2)** You will need to modify [**Line 278** of **furi_hal_version.c**](https://github.com/flipperdevices/flipperzero-firmware/blob/f6384116a1e501d2925013f6fae7e1d7cb6786cb/firmware/targets/f7/furi_hal/furi_hal_version.c#L278)

Change this line from 
```C
return *furi_hal_version.name == 0x00 ? NULL : furi_hal_version.name;
```
to
```C
return "YourNewFlipperName";
```
---

**Step 3)**  Once you have modified the code as required, you will need to build your firmware. Step by step instructions on how you build firmware can be found on the Flipper Zero Repository: 
- [Build with Docker](https://github.com/flipperdevices/flipperzero-firmware#build-with-docker)
- [Build with Linux or MacOS](https://github.com/flipperdevices/flipperzero-firmware#build-on-linuxmacos)
