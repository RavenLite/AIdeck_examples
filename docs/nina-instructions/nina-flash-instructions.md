---
title: NINA flash instructions
page_id: nina-flash-instructions
---


# Building NINA 

Follow instructions here for installing dependencies:
https://docs.espressif.com/projects/esp-idf/en/latest/get-started/index.html

***Make sure you install IDF version v3.3.1***

The env var IDF_PATH must be define and the esp toolchain must be in the path.

To flash with openocd
~~~~~shell
	~/esp/openocd-esp32/bin/openocd -f interface/ftdi/olimex-arm-usb-tiny-h.cfg -f board/esp-wroom-32.cfg -c "program_esp32 build/partitions_singleapp.bin 0x8000 verify" -c "program_esp32 build/bootloader/bootloader.bin 0x1000 verify" -c "program_esp32 build/nina_w10_fw.bin 0x10000 verify reset exit"
~~~~~

Check if the interface file matches your programmer