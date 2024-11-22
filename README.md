# NDDimmerboard
Dimmer board with 10 channels for ESPHome and HomeAssistant

WARNING: Please do not replicate this project if you are not qualified to work with mains ac voltage! Replicate this project on your own risk!

OUTPUTS:
This board contains 10 MOSFET AC dimmers for (Mains AC) LED bulbs in homes. The board can be set-up in either leading-edge or trailing-edge dimmer modes, however trailing-edge is preferred. Each output is rated for +-1A for a total of 10A. The MOSFETS are controlled via SI8752AB-IS ICs to isolate mains from the low-voltage electronics.
The board dimmer circuitry is based on the following project: https://sound-au.com/project201.htm

INPUTS:
The board also contains 16 inputs for switches, this is done via low-voltage by connecting a switch to the SWx terminal. The behaviour of each switch can be programmed to your desire.

COMMUNICATIONS:
The ESP32-WROOM-30pin, which acts as the master for this board, communicates to ESPHome/HomeAssitant with LAN with the help of a LAN8720 module OR via Wifi.
The LAN8720 board has to be modified to remove the clk signal from the module and provide it from the ESP32, more on this in a different file (SoonTM).
The ESP32 sends the commands for the dimmer outputs to three Arduino Nanos via UART, which use their internal timers to generate accurate timing for the MOSFETS. 
More on the programming of the Arduino Nanos in a different file (SoonTM).

DIMENSIONS :
The board is 200mm x 202mm in size, the GERBER file is given in the 'NDDimmerBoardV20241122.zip' file. Obviously this board does not fit in standard electrical boxes on which you mount your switch, however this board is quite compact.

COST:
The total cost of this project is 112.02euros as elaborated in the 'Cost' file.
This board was developed to decrease cost, complexity and radio interference. 
Comparing the cost to on the shelf components like Z-Wave FIBARO Dimmer 2 or Zigbee Tuya dual channel dimmers, the cost is respectable.
This board comes in at a cost of 11.20euros per channel.
The FIBARO Dimmer 2 comes in at a cost of 50 euro per channel (it has more features like current measurement, which I do not need).
The Tuya Dual channel dimmer module comes in at only 7.50euros per channel, however it's made in china and false CE standard do not encourage me to buy those.
