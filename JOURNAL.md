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


# June 20th - Sketch and hopefully CAD!

I made a sketch on my tablet of what I want it to look like! It obviously took some very heavy inspo from the ROG Ally and MSI Claw but since those are both proven designs with good ergonomics, why not!!

<img width="1222" height="876" alt="image" src="https://github.com/user-attachments/assets/860b4a48-5dbc-47ce-94a7-ee61a4cb895b" />

Update 1:

I spent a LOT of time trying to figure out this CAD Model, this is where I am so far :D

<img width="1025" height="547" alt="image" src="https://github.com/user-attachments/assets/087f9050-ec20-47d9-85c7-e87c9c29651c" />

<img width="624" height="375" alt="image" src="https://github.com/user-attachments/assets/da9756a7-8e93-4a57-b876-b3dc039939c2" />

<img width="1124" height="623" alt="image" src="https://github.com/user-attachments/assets/399c30f4-835f-4b46-b6a6-e182a1671b21" />

I am still very new to cad so this took me 3 hours to make 😭 but its okay!! progress is progress right?? :D

**Total Time Spent Today: 3.5h**


# June 21st - DID A LOTT OF CAD and tested ergonomics!

omg omg so I think I am pretty much where I want to be with the CAD/3d model!! 

TADA:

<img width="790" height="378" alt="image" src="https://github.com/user-attachments/assets/26e54238-e8ca-4937-ba8a-61f85d0cc06d" />
<img width="739" height="418" alt="image" src="https://github.com/user-attachments/assets/0ebabf33-c904-4e12-913f-43290b33957a" />
<img width="422" height="374" alt="image" src="https://github.com/user-attachments/assets/b347d0fa-d9f7-4d88-bf69-131d52a36fc8" />


I am very proud of this model but it took me a WHILE to do.

I also 3d printed the controller sides to see how they feel in my hands and if the placement of everything made sense, decided they didnt make sense so moved stuff around and reprinted it :D

<img width="4032" height="3024" alt="image" src="https://github.com/user-attachments/assets/2a0d94aa-3c74-4862-8e32-2a4006f4b737" />
<img width="1032" height="397" alt="image" src="https://github.com/user-attachments/assets/5c8e93c5-4cf0-4cb3-b2a9-c1939531ca4f" />

anyways now that I roughly know where I want everything to be placed I can move on the PCB design tmrw :D

**Total time spent today: 3h** 

# June 22nd - PCB time!

Before I get started with the schematic or any actual routing I realized I needed to figure out how to line up everything on the PCB to the way I wanted it on the 3D Model. I didnt know how to do this at first and I could not find much cuz most videos/tutorials online were PCB to 3D model not the other way around. Then I found a tutorial showing me how to export my sketch as DFX file and import that to KiCad. Thats exactly what I did and tada!

<img width="1169" height="659" alt="image" src="https://github.com/user-attachments/assets/b368d1f1-160d-452f-aeb3-b74e876b4d9e" />

I can line it all up now :D and this is to scale as well!! Alright time to work on the schematic and think about wiring hmhmhm


Update 1:

Done the schematic except for the joysticks cuz im lowkey a bit confused about that and need to research that more 

<img width="1617" height="537" alt="image" src="https://github.com/user-attachments/assets/46fbd765-ba67-45e4-ad3c-6ea7ca96f202" />

And you may have noticed that I am not using a raspberry pico in this schematic... and thats because I had to switch to a **waveshare rp2040-zero!** this is because I realized the Raspberry Pico only has **3 analog pins** and each joystick requires 2 analog pins, soooo 2x2=4 meaning I need 4 analog pins which the pico does not have D: fortunately rp2040-zero has exactly 4 :D

so yeah the joysticks actually seem kinda confusing cuz there are so many different versions of them so I need to research it more but I might try and finish the rest of the PCB before that if I can :0 

Also also also I added colors to the 3d model cuz why not :D

