# Push-n-Turn 31

Push-n-Turn 31 is a USB MIDI controller with 3 keyboard switches (RedDragon low profile), a rotary encoder and 3/4 RGB leds (WS8212).

The device sports a USB type-C connector and requires no device drivers on Mac or PC.

The keys can be configured (via MIDI messages, or the configurator) to produce notes, CC codes (momentary or toggle mode). The encoder produces 0..127 on a configurable CC channel. The encoder button produces 127/0 on a CC channel of choice.
Each switch has an RGB led that shows the state of the switch.
The device uses a modified midi library for CH55x devices made by mi:muz 

## Configuring the keys
Configuration of the keys can be done by sending midi codes to the device.
You can use python midiutil for this (https://github.com/sourcebox/midiutil).

start prog
./midiutil.py -d 1 -w 186 102 42

end prog
./midiutil.py -d 1 -w 186 102 43

module type
./midiutil.py -d 1 -w 186 102 44
returns: (10, 103, INSTRUMENT_TYPE);


firmware version
./midiutil.py -d 1 -w 186 102 45
returns (10, 104, FW_VERSION) 10 for version 1.0

show configuration
./midiutil.py -d 1 -w 186 102 46
returns the config of each of the 6 buttons, the rotary knob and rotary encoder

show stepsize 
./midiutil.py -d 1 -w 186 102 47
returns (10, 105, encStepSize)

show MIDI channel 
./midiutil.py -d 1 -w 186 102 48
returns (10, 106, MIDIChannel)

reboot in firmware update mode
./midiutil.py -d 1 -w 186 102 49

programming keys
./midiutil.py -d 1 -w 186 102 42
./midiutil.py -d 1 -w 186 11 60
./midiutil.py -d 1 -w 186 22 30
./midiutil.py -d 1 -w 186 33 9
./midiutil.py -d 1 -w 186 24 15
./midiutil.py -d 1 -w 186 5 24
./midiutil.py -d 1 -w 186 102 43


## Links & References

* [mi:muz:ch55x Tiny USB MIDI Library for Ch55xduino](https://github.com/mimuz/mimuz-ch55x)
* [push-n-turn-midi61](https://github.com/concept-code-design/push-n-turn-midi61)

# License

![OpenSourceLicense](https://github.com/concept-code-design/push-n-turn-midi61/blob/main/OpenSourceLicense.png)

Concept & Code invests time and resources providing this open source design, please support them and open-source hardware by purchasing products from Etsy or Tindie!

Designed by Ronald Leenes.

Firmware released under an GNU AGPL v3.0 license. See the LICENSE file for more information.

Hardware released under an CERN Open Hardware Licence v1.2. See the LICENSE_HARDWARE file for more information.


February 2025
