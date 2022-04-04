# Teensy 4.1 slcan
Turn your teensy4.1 into a slcan device, source code based on https://github.com/mintynet/teensy-slcan but using FlexCan_T4 library instead of FlexCAN.

Note: You'll need a 3.3V logic CAN transceiver (like the mcp2562) to interface the teensy with the can bus 

Build using VScode and platformio

# Usage

Tested on linux only\

## Building
You need FlexCan_T4 library installed on platformio for building

Build and Flash the program to the teensy using platformio (or your ide of choice)\

## Requirements:
    $ python3-can
    $ can-utils

## Test (with python-can)
    
    $ python -m can.viewer -c /dev/ttyACM0@2000000 -i slcan

## Setup (with can-utils)

    $ sudo slcan_attach -f -s6 -o /dev/ttyACM0  
    $ sudo slcand -S 2000000 ttyACM0 can0  
    $ sudo ifconfig can0 up  

then,

    $ candump can0

or open SavvyCan and set up a new socketcan device 

## Cleanup

    $ sudo ifconfig can0 down  
    $ sudo killall slcand  

