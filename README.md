**Intro**
Sharing my hardware PCB design for smart powerstrip as it was requested.
Made some v.9 changes based on initial feedback I received posting pictures online.

It's one of my first PCB Projects, so was mainly used to learn as well as get a better understanding of KiCad.
I'm sure there is plenty to improve. So, I welcome anyone to do so. But please share your upgrades. Love to hear what you did.

**Baseline features:**
- Power conversion onboard: Single plug into main outlet
- All THT components: anyone can make this with basic equipment
-  4 x Relay for individual control
- Reduce interference: Star configuration
- Easy ESP: Off-the-shelf ESP32
- Replaceable: ESP in case of failure (I've blown a few in my time)
- ESP32C6 allows both WiFi and Zigbee
- Safety: Glass fuse on each outlet

**Hardware (BOM):**
Electrical Components
- 4 x 1N4448
- 4 x 1N4739A
- 4 x 2N3904
- 4 x	Relay_SPST_RAYEX-L90AS
- 1 x HLK-12M05A
- 1 x X2 CAP 100nf
- 1 x Varistor CAP VY2
- 1 x	Polymer cap	100µF
- 4 x Resistor 1kΩ

MCU
- 1 x XIAO-ESP32C6
- Optional: Pinheaders to seat ESP. Or solder directly to board.

Connectors  
- 5 x Fuseholder_Clip-5x20mm
- 1 x FL1	Choke_Schaffner_RN102-04-14.0x14.0mm
- 5 x TerminalBlock_WAGO_236-202_1x02_P7.50m
- 1 x	PinSocket_1x04_P2.54mm_Vertical
- 1 x	PinHeader_1x03_P2.54mm_Vertical




**Software:**
Currently running ESPhome firmware. No custom firmware jobs. ESPhome integrates well into my Home Assistant environment.

**ESPHome YAML Config**
  switch:
    - platform: gpio
      name: "Relay 1"
      pin: 1  # D1 (GPIO5)
    - platform: gpio
      name: "Relay 2"
      pin: 2  # D2 (GPIO4)
    - platform: gpio
      name: "Relay 3"
      pin: 21  # D3 (GPIO3)
    - platform: gpio
      name: "Relay 4"
      pin: 22  # D4 (GPIO2)

      
