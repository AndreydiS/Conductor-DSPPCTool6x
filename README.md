# Conductor-DSPPCTool6x
Steps to upload new code
- Install Arduino IDE
- Add MiniCore board manager
  - In the Arduino IDE go to File -> Preferences and add the following URL to Additional boards manager:
  - https://mcudude.github.io/MiniCore/package_MCUdude_MiniCore_index.json
  - Install/Update following this article https://github.com/MCUdude/MiniCore?tab=readme-ov-file#how-to-install
- Download the following files to a local folder (e.g. C:\Temp\Helix)
  - avrdude.conf
  - HelixVolumeControlLite.ino.eep
  - HelixVolumeControlLite.ino.hex
- Connect USBToTTL converter to PC and board (double check VCC and GND connection) and check the COM port number
- Open Command Prompt (not Powershell) go to C:\Temp\Helix and run the following command (update COM port number and path to *avrdude*)
- "C:\Users\admin\AppData\Local\Arduino15\packages\MiniCore\tools\avrdude\8.0-arduino.1/bin/avrdude" "-Cavrdude.conf" -v -V -patmega328p -curclock -PCOM4 -b115200 -D -xnometadata "-Ueeprom:w:HelixVolumeControlLite.ino.eep:i" "-Uflash:w:HelixVolumeControlLite.ino.hex:i"
