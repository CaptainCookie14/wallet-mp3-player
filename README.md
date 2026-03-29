# wallet-mp3-player
This project is a compact, portable MP3 player designed to fit roughly the size of a credit card. It focuses on minimal power usage, small PCB design, and simple user controls for playing music from onboard or external storage.

HOW TO USE IT 
Copy MP3 or WAV files onto a microSD card and insert it into the device. Power it on using the built-in battery and use the onboard buttons to control playback. You can play, pause, skip tracks, and adjust volume directly from the device without needing a phone or computer.

<img width="729" height="687" alt="Screenshot 2026-03-28 180335" src="https://github.com/user-attachments/assets/70779c3c-e29a-41a4-81cb-d4196a4f4a52" />


Features

Plays MP3 audio files
Ultra-compact PCB design (credit card sized)
Button-based controls (play/pause, next, previous, volume)
MicroSD storage support for music files
Low-power operation for portable use
Optional headphone or small speaker output

How It Works

The system is built around a microcontroller that reads audio files from a storage module (typically a microSD card). The audio data is decoded either by an onboard decoder chip or firmware library and then sent to an audio amplifier for output.

Button inputs are continuously read by the microcontroller to control playback state, track switching, and volume adjustment.

Hardware Used
Microcontroller (STM32F411CEU6x)
MicroSD card module
Audio DAC module 
Small audio amplifier
Tactile & low profile buttons
Lithium battery + charging circuit
PCB designed in KiCad

Wiring / Connections
MicroSD module connected via SPI
Audio module connected via I2S or analog pins
Buttons connected to digital GPIO pins with pull-ups
Battery connected through power management circuit

<img width="368" height="585" alt="Screenshot 2026-03-28 175625" src="https://github.com/user-attachments/assets/4fd8b7ca-de09-456d-a16c-0dc771e36ba9" />

The goal of this project is to create a fully functional, pocket-sized music player that is:

- as thin as possible (under 5mm)
- at least 5 hours of playing time
- able to fit in your wallet
- cheap as possible to make (under 80$ per unit after considering battery, case, shipping & PCB assembly)

The PCB files in this repository were prepared using the JLCPCB KiCad plugin to streamline manufacturing and assembly.

After completing the schematic and PCB layout in KiCad, the plugin was used to:

Generate production-ready Gerber files
Export drill files (Excellon format)
Create a complete BOM (Bill of Materials) with part numbers
Generate a CPL (Pick and Place file) for SMT assembly
Automatically align component footprints with JLCPCB’s supported parts library

i also added the project files and schematic files used for kiCad

Status

Currently in development / testing stage. PCB revisions and firmware improvements are ongoing and am trying to get my first prototype tested.

