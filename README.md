# NDDimmerboard
Dimmer board with 10 channels for ESPHome and HomeAssistant

This board contains 10 MOSFET AC dimmers for (Mains AC) LED bulbs in homes. The board can be set-up in either leading-edge or trailing-edge dimmer modes, however trailing-edge is preferred. Each output is rated for +-1A for a total of 10A.
The board also contains 16 inputs for switches, this is done via 3.3v by just connecting a switch to the SWx terminal.

The ESP32-WROOM-30pin,which acts as the master for this board, communicates to ESPHome/HomeAssitant with LAN with the help of a LAN8720 module OR via Wifi.
The LAN8720 board has to be modified to remove the clk signal from the module and provide it from the ESP32, more on this in a different file.

The ESP32 sends the commands for the dimmer outputs to three Arduino Nanos via UART, which use their internal timers to generate accurate timing for the MOSFETS. The MOSFETS are controlled via SI8752AB-IS ICs to isolate mains from the low-voltage electronics.
More on the programming of the Arduino Nanos in a different file.

The total cost of this project is given in the 'Costs' file.
