# NDDimmerboard
10 channel Dimmer Board for ESPHome and HomeAssistant

This board contains 10 MOSFET dimmer outputs for LED lighting in homes. The board can be set-up in either leading-edge or trailing-edge dimmer modes, however trailing-edge is preferred. Each output is rated for +-1A for a total of 10A.
The board also contains 16 inputs for switches, this is done via 3.3v by just connecting a switch to the SWx terminal.

Communication to ESPHome/HomeAssitant is done with the ESP32-WROOM-30pin via a LAN8720 which acts as the master for this board.
The LAN8720 board has to be modified to remove the clk signal from the module and provide it from the ESP32.

The ESP32 sends the commands for the dimmer outputs to three Arduino Nanos via UART, which use their internal timers to generate accurate timing for the MOSFETS. The mosfets are isolated via SI8752AB-IS.
