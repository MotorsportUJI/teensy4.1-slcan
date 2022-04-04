# Teensy 4.1 slcan
Turn your teensy4.1 into a slcan device, source code based on https://github.com/mintynet/teensy-slcan but using FlexCan_T4 library instead of FlexCAN.

Build using VScode and platformio

# Usage
Tested on linux only:

Using python:\
  $ python -m can.viewer -c /dev/ttyACM0@2000000 -i slcan

## Setup
Please replace ttyUSB with ttyACM in case of using Arduino Uno.

    $ sudo slcan_attach -f -s6 -o /dev/ttyUSB0  
    $ sudo slcand -S 1000000 ttyUSB0 can0  
    $ sudo ifconfig can0 up  

then,

    $ candump can0

## Cleanup

    $ sudo ifconfig can0 down  
    $ sudo killall slcand  

