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
