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
- **0.96-inch RGB OLED**: Connected via SPI.  
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

## Acknowledgements  
- JLCPCB for PCB manufacturing.  
- Raspberry Pi Foundation for RP2040.  

## 📸 Photos!  

**Keyboard layout** 
![keyboard-layout](https://github.com/user-attachments/assets/36374ffc-ff6f-4ab3-b52e-819034e13172)

**Schematic** 
![image](https://github.com/user-attachments/assets/e2352559-2c77-420e-8224-c967ec53c53b)
![image](https://github.com/user-attachments/assets/c1ecb416-31de-44c8-9e1a-9129b640e424)

**PCB Layout**
![image](https://github.com/user-attachments/assets/e2a1e1b3-3463-414b-8dad-01f92e65b5f2)

**Keyboard Plate**
![image](https://github.com/user-attachments/assets/228409c0-0588-44f2-9471-006ce878b704)

**Back Plate**
![image](https://github.com/user-attachments/assets/eb16f702-afb3-4fd0-a452-9f7609b363d3)

**3D PCB Layout**
![image](https://github.com/user-attachments/assets/5ca09da4-3994-46e7-9734-d4910ed0aa89)

**3D Keyboard Plate**
![image](https://github.com/user-attachments/assets/65f55a00-97cf-4d20-8e37-9bb705ff3d45)

**3D Back Plate**
![image](https://github.com/user-attachments/assets/1ba2c2ec-b057-4017-ab46-482667685f35)

**Boards After Manufacturing**
![de2a45c0-26ce-4094-b5c6-7f7046fe6de4](https://github.com/user-attachments/assets/55a00167-a0f2-483d-bb35-7990f8b64e47)
![ff16e77b-f6f2-4f7a-a8ca-ae126aca71c9](https://github.com/user-attachments/assets/05522286-4a75-40ec-affa-df896fff20d5)
![aa148c33-f10a-49f3-b886-1f6bd5d3fd8b](https://github.com/user-attachments/assets/a5459021-be8b-4f22-b05b-54fb88cb2bae)
![42f9e057-b715-42d8-a504-73b2bb60c914](https://github.com/user-attachments/assets/35e36f4b-e37e-4cb5-a0d1-208a5fb0f74c)



---  
*Designed with Kicad by Bartosz Piotrowski.*
