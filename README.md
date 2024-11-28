# NDDimmerboard

**Dimmer board with 10 channels for ESPHome and HomeAssistant**  
This board was designed to reduce cost, complexity, and radio interference while maintaining good performance compared to off-the-shelf components.

---

## ⚠️ WARNING  
**Please do not replicate this project if you are not qualified to work with mains AC voltage!**  
Replicate this project at your own risk.

---

## OUTPUTS  
This board contains **10 MOSFET AC dimmers** for (Mains AC) LED bulbs in homes.  
- The board can be set up in either **leading-edge** or **trailing-edge dimmer modes**, although trailing-edge is preferred.  
- **Output Rating:** Each output supports approximately ±1A, for a total of 10A across all channels.  
- The MOSFETs are controlled via **SI8752AB-IS ICs** to ensure isolation between mains and low-voltage electronics.  

The board's dimmer circuitry is based on the project:  
[Multi-Channel Trailing-Edge Dimmer System by Rod Elliott](https://sound-au.com/project201.htm)

---

## INPUTS  
The board supports **16 low-voltage inputs for switches**, connected via the SWx terminal.  
Inputs are configured for **LED lighting** and **momentary switches** with the following behavior:  
- **Short press:** Toggle light  
- **Long press:** Dim up/down  
- **Double press:** Max brightness  

---

## COMMUNICATIONS  
The ESP32-WROOM-30pin is the **master controller** for the board. It communicates with ESPHome/HomeAssistant via:  
- **LAN** (using a LAN8720 module)  
- **Wi-Fi**  

**LAN8720 Module Modification:**  
The module must be modified to remove the CLK signal and provide it from the ESP32.  
For more information, see:  
- [Home Assistant Community Post](https://community.home-assistant.io/t/esp32-lan8720-need-help/316270/7)  
- **Folder:** `LAN8720`  

The ESP32 communicates with three Arduino Nanos via **UART** to send dimmer output commands. The Nanos use internal timers to ensure accurate timing for the MOSFETs.

---

## ARDUINO NANOS  
- **Default Mode:** Ramping (brightness increases/decreases steadily for smooth transitions).  
  - Ideal for LED lighting.  
- **Instant Mode:** Changes are immediate (no ramping).  
  - Better for non-dimmer switch functionality.  

The Nano code and configuration details are in the `Arduino` folder.

---

## DIMENSIONS  
- **Board Size:** 200mm x 202mm  
- The **GERBER file** is included in `NDDimmerBoardV20241122.zip`.  
- The board does not fit into standard electrical boxes but is compact enough for most mains cabinets.

---

## COST  
- **Total Project Cost:** €112.02 (see `Cost` file for details).  
- **Cost per Channel:** €11.20  

### Comparison with Commercial Solutions:  
1. **FIBARO Dimmer 2:**  
   - Cost: €50 per channel  
   - Additional Features: Current measurement (not needed for this project)  
2. **Zigbee Tuya Dual Channel Dimmer:**  
   - Cost: €7.50 per channel  
   - Note: Manufactured in China with questionable CE standards  

---

## PCB  
![PCB Image](https://github.com/NytoxRex0/NDDimmerboard/blob/main/IMG/TOP.jpg?raw=true)  

---

### Additional Images:  
- **SOLDERED 1 CHANNEL:** *(Include a relevant image if available)*  
- **TEST 1 CHANNEL:** *(Include a relevant image if available)*  
- **FULL PCB:** *(Include a relevant image if available)*  

---