<img width="1522" height="789" alt="image" src="https://github.com/user-attachments/assets/c37567a1-3043-4167-b435-6420e9ed4c04" />

Upadte 2:

<img width="1087" height="459" alt="image" src="https://github.com/user-attachments/assets/35d34182-bf53-4748-a8e6-aa704fda9018" />

Placed all the components besides the joysticks! will route tmrw cuz its 4 am and I am sleepy

**Total Time Spent today: 3h**

# July 23rd - IM GONNA FINISH THE PCB TODAY RAHHH

<img width="1623" height="602" alt="image" src="https://github.com/user-attachments/assets/1b927774-2598-4c8b-bc66-b2fb2a93f027" />

hi hi! this is where I am with the PCB so far! you might have noticed: shiva you dummy u did not put the joystick footprints in! and yes I know that, but like I said yesterday there were a lot of different footprints for the joystick and I got confused so instead of feeling overwhelmed I tried to route everything else beforehand. obv I will have to redo a lot of this once the joysticks are here but now I have the confidence to route stuff properly :D this took me around an hour to route properly :0 

Update 1:

tada!! I figured out the wiring for the joysticks :D 

<img width="890" height="823" alt="image" src="https://github.com/user-attachments/assets/65230a66-989d-4820-a518-f7b6b5bfbbc8" />

I figured it out by looking at a sparkfun breakout board for a joystick so i will explain it here:

As u can see the symbol is split into 4 parts V, H, SEL and SHIELD

V: is the vertical axis
H: is the horizontal axis
SEL: is the button when you push down on the joystick
Shield: these just dont get connected :0

So V+ and H+ are voltage so they go to 3.3v on the RP2040-Zero, V- and H- go to ground (so does SEL-). and finally H and V are the values we are actually gonna be reading and they go to the Analog gpio pins on the RP2040-Zero. The RP2040-Zero has 4 Analog pins like I said earlier and thats exactly how many we need because H and V for LS and H and V for RS. These pins are GPIO 26,27,28, and 29:

<img width="1088" height="558" alt="image" src="https://github.com/user-attachments/assets/1e8fbc6b-af3f-4d73-a4a5-99039fb5ef51" />
 
and then finally for the buttons I wired SEL+ on RS to GPIO14 and GPIO15 on LS

So yippee!! 

here is the completed schematic :D

<img width="1179" height="587" alt="image" src="https://github.com/user-attachments/assets/f5523484-babc-44de-ac6d-27dc5ce70fc9" />

now I just gotta do the routing for the joysticks and I think I can probably finish this project today (this is assuming trying to cad the electronics does not kill me)

oh my god this took wayy to long because I was being silly but I finished the routing which means im done with the PCB YIPPEEEEE:

<img width="1453" height="459" alt="image" src="https://github.com/user-attachments/assets/dd1d9f81-1288-4eb8-815d-b8517955c266" />

:D

Time to work on the CAD assembly... (this is going to kill me.)

**Total Time Spent: 5.5h** (Blame me being bad at routing

# July 24th - ITS ALL COMING TOGETHER NOW!

I split the body and I learned how to use shell to hollow it out for th components!! TADAA:

<img width="951" height="536" alt="image" src="https://github.com/user-attachments/assets/56bbb6e1-4943-477d-bf5d-773e25bc580c" />
<img width="959" height="481" alt="image" src="https://github.com/user-attachments/assets/66cd6f4b-75c1-495a-97d7-f9c4b3754b0f" />

I did not think this would work first try but im glad it did :D

also also also I have found 3d models for the Pi, Screen, and obv I have the model of the PCB from kicad :DD Now I just need to find a model of the pisugar (power supply/battery) online and I can wrap this up hopefully today mwehehe

# Update 1:

I have found a model for the PiSugar! which means I have all the models I need to finish the CAD YIPPEE
<img width="749" height="224" alt="image" src="https://github.com/user-attachments/assets/64e7fc32-9856-4cc6-89ed-54e3d15e30b4" />

