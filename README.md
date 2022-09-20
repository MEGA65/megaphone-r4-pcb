# megaphone-pcb-2020

This repository contains the PCB design for the MEGAphone R4 board.

This work was supported by the NLnet Foundation, for which we are extremely grateful. With their support we are very pleased to make these designs available on an open-source basis under the GPLv3.

The focus of this iteration of the PCB design was to get the power management system implemented, so that the device can charge its own battery from mains, USB, a car 12V accessory outlet or a solar panel. This will also allow the inclusion of a solar panel in the device, thus allowing it to in theory have infinite battery life / energy self-sufficiency, which would be very helpful for people living in isolated areas, or where power is unreliable for various reasons.

Other significant changes are the inclusion of a place for a Pi Compute Module 4, so that Android can be run in a secure sand-box, if required, and a general reworking to reduce the outline size of the PCB somewhat.  Support has also been added for various add-on modules for backup communications channels, as well as moving the audio circuitry to a pluggable module, so that Bluetooth and audio amplifiers and filters can be iterated separately from the rest of the PCB.
