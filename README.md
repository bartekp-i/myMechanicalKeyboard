# 75% Custom Mechanical Keyboard PCB Documentation  
**A compact, RP2040-powered keyboard with USB-C and OLED support.**  

---

## Overview  
This project is a custom 75% mechanical keyboard PCB designed around the Raspberry Pi RP2040 microcontroller. It features a non-standard QWERTY layout with 83 keys, USB-C connectivity with robust signal filtering, ESD protection, and support for a 0.96-inch RGB OLED module. The PCB is manufactured by JLCPCB and ready for soldering and programming.  

---

## Features  
- **RP2040 Microcontroller**: Dual-core ARM Cortex-M0+ for flexible firmware customization.  
- **USB-C Connectivity**: Built-in signal filtering and ESD protection (TVS diode) on D+/D- lines.  
- **Power Regulation**: 3.3V LDO Regulator (SPX5205M5-L-3-3/TR) for stable power delivery.  
- **QSPI Flash**: W25Q16JVUXIQ (2MB) for firmware storage.  
- **Precision Timing**: ABM8-272-T3 12MHz crystal oscillator.  
- **OLED Support**: Pads/THT headers for a 0.96-inch RGB OLED module.  
- **Debugging**: SWD (Serial Wire Debug) pins for firmware flashing/troubleshooting.  
- **Mechanical Design**:  
  - 75% layout (83 keys).  
  - Custom plate and back panel.  
  - Stabilizers for Space, Shift, Enter, and Backspace keys.  
  - AKKO V3 Pro Yellow switches (pre-lubed linear).  
  - Switching diodes for every key (anti-ghosting).  

---

## Hardware Details  

### RP2040 Microcontroller  
- Handles key matrix scanning, USB communication, and peripheral control.  
- Connected peripherals:  
  - **QSPI Flash**: Stores firmware and configuration data.  
  - **ABM8-272-T3 Oscillator**: Provides precise timing for USB communication.  
  - **Boot Button**: For entering firmware update mode.  
  - **SWD Pins**: 1x3 header for programming/debugging.  

### USB-C and Signal Integrity  
- **ESD Protection**: TVS diodes on D+/D- lines to protect against electrostatic discharge.  
- **Filtering**: Ferrite beads/RC filters to reduce noise on data lines.  

### Power Regulation  
- **SPX5205M5-L-3-3/TR LDO**: Converts USB 5V to 3.3V for RP2040 and peripherals.  
- Max current: 150mA (sufficient for RP2040, OLED, and peripherals).  

### Keyboard Matrix  
- **83-Key Layout**: Non-standard 75% design (see `Layout/` directory for matrix mapping).  
- **Switching Diodes**: Each key has a diode (1N4148 or similar) to prevent "ghosting" by blocking reverse current in the matrix.  

### Stabilizers  
- Required for longer keys: Spacebar, Enter, Backspace, and Shift (supports Cherry-style stabilizers).  

### OLED Module  
- **0.96-inch RGB OLED**: Connected via I2C/SPI (configurable in firmware).  
- Mounting: THT pads or header pins for secure attachment.  

---

## Design & Manufacturing  
- **PCB**: Designed in KiCad (files in `Hardware/`).   
- **Manufacturing**:  
  - JLCPCB 2-layer PCB with white solder mask finish.  
  - SMD components can be pre-soldered.  

---

## Firmware  
- Yet to be coded
- Compatible with **QMK** or **KMK** (CircuitPython-based).  
- Example firmware will be available in `Firmware/`.  

---

## Build Instructions  
1. **Solder Components**:  
   - Diodes (orient cathode stripe correctly).  
   - RP2040, USB-C port, oscillator, and regulator.  
   - SWD header and OLED pins.  
2. **Mount Stabilizers**: Clip-in Cherry stabilizers for large keys.  
3. **Install Switches**: Secure AKKO V3 Pro switches into the plate and solder to PCB.  
4. **Attach OLED**: Solder headers or directly mount the OLED module.  
5. **Flash Firmware**: Use SWD or UF2 bootloader (press boot button while plugging in USB).  

---

## License  
- **Hardware**: [CERN OHL 1.2](LICENSE_HARDWARE).  
 

---

## Acknowledgements  
- JLCPCB for PCB manufacturing.  
- Raspberry Pi Foundation for RP2040.  

📸 *Photos!*  


---  
*Designed with ⌨️ by Bartosz Piotrowski.*
