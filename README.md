# Project-Hermes

> Hermes (n.): God of speed, travel, and messangers. In this incarnation he carries pixels instead of scrolls, streaming your games from your desktop to your hands.

Project Hermes is a handheld "console" designed for people who already own gaming PCs so they can stream their games via SteamLink so they can take it anywhere for cheap!

<img width="515" height="709" alt="image" src="https://github.com/user-attachments/assets/cfceb048-ffd1-4350-9c66-8f8eed938f32" />

## Usage


Gaming PC => SteamLink => Project Hermes (Video + Audio)


Project Hermes => SteamLink => Gaming PC (Controller Input)


## Design Constraints / Goals:

- Size: Must be similar size/footprint to Steam Deck, ROG Allay or Switch (around 30cm x 11cm x 4cm)
- Price: Must be cheaper than a Switch Lite (since it can't actually run games natively and only stream its not reasonable for it to cost more than an actual console) therefore must cost less than **$260 CAD or $190 USD**
- Power: Battery Powered, chargable via USB-C while in use (aiming for around 2-3 hours)
- Compute: Be able to run SteamLink at 720p 60hz
- Display: Atleast 7 inch, 720p 60hz, HDMI compatible
- Input: Via USB HID, same layout as an Xbox controller
- Connectivity: Must be able to run off just WiFi
- Encolosure: Fully 3D Printed, no custom fabrication or CNC. Easily assembled with hand tools.


## Anatomy of Project Hermes:

<img width="504" height="320" alt="image" src="https://github.com/user-attachments/assets/55be963d-600b-400c-b56a-53bcda2824cd" />

Raspberry Pi 4 (2 GB with cooler) + Pisugar S Pro Portable 5000 mAh UPS +  7 inch LCD Display + Raspberry Pico Custom Controller + 3D Printed Housing = Project Hermes! :D 

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

