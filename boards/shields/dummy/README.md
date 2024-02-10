# The Dummy

Simplest possible keyboard with just one key. Purpose is to verify the functionality of your nice!nano.
- Connects immediately via USB (p.e. because it's a raw shield without an actual keyboard or battery)
- Advertises itself as 'aDummy' Bluetooth device

It supports only a single Bluetooth pairing, i.e. once you paired it with your computer, it won't pair with anything else.

## First
Disconnect the nice!nano from usb and battery if connected.

## Build
Fork the github repo and download the firmware.zip as described [here](https://zmk.dev/docs/user-setup#download-the-archive)
Unzip the file.

## Connect
Insert the USB, put shield into bootloader mode, mount the NICENANO mass storage 
 and copy dummy-nice_nano-zmk.uf2 to flash the firmware. More details [here](https://zmk.dev/docs/user-setup#flashing-uf2-files).
The device should reboot (i.e. the mass storage disappears) and now the keyboard should be usable

## Use USB
Open a text editor with an empty document.
Connect the pins 10 and 16 (the two lowest pins on the right of a pro-micro-like board (see https://zmk.dev/docs/development/new-shield#shield-overlays)) and see the character 'a' appear -> 🤯

## Use Bluetooth
Pair the 'aDummy' device with your computer and test functionality like before in [Use USB](#use-usb)

## Debug
`sudo tio /dev/ttyACM0`

## Technical Details
Default pins are 10 and 16: the two lowest pins on the right of a pro-micro-like board (see https://zmk.dev/docs/development/new-shield#shield-overlays)
Default key that's pressed when connecting these pins (p.e. with a tweezer) is "A"

Adjust the pins in [dummy.overlay](dummy.overlay) and the key that's pressed in [dummy.keymap](dummy.keymap).
