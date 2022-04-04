# Teensy 4.1 slcan
Turn your teensy4.1 into a slcan device, source code based on https://github.com/mintynet/teensy-slcan but using FlexCan_T4 library instead of FlexCAN.

Build using VScode and platformio
# Usage
Tested on linux only:

Using python: 
python -m can.viewer -c /dev/ttyACM0@2000000 -i slcan

Using cansocket (Compatible with CanSavvy)
`sudo slcan_attach -f -s6 -o /dev/ttyACM0
sudo slcand -S 2000000 ttyACM0 can0
sudo ifconfig can0 up
candump can0`
