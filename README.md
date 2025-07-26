# Project Hermes

<img width="1003" height="626" alt="image" src="https://github.com/user-attachments/assets/5d83a72a-ea9e-4dfc-b0da-4932722fab98" />


> Hermes (n.): God of speed, travel, and messangers. In this incarnation he carries pixels instead of scrolls, streaming your games from your desktop to your hands :D


## What is Project Hermes?
Project Hermes is a Raspberry Pi powered game _**streaming**_ handheld built for PC gamers, streaming of your games from your pc via SteamLink to the console wherever you want! (provided you have an internet connection) and since its only streaming the games you can do this without rebuying games or paying console prices for the hardware! 


## Why did I make Project Hermes

This might sound silly but I made Project Hermes because... I really really really want it! I want something like this to use! All the handheld consoles on the market right now are way to expensive and besides that I have two big issues with all of them:

1. I can't play on the same save file as my main computer on the handheld (without some tedious work around)
2. I already have a good pc! why should I a lot of money for a handheld to run the same games slightly worse??

So I designed a handheld that fixes both of these issues! It streams directly from the main PC so all the save files are still stored on the main computer, and since its running of the main computers hardware the console can be cheaper and use less expensive hardware! The whole thing pretty much runs of a Raspberry Pi 4 and is in total cheaper than a Switch Lite :D

<img width="515" height="709" alt="image" src="https://github.com/user-attachments/assets/cfceb048-ffd1-4350-9c66-8f8eed938f32" />
<img width="1222" height="876" alt="image" src="https://github.com/user-attachments/assets/fd4e3bd9-86b3-4d73-8584-05efb4eccc81" />

## Design Constraints / Goals:

- Size: Must be similar size/footprint to Steam Deck, ROG Ally or Switch (around 30cm x 11cm x 4cm) ☑️ (well... except for that 4cm part it ended up being a lil bit more chonky lol!!)
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


## 3D Model

<img width="872" height="348" alt="image" src="https://github.com/user-attachments/assets/5f1276e5-3d10-4f35-bf33-311273b4e003" />



## Controller PCB:

<img width="1468" height="777" alt="image" src="https://github.com/user-attachments/assets/5630e20a-485d-4203-a1d7-e592746b57e0" />
<img width="1582" height="491" alt="image" src="https://github.com/user-attachments/assets/79acefe4-89cc-409f-9546-678083317982" />
<img width="1470" height="477" alt="image" src="https://github.com/user-attachments/assets/d1333003-bc9b-4d26-b2fc-6ea7278ec6f6" />

## Wiring / Cable fun

Display: Hdmi to Micro Hdmi + Power mico-usb that both plug into the Pi

Controller: USB-C to USB-A that plugs into the Pi

Battery: its a hat! 

Shoulder Buttons: Shoulder buttons may be hand wired to the PCB with a wire extending it :O

## Firmware

ok this part is important and might be confusing, Project Hermes uses two layers of firmware/software:

### 1. Raspberry Pi 4 - SteamLink Client

<img width="250" height="83" alt="Raspberry_Pi_OS_Logo" src="https://github.com/user-attachments/assets/f675ae30-a4a0-4a15-9b26-a391e9c8d25a" />
<img width="213" height="142" alt="image" src="https://github.com/user-attachments/assets/6fbe900c-c207-4854-ac27-e75d038d910b" />

The Raspberry Pi 4 will be running Raspberry Pi OS with the official SteamLink client downloaded onto it (might also add a script that makes SteamLink automatically launch every time the Pi is booted :0).

SteamLink Handles this:

- Video/Audio: It takes the video and audio from your computer and streams it to the Pi!
- It also takes inputs from the controller on Project Hermes and sends it back to your computer

So basically:

Gaming PC => SteamLink => Project Hermes (Video + Audio)

Project Hermes => SteamLink => Gaming PC (Controller Input)

This makes it so all the heavy lifting/processing power is done by your PC and the Pi just becomes the bridge the carries the pixels (video/audio) in one direction and controller signals in the other (just like Hermes!!).

### 2. Custom Controller - [GP2040-CE Firmware](https://github.com/OpenStickCommunity/GP2040-CE)

<img width="342" height="100" alt="gp2040-ce-logo" src="https://github.com/user-attachments/assets/297c4362-7481-4f5f-9468-7520bdaba086" />

- The RP2040-Zero microcontroller inside the controller PCB will be running [GP2040-CE, which is an opensource firmware deisnged for game controllers! ](https://github.com/OpenStickCommunity/GP2040-CE)
What GP2040-CE does:
- Turns the controller into a USB HID! Basically this means that the Pi and PC see it as a standard controller just like an Xbox controller
- Handles all the button presses, D-pad inputs, and analog signals from the joysticks (which the Pi cannot do btw since it does not have analog pins to my knowledge) and then sends them as input data over USB to the Pi.
- It's low latency and fully compatible with SteamLink, which means your computer treats Project Hermes like a normal controller with no special drivers or extra setup :D
- LOOK INTO GP2040-CE AND SUPPORT THEM THEY ARE SO COOL RAHHHH >:O

Why This Setup?

- No custom firmware: Since GP2040-CE is highly optimized for gaming responsiveness (fancy shamncy way of saying its low latency ig) and supports all the features I need for this project without :DD
- Plug and play: this one is kinda self explantory but it makes sure that I can just plug in USB and immediately start using it as a controller without having the Raspberry Pi guess what the controller is or anything like that
- Reliability: Using a seperate dedicated microcontroller for the input reduces latency and avoids weird input issues (take this with a grain of salt this is what I infered from other handheld console projects online) 
 

## BOM

| Item                                | Usage                        | Source       | Link                                        | Price (CAD) |
|-------------------------------------|------------------------------|--------------|---------------------------------------------|-------------|
| Raspberry Pi 4 (2 GB)               | Computer                     | AliExpress   |           https://a.aliexpress.com/_mrh0oph |      $80.38 |
| Pi 4 Cooling Fan                    | Cooling                      | Ali Express  |           https://a.aliexpress.com/_mOZZjXv |       $5.67 |
| Pisugar S Pro Portable 5000 mAh UPS | Power Supply / Bank          | Amazon       | https://www.amazon.ca/gp/product/B097RCFHD2 |      $47.46 |
| 7 inch LCD Display                  | Display                      | AliExpress   |           https://a.aliexpress.com/_mPIB3Jt |      $34.99 |
| Waveshare rp2040-Zero               | Controller Microcontroller   | Self-Sourced |                                         N/a |       $0.00 |
| Tact Switch Push Button             | Controller Buttons + Trigger | AliExpress   |           https://a.aliexpress.com/_mMydiq7 |       $2.42 |
| Analog Effect Joystick              | Controller Joysticks         | AliExpress   |           https://a.aliexpress.com/_mNbLpIn |       $4.33 |
| Controller PCB                      | Controller PCB               | JLCPCB       |                                         N/a |      $25.76 |
| 3D Printed Case/Parts               | Housing/Buttons              | Self-Sourced |                                         N/a |       $0.00 |
|                                     |                              |              |                                   Total CAD |     $201.01 |
|                                     |                              |              |                                   Total USD |     $146.74 |

(that's cheaper than a Switch Lite :O)
