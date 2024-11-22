# NDDimmerboard
Dimmer board with 10 channels for ESPHome and HomeAssistant

WARNING: Please do not replicate this project if you are not qualified to work with mains ac voltage! Replicate this project on your own risk!

OUTPUTS:
This board contains 10 MOSFET AC dimmers for (Mains AC) LED bulbs in homes. The board can be set-up in either leading-edge or trailing-edge dimmer modes, however trailing-edge is preferred. Each output is rated for +-1A for a total of 10A. The MOSFETS are controlled via SI8752AB-IS ICs to isolate mains from the low-voltage electronics.
The board dimmer circuitry is based on the following project: https://sound-au.com/project201.htm

INPUTS:
The board also contains 16 inputs for switches, this is done via 3.3v by just connecting a switch to the SWx terminal.

COMMUNICATIONS:
The ESP32-WROOM-30pin, which acts as the master for this board, communicates to ESPHome/HomeAssitant with LAN with the help of a LAN8720 module OR via Wifi.
The LAN8720 board has to be modified to remove the clk signal from the module and provide it from the ESP32, more on this in a different file (SoonTM).
The ESP32 sends the commands for the dimmer outputs to three Arduino Nanos via UART, which use their internal timers to generate accurate timing for the MOSFETS. 
More on the programming of the Arduino Nanos in a different file (SoonTM).

DIMENSIONS AND COST:
The board is 200mm x 202mm in size, the GERBER file is given in the 'NDDimmerBoardV20241122.zip' file.
The total cost of this project is 112.02euros as given in the 'Cost' file.
