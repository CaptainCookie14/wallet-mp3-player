# wallet-mp3-player
This project is a compact, portable MP3 player designed to fit roughly the size of a credit card. It focuses on minimal power usage, small PCB design, and simple user controls for playing music from onboard or external storage.

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
Reference	Qty	Value	DNP	Exclude from BOM	Exclude from Board	Footprint	Datasheet	LSCS
Y1	1	16mhz				Crystal:Crystal_SMD_3225-4Pin_3.2x2.5mm		C13738
U5	1	TPA6132A2RTE				Package_DFN_QFN:WQFN-16-1EP_3x3mm_P0.5mm_EP1.6x1.6mm_ThermalVias	https://www.ti.com/lit/ds/symlink/tpa6132a2.pdf	C2863070
U4	1	PCM5102A				Package_SO:TSSOP-20_4.4x6.5mm_P0.65mm	https://www.ti.com/lit/ds/symlink/pcm5102a.pdf	C1520792
U3	1	USBLC6-2SC6				Package_TO_SOT_SMD:SOT-23-6	https://www.st.com/resource/en/datasheet/usblc6-2.pdf	C7519
U2	1	AMS1117				Package_TO_SOT_SMD:SOT-223-3_TabPin2	http://www.advanced-monolithic.com/pdf/ds1117.pdf	C6186
U1	1	STM32F411CEUx				Package_DFN_QFN:QFN-48-1EP_7x7mm_P0.5mm_EP5.6x5.6mm	https://www.st.com/resource/en/datasheet/stm32f411ce.pdf	C60420
SW2,SW3,SW4,SW5,SW6	5	SW_Push				Button_Switch_SMD:SW_Push_1P1T_XKB_TS-1187A		C318884
SW1	1	SW_SPDT				Button_Switch_SMD:SW_SPDT_PCM12		 C109335
R15,R16	2	5k1				Resistor_SMD:R_0402_1005Metric		C25905
R13,R14	2	10ohm				Resistor_SMD:R_0402_1005Metric		C25077
R11,R12	2	450				Resistor_SMD:R_0402_1005Metric		C25117
R2,R3	2	1.5k ohm				Resistor_SMD:R_0402_1005Metric		C25867
R1,R4,R5,R6,R7,R9,R10	7	10k				Resistor_SMD:R_0402_1005Metric		C25744
J5	1	AudioJack3				Connector_Audio:Jack_3.5mm_CUI_SJ-3523-SMT_Horizontal		C4991872
J4	1	USB_C_Receptacle_USB2.0_16P				Connector_USB:USB_C_Receptacle_HCTL_HC-TYPE-C-16P-01A	https://www.usb.org/sites/default/files/documents/usb_type-c.zip	C2894897
J2	1	Micro_SD_Card				sd_card_socket:TF-01A	https://www.we-online.com/components/products/datasheet/693072010801.pdf	C91145
J1	1	Conn_01x04_Pin				Connector_PinHeader_2.54mm:PinHeader_1x04_P2.54mm_Vertical		
FB1	1	120 ohms @ 100 mhz				Inductor_SMD:L_0603_1608Metric		C76892
D1,D2	2	LED				LED_SMD:LED_0805_2012Metric		C2290
C44,C45	2	2.2n				Capacitor_SMD:C_0402_1005Metric		 C1531
C23,C26,C27,C43	4	2u2				Capacitor_SMD:C_0402_1005Metric		C12530
C10,C11	2	22u				Capacitor_SMD:C_0805_2012Metric		C45783
C8,C9	2	10p				Capacitor_SMD:C_0402_1005Metric		C32949
C6,C7,C24,C25,C30,C31	6	1uf				Capacitor_SMD:C_0402_1005Metric		C52923
C5	1	10n				Capacitor_SMD:C_0402_1005Metric		C15195
C4,C15,C17,C19,C32	5	10u				Capacitor_SMD:C_0805_2012Metric		C15850
C1,C2,C3,C12,C13,C14,C16,C18,C22,C28,C29,C33	12	100n				Capacitor_SMD:C_0402_1005Metric		C1525
<img width="865" height="813" alt="image" src="https://github.com/user-attachments/assets/a061a979-f948-44e8-b7bb-bfc450ce2f27" />

