---
title: Project Hermes
author: Shiva Prakash
description: Project Hermes is a handheld "console" designed for people who already own gaming PCs so they can stream their games via SteamLink so they can take it anywhere for cheap! 
created_at: 2025-07-19
---
# Project Hermes Devlog / Creation Journal
----

# July 18th - Planning/Research

Hi hi this is my devlog/journal for Project Hermes! 

Project Hermes is a handheld "console" designed for people who already own gaming PCs so they can stream their games via SteamLink so they can take it anywhere for cheap! I want to make this so that I can play the games from my PC wherever I want without having to buy all of them on a handheld console or pay the handheld console prices. 

The goal is to have 720p 60hz streaming from my personal pc to the handheld so I can play whatever games I want wherever :D.

After a lot of thinking and research today I was able to figure out what parts I wanted and decide on the design constraints which I have pasted below:

## Design Constraints / Goals:

- Size: Must be similar size/footprint to Steam Deck, ROG Allay or Switch (around 30cm x 11cm x 4cm)
- Price: Must be cheaper than a Switch Lite (since it can't actually run games natively and only stream its not reasonable for it to cost more than an actual console) therefore must cost less than **$260 CAD or $190 USD**
- Power: Battery Powered, chargable via USB-C while in use (aiming for around 2-3 hours)
- Compute: Be able to run SteamLink at 720p 60hz
- Display: Atleast 7 inch, 720p 60hz, HDMI compatible
- Input: Via USB HID, same layout as an Xbox controller
- Connectivity: Must be able to run off just WiFi
- Encolosure: Fully 3D Printed, no custom fabrication or CNC. Easily assembled with hand tools.

And here is the list of parts that I decided on today:


## BOM (Subject to Change)

| Item                                | Usage                          | Source       | Price (CAD) |
|-------------------------------------|--------------------------------|--------------|-------------|
| Raspberry Pi 4 (2 GB with cooler)   | Main Compute Unit              | AliExpress   |      $80.38 |
| Pisugar S Pro Portable 5000 mAh UPS | Battery + Power Management     | Amazon       |      $47.46 |
| 7 inch LCD Display                  | Display                        | AliExpress   |      $34.99 |
| Raspberry Pico                      | Controller Input MCU           | Self-Sourced |       $0.00 |
| Tact Switch Push Button             | Face Buttons + Utility Inputs  | AliExpress   |       $2.42 |
| Hall Effect Joystick (x2)           | Analog Thumbsticks             | AliExpress   |       $4.33 |
| Controller PCB                      | Controller PCB                 | JLCPCB       |       38.45 |
| 3D Printed Case/Parts               |	Enclosure + Mechanical Housing | Self-Sourced |       $0.00 |
|                                     |                                | Total CAD    |     $208.03 |
|                                     |                                | Total USD    |     $151.86 |


The design constraints should be pretty self explanatory but I will explain why I chose each of the parts ish: 

- Raspberry Pi 4 (2 GB with cooler): I choose this because it was the simplest way I could think of to run SteamLink on a handheld. Raspberry Pi 4 has already been proven to be able to run Steam Link at 1080p 60hz :D
- Pisugar S Pro Portable 5000 mAh UPS: Its a portable power supply for the Raspberry Pi! It plugs right in and it provides enough for this build :DD
-  7 inch LCD Display: This one should be self-explanatory lol!!
- Raspberry Pico: The raspberry pico is going to be the brains of the controller/input and it will plug into the Raspberry Pi 4 as a usb device to be the controller. I am going to be using the opensource project [gp2040-ce](https://gp2040-ce.info/) for the firmware of the controller but more on that in a bit.
- Tact Switch Push Buttons: This is going to be all the buttons on the controller so AXYB, DPAD, Start/Select, Shoulder Buttons/Triggers!
- Hall Effect Joysticks: These are the type of joysticks used in ps5 and xbox controllers! I need to figure out how to use them in a DIY project tho :0 (that being said [gp2040-ce](https://gp2040-ce.info/) seems to have a lot of documentation for this so yay!
- Controller PCB: All of the controller stuff/input is going to be on its own PCB with the Raspberry Pico that then plugs into the Rapsberry Pi 4
- 3D Printed Case/Parts: Self-explanatory lol


<img width="1105" height="759" alt="image" src="https://github.com/user-attachments/assets/c5a6e235-d192-42d9-9bdb-0e6776b29734" />

^ Some conecpt art and planning :D

Anyways this took me a while trying to figure out everything I needed and finding the right parts (especially powering this damm thing that was so annoying to figure out)

**Total Time Spent Today: 3h**
