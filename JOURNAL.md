---
title: Project Hermes
author: Shiva Prakash
description: Project Hermes is a handheld console designed for people who already own gaming PCs so they can stream their games via SteamLink so they can take it anywhere for cheap! 
created_at: 2025-07-19
---
# Project Hermes Devlog / Creation Journal
----

# Total time spent: 24h (wow I did not expect such a nice number) 

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


**Total Time Spent: 1h**


# July 25th - I will finish this today >:)

<img width="1069" height="424" alt="image" src="https://github.com/user-attachments/assets/5ccb2082-87a1-4c5a-9c42-7eb54794df27" />
So I got all the electronics into my cad!! but it ended up being chunkier than I wanted to so I could fit the Pi and PCB :(

Im gonna experiment a bit but now all I need to do is add shoulder buttons and buttons for everything else and I should be good?? :D

Oki I added the buttons and stuff but I am still unhappy with how chonky it is:
<img width="843" height="446" alt="image" src="https://github.com/user-attachments/assets/7c7c19f8-2908-442d-bd4a-9744fced6d13" />
<img width="747" height="310" alt="image" src="https://github.com/user-attachments/assets/df468bc1-d483-45e0-9353-6de850353458" />

Im gonna mess around with a few different orientations for the pi and see what happens, but this is really annoying me. Worst case scenario I submit it like this (chonky boi) and then redesign it later after I have it built because I have a 3D printer. While it isnt perfect I do want to keep the deadline in mind and not do it too last minute for the reviewers

# Update 1:

OK this is a bit unorthadox and definetly is not ideal but I pushed the pi to the left side of the console instead of the middle so that the pcb lays flush with the side without the tall USB 3.0 ports. this is a bit weird because I would have to slightly trim the gpio headers on the pi but if I can make it thinner by doing this I think ima go for it

<img width="743" height="567" alt="image" src="https://github.com/user-attachments/assets/45c7ab7b-5932-463a-90a2-e34e4c4969c8" />
these lil guys poking through need a lil haircut >:D

**obviously if anyone else wants to build this they would have to do the same thing and trim the gpio pins or reposition the Pi which is why it is not ideal** in a future revision (if I ever decide to upgrade it or maybe try and sell project hermes) I would probably use a thinner board like the pi4 compute with a hat for IO or maybe design my own SBC for this project but thats way to big of a task for me currently (based on my experience and obv the time constraint) which is why I am going with this work around 

I will try my best to document the assembly instructions so if anyone does want to build this they can easily replicate the workaround I did :D 

# Update 2: 

AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA WHY DOES IT KEEP BREAKING WHEN I TRY TO MAKE IT LESS CHONKY:
<img width="202" height="158" alt="image" src="https://github.com/user-attachments/assets/1cf4c96c-dabc-44c2-b693-300092ba616e" />

<img width="904" height="642" alt="image" src="https://github.com/user-attachments/assets/e6618b98-0ba5-4e90-b678-0e65149a848a" />

<img width="431" height="167" alt="image" src="https://github.com/user-attachments/assets/bfb8e5b9-ba8b-4b23-a74f-d28af5d0062b" />


WHERE DID MY SHELL GO??? im about to crash out and punch my monitor

![break-monitor](https://github.com/user-attachments/assets/cede4fda-c61d-462d-ae65-689f97ca5b2d)

# Update 3:

ok it has gotten a little better here is where I am now:

<img width="1108" height="546" alt="image" src="https://github.com/user-attachments/assets/2529615a-dc6e-4648-ac69-122d78a6a462" />
... im gonna cry

Ok I messed around with the form more and I guess this is progress??? 
<img width="1361" height="724" alt="image" src="https://github.com/user-attachments/assets/d840c01a-eaed-4912-a3d2-46394931fadb" />

HOW THE FLIP DO I EVEN FIX THIS MAN

# Update 4: 

YIPPEEE IT WORKS IT WORKS IT WORKS AND ITS LESS CHONKY :D

<img width="1170" height="666" alt="image" src="https://github.com/user-attachments/assets/5d6b6c92-03e9-484d-81d2-1985a0409b29" />

YAYYY

also also added the usb-c charging port :D 

<img width="813" height="593" alt="image" src="https://github.com/user-attachments/assets/89252c2c-d777-477b-be83-13af615c8c5e" />

Now all I need to do is add the shoulder button holes and I should officially be ready to submit! (I dont know how to add the shoulder buttons though they are at an akward angle ;-;..) ohh well I will take a break and tackle it later

# Update 5: 

TADAAA THE SHOULDER BUTTONS ARE DONNE THIS TOOK WAYY TO LONG CUZ ONE OF THEM HAD TO BE AT AN ANGLE AND I DIDNT KNOW HOW TO DO THAT BUT I DID IT YIPPEEE:

<img width="701" height="388" alt="image" src="https://github.com/user-attachments/assets/5f907a9f-85e3-41f5-ad46-54e74c1bd0d7" />

now I would love to say thats it and I can submit now... but I noticed this:

<img width="951" height="402" alt="image" src="https://github.com/user-attachments/assets/e990be36-1358-491f-babb-1e4b59956f36" />

the screen is slightly poking out.

![dog-sunset-javgag](https://github.com/user-attachments/assets/58d2fd61-fb2a-4195-bd81-c00930635259)

well time to fix that and hopefully nothing breaks :D

NO NO NO NO 

<img width="1164" height="621" alt="image" src="https://github.com/user-attachments/assets/b8935c3b-8884-4a80-aae0-acd3010c1941" />
WHY DID IT BREAK AGAIN NO IM GONNA CRASH OUT

OK IM GONNA TRY AGAIN THIS TIME JUST MOVING 4 FACES BY ONLY **1 MILIMETER** IF THIS BREAKS IT MY MONITOR WILL NOT BE SAFE

<img width="1457" height="805" alt="image" src="https://github.com/user-attachments/assets/dcdbe78a-0c23-4eeb-a5e5-4c18a8c8f429" />

no freaking way.

![drakendedyou](https://github.com/user-attachments/assets/ba28d5b0-bfb8-4b5f-a841-723233d90c2d)
^ live view of me tweaking the fuck out it is 2:30 AM right now.

Am I Sisphys?

Eternally doomed king of Ephyra

Forced to roll the same boulder up the hill only for it to fall down again?

how many times must I edit the form, click finish form only to see everything break and click ctrl-z

just to roll it up the hill again 


# Update 6:

IT WORKED IT OWRKED IT WORKED IT OWRKEDHJ

IM DONE

<img width="1124" height="477" alt="image" src="https://github.com/user-attachments/assets/b19dda4e-a874-4b19-aa0f-390e3b603394" />

IM FINALLY DONE THE CAD AND THAT MARKS THE END OF THE DESIGN PHASE FOR THIS PROJECT! I CAN SUBMIT IT TO HIGHWAY AND GET MY GRANT AFTER I FINISH THE README YIPPEEEEEEE

![freedom-chain](https://github.com/user-attachments/assets/46acb060-2476-4ac0-b2ee-cac2d54a7dfa)

if you got all the way here thank you for reading: here is the final cad :D

<img width="1003" height="626" alt="image" src="https://github.com/user-attachments/assets/fa448558-1425-4072-8ea3-53938f473191" />


after 51 revisions.. 

<img width="510" height="66" alt="image" src="https://github.com/user-attachments/assets/b98000a0-f7a8-4eeb-b8c4-804fdfd3f36c" />

**Total time spent today: 5 whole hours 😭 I HATE CAD BUT ALSO IM SO PROUD AAA**