BOM MATERIALS LIST:
| Ref                                   | Qty | Value             | Footprint       | LCSC Link                                                                                                                                                                                                                            |
| ------------------------------------- | --- | ----------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Y1                                    | 1   | 16 MHz crystal    | 3225            | [https://www.lcsc.com/product-detail/Crystals_YXC-Crystal-CX3225SB16000D0FLJCC_C13738.html](https://www.lcsc.com/product-detail/Crystals_YXC-Crystal-CX3225SB16000D0FLJCC_C13738.html)                                               |
| U5                                    | 1   | TPA6132A2RTE      | WQFN-16         | [https://www.lcsc.com/product-detail/Audio-ICs_Texas-Instruments-TPA6132A2RTE_C2863070.html](https://www.lcsc.com/product-detail/Audio-ICs_Texas-Instruments-TPA6132A2RTE_C2863070.html)                                             |
| U4                                    | 1   | PCM5102A          | TSSOP-20        | [https://www.lcsc.com/product-detail/Audio-ICs_Texas-Instruments-PCM5102A_C1520792.html](https://www.lcsc.com/product-detail/Audio-ICs_Texas-Instruments-PCM5102A_C1520792.html)                                                     |
| U3                                    | 1   | USBLC6-2SC6       | SOT-23-6        | [https://www.lcsc.com/product-detail/TVS-Diodes_STMicroelectronics-USBLC6-2SC6_C7519.html](https://www.lcsc.com/product-detail/TVS-Diodes_STMicroelectronics-USBLC6-2SC6_C7519.html)                                                 |
| U2                                    | 1   | AMS1117           | SOT-223         | [https://www.lcsc.com/product-detail/Linear-Voltage-Regulators_Advanced-Monolithic-Systems-AMS1117-3-3_C6186.html](https://www.lcsc.com/product-detail/Linear-Voltage-Regulators_Advanced-Monolithic-Systems-AMS1117-3-3_C6186.html) |
| U1                                    | 1   | STM32F411CEUx     | QFN-48          | [https://www.lcsc.com/product-detail/Microcontrollers-MCU-ST-Microelectronics-STM32F411CEUx_C60420.html](https://www.lcsc.com/product-detail/Microcontrollers-MCU-ST-Microelectronics-STM32F411CEUx_C60420.html)                     |
| SW2–SW6                               | 5   | Tactile switch    | SMD push button | [https://www.lcsc.com/product-detail/Tactile-Switches_XKB-TS-1187A_C318884.html](https://www.lcsc.com/product-detail/Tactile-Switches_XKB-TS-1187A_C318884.html)                                                                     |
| SW1                                   | 1   | SPDT switch       | PCM12           | [https://www.lcsc.com/product-detail/Slide-Switches_CW-PCM12_C109335.html](https://www.lcsc.com/product-detail/Slide-Switches_CW-PCM12_C109335.html)                                                                                 |
| R15,R16                               | 2   | 5.1kΩ             | 0402            | [https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-075K1L_C25905.html](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-075K1L_C25905.html)                               |
| R13,R14                               | 2   | 10Ω               | 0402            | [https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-0710RL_C25077.html](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-0710RL_C25077.html)                               |
| R11,R12                               | 2   | 450Ω              | 0402            | [https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-07450RL_C25117.html](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-07450RL_C25117.html)                             |
| R2,R3                                 | 2   | 1.5kΩ             | 0402            | [https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-071K5L_C25867.html](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-071K5L_C25867.html)                               |
| R1,R4–R7,R9,R10                       | 7   | 10kΩ              | 0402            | [https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-0710KL_C25744.html](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0402FR-0710KL_C25744.html)                               |
| J5                                    | 1   | 3.5mm audio jack  | SMT             | [https://www.lcsc.com/product-detail/Audio-Connectors_CUI-Devices-SJ-3523-SMT_C4991872.html](https://www.lcsc.com/product-detail/Audio-Connectors_CUI-Devices-SJ-3523-SMT_C4991872.html)                                             |
| J4                                    | 1   | USB-C receptacle  | 16P USB2.0      | [https://www.lcsc.com/product-detail/USB-Connectors_XKB-Connectivity-U262-16XN-4BVC11_C2894897.html](https://www.lcsc.com/product-detail/USB-Connectors_XKB-Connectivity-U262-16XN-4BVC11_C2894897.html)                             |
| J2                                    | 1   | Micro SD socket   | TF-01A          | [https://www.lcsc.com/product-detail/Memory-Card-Sockets_Jinling-Group-TF-01A_C91145.html](https://www.lcsc.com/product-detail/Memory-Card-Sockets_Jinling-Group-TF-01A_C91145.html)                                                 |
| J1                                    | 1   | 4-pin header      | 2.54mm          | [https://www.lcsc.com/product-detail/Pin-Header-Sockets_Generic-2-54mm-pin-header_CNA.html](https://www.lcsc.com/product-detail/Pin-Header-Sockets_Generic-2-54mm-pin-header_CNA.html)                                               |
| FB1                                   | 1   | 120Ω ferrite bead | 0603            | [https://www.lcsc.com/product-detail/Ferrite-Beads_Murata-BLM18AG121SN1D_C76892.html](https://www.lcsc.com/product-detail/Ferrite-Beads_Murata-BLM18AG121SN1D_C76892.html)                                                           |
| D1,D2                                 | 2   | LED               | 0805            | [https://www.lcsc.com/product-detail/LED-Indication_YONGYUTAI-0805-LED_C2290.html](https://www.lcsc.com/product-detail/LED-Indication_YONGYUTAI-0805-LED_C2290.html)                                                                 |
| C44,C45                               | 2   | 2.2nF             | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R7BB222_C1531.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R7BB222_C1531.html)                                               |
| C23,C26,C27,C43                       | 4   | 2.2µF             | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402MRX5R5BB225_C12530.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402MRX5R5BB225_C12530.html)                                             |
| C10,C11                               | 2   | 22µF              | 0805            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_Murata-GRM21BR61A226ME44_C45783.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_Murata-GRM21BR61A226ME44_C45783.html)                                           |
| C8,C9                                 | 2   | 10pF              | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402JRNPO9BN100_C32949.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402JRNPO9BN100_C32949.html)                                             |
| C6,C7,C24,C25,C30,C31                 | 6   | 1µF               | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402MRX5R5BB105_C52923.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402MRX5R5BB105_C52923.html)                                             |
| C5                                    | 1   | 10nF              | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R9BB103_C15195.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R9BB103_C15195.html)                                             |
| C4,C15,C17,C19,C32                    | 5   | 10µF              | 0805            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_Murata-GRM21BR61A106KE19_C15850.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_Murata-GRM21BR61A106KE19_C15850.html)                                           |
| C1–C3,C12–C14,C16,C18,C22,C28–C29,C33 | 12  | 100nF             | 0402            | [https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R7BB104_C1525.html](https://www.lcsc.com/product-detail/Ceramic-Capacitors_YAGEO-CC0402KRX7R7BB104_C1525.html)                                               |


<img width="1508" height="537" alt="Screenshot 2026-03-28 184904" src="https://github.com/user-attachments/assets/5a637558-4bcc-41c8-ad8c-d06ffcc73810" />
