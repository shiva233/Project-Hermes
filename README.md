# Project Hermes

<img width="1003" height="626" alt="image" src="https://github.com/user-attachments/assets/5d83a72a-ea9e-4dfc-b0da-4932722fab98" />


> Hermes (n.): God of speed, travel, and messangers. In this incarnation he carries pixels instead of scrolls, streaming your games from your desktop to your hands :D


## What is Project Hermes?
Project Hermes is a Raspberry Pi powered game streaming handheld built for PC gamers, streamming of your games from your pc via SteamLink to the console wherever you want! (provided you have an internet connection) and since its only streaming theh games you can do this without rebuying games or paying console prices for the hardware! 


## Why did I make Project Hermes

This might sound silly but I made Project Hermes because... I really really really want it! I want something like this to use! All the handheld consoles on the market right now are way to expensive and besides that I have two big issues with all of them:

1. I can't play on the same save file as my main computer on the handheld (without some tedious work around)
2. I already have a good pc! why should I a lot of money for a handheld to run the same games slightly worse??

So I designed a handheld that fixes both of these issues! It streams directly from the main PC so all the save files are still stored on the main computer, and since its running of the main computers hardware the console can be cheaper and use less expensive hardware! The whole thing pretty much runs of a Raspberry Pi 4 and is in total cheaper than a Switch Lite :D

<img width="515" height="709" alt="image" src="https://github.com/user-attachments/assets/cfceb048-ffd1-4350-9c66-8f8eed938f32" />
<img width="1222" height="876" alt="image" src="https://github.com/user-attachments/assets/fd4e3bd9-86b3-4d73-8584-05efb4eccc81" />

## Usage

<img width="413" height="284" alt="image" src="https://github.com/user-attachments/assets/6fbe900c-c207-4854-ac27-e75d038d910b" />


Gaming PC => SteamLink => Project Hermes (Video + Audio)


Project Hermes => SteamLink => Gaming PC (Controller Input)


## Design Constraints / Goals:

- Size: Must be similar size/footprint to Steam Deck, ROG Ally or Switch (around 30cm x 11cm x 4cm) ☑️
- Price: Must be cheaper than a Switch Lite (since it can't actually run games natively and only stream its not reasonable for it to cost more than an actual console) therefore must cost less than **$260 CAD or $190 USD** ☑️
- Power: Battery Powered, chargable via USB-C while in use (aiming for around 2-3 hours) ☑️
- Compute: Be able to run SteamLink at 720p 60hz ☑️
- Display: Atleast 7 inch, 720p 60hz, HDMI compatible ☑️
- Input: Via USB HID, same layout as an Xbox controller ☑️
- Connectivity: Must be able to run off just WiFi ☑️ 
- Encolosure: Fully 3D Printed, no custom fabrication or CNC. Easily assembled with hand tools ☑️


## Anatomy of Project Hermes:

<img width="504" height="320" alt="image" src="https://github.com/user-attachments/assets/55be963d-600b-400c-b56a-53bcda2824cd" />

Raspberry Pi 4 (2 GB with cooler) + Pisugar S Pro Portable 5000 mAh UPS +  7 inch LCD Display + RP2040-Zero Custom Controller + 3D Printed Housing = Project Hermes! :D 

## BOM (Subject to Change)

| Item                                | Usage                          | Source       | Price (CAD) |
|-------------------------------------|--------------------------------|--------------|-------------|
| Raspberry Pi 4 (2 GB with cooler)   | Main Compute Unit              | AliExpress   |      $80.38 |
| Pisugar S Pro Portable 5000 mAh UPS | Battery + Power Management     | Amazon       |      $47.46 |
| 7 inch LCD Display                  | Display                        | AliExpress   |      $34.99 |
| Waveshare RP2040-Zero               | Controller Input MCU           | Self-Sourced |       $0.00 |
| Tact Switch Push Button             | Face Buttons + Utility Inputs  | AliExpress   |       $2.42 |
| Hall Effect Joystick (x2)           | Analog Thumbsticks             | AliExpress   |       $4.33 |
| Controller PCB                      | Controller PCB                 | JLCPCB       |      $25.57 |
| 3D Printed Case/Parts               |	Enclosure + Mechanical Housing | Self-Sourced |       $0.00 |
|                                     |                                | Total CAD    |     $195.15 |
|                                     |                                | Total USD    |     $142.46 |

