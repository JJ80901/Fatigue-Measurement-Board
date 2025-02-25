# Fatigue-Measurement-Board
**Precision Displacement Sensing**

This board is designed to process and digitize a ±10V analog signal from a laser displacement sensor, ensuring high-fidelity data acquisition for fatigue testing applications. 

The signal enters through a BNC connector, passes through ESD protection and an RF filter, and is then scaled down to a ±1.65V range using a resistor divider. A non-inverting summing amplifier shifts the signal into a 0-3.3V range, with a 1.65V bias generated by an op-amp follower from a half-resistor divider off the 3.3V power rail.

To prevent aliasing, the conditioned signal passes through a third-order Butterworth Sallen-Key low-pass filter with a 5kHz cutoff frequency, optimized for sampling rates up to 1kHz. The filtered signal is digitized by an ADC141S626 14-bit ADC, which interfaces over SPI with an STM32F103CBT6 microcontroller, responsible for managing data acquisition and transmission.

Power is regulated using a TLV62569 switching regulator for 3.3V conversion and an HT7533-1 LDO, ensuring clean and stable power for the analog front end and microcontroller. 

This design improves upon earlier iterations by incorporating better filtering, precise voltage scaling, and a high-resolution ADC, making it ideal for fatigue analysis, precision displacement measurement, and other high-accuracy signal acquisition applications.

---

### What you'll find in this repository:
- Hardware designs (made in KiCad)
- STM32 Application Notes
- Device datasheets
- Circuit simulations

---

### Repository Project Structure:
- *3D Models* - Models for PCB components not found in the standard KiCad library
- *BOM* - An interactive HTML bill of materials (generated from the *Interactive HTML BOM* Plugin)
- *Datasheets* - Datasheets for specific devices used, such as the buck converter, LDO, Op-Amp, etc.
- *Docs* - STM32 application notes for crystal and USB design
- *Fatigue Test Board* - KiCad design files
- *Images* - High quality renderings of the final PCB in 3D
- *Libraries* - Folders to include schematic symbols and footprints for components not found in the standard KiCad library
- *Outputs* - Gerber files for manufacturing the PCB
- *Schematics* - PDFs of entire PCB schematic
- *Simulations* - LTSpice simulation block with any custom component libraries

---
***Disclaimer**: This board is ordered, but not yet tested!*