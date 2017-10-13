---
title: SDVX CON
---

# SDVX PC Controller (DIY)

>Last update: July 31th 2017
- Finished controller, check out the video at the end of the page.
- Fixed position of the knobs. Check the github page.
- Fixed box measures
- Added gallery album
- Added To Do List
>2017-08-10 Fixed LED pins on the table. Thanks RockyMadia for the help.


![enter image description here](http://imgur.com/4ZYRcuI.jpg)

Many thanks to:

- [LEONARDOjoy](https://sdvxdiy.github.io/) 
For the style and useful info.

- User WAFU from the Ainsun Discord for building the firmware for the Teensy.

- User BonDiggity from the Cons&Stuff Discord for helping me out with some files missing in the code and also for some nice circuit board ideas.


## Other Projects:

1. [Beatmania IIDX Controller, with CAD files to make the box look amazing](http://consandstuff.github.io/rhythmcons/beatmania-iidx/iidx-small)
2. [IIDX - SDVX Hybrid Controller (incomplete)](http://consandstuff.github.io/rhythmcons/beatmania-iidx/iidx-hybrid)
3. [Soundvoltex Minicon for $90](http://consandstuff.github.io/rhythmcons/sound-voltex/sdvx-minicon)

### TO DO List:

- Add skins to download

<hr>

# Index

1. Introduction
2. Variations
3. Code
4. Parts List / Hardware
5. Parts List / Building Materials
6. Assembly /Building the controller
7. Software & Wiring
8. Gallery
9. Troubleshooting

<hr>

## Introduction

Step by step instructions to build a Sound Voltex Controller for PC. The final product will resemble a DJ DAO SVSE controller in it's dimensions and keyboard layout. 

The main board will be a Teensy 3.2, and alternatively a Leonardo Arduino PCB.

The source of the information was collected by me, and I also used info from some other sources, like the code and measurements.

The Leonardo code is a modification of another tutorial you can see here: [github user 4yn](https://github.com/4yn/iivx)

The Teensy 3.2 firmware was made by user WAFU from the Ainsun Discord server, and I don't have the source, only the firmware file ready to upload. If you're reading this WAFU come to my discord! I don't know how else to credit you.


<hr>

## Variations

The code and CAD files included will let you make a SOUND VOLTEX controller.

Included in this tutorial are two versions on how to aproach this:

* Teensy 3.2 controller
	* Difficulty: medium-hard
	* Costs: expensive alternative
	* Pros: modable, code ready to upload
	* Cons: messy work, need soldering skills

* Arduino Leonardo controller
	* Difficulty: medium-hard
	* Costs: cheaper alternative
	* Pros: modable, friendly code
	* Cons: messy work, needs some coding skills, need soldering skills
	* 
For both versions the box is exactly the same, the only thing that'll change is the wiring stuff at the end.
Included there's code for both Arduino and Teensy controllers.

![enter image description here](http://imgur.com/4ZYRcuI.jpg)

<hr> 

## Code and CAD files

All the files are in my github repository, included:
* Teensy 3.2 hex file (firmware)
* Leonardo Arduino code (.ino file and libs)
* Box measures (pdf file)
* CAD file for acrylic / plexiglass laser cutting

https://github.com/lizardbeans/sdvx-diy 

>This tutorial has been made with a Teensy 3.2 in mind and using only the hardware provided in the links below, any change on that would probably need some modifications on the code.

**How to upload the code on the Teensy 3.2 PCB.**

* Download and install [ARDUINO IDE v1.8](https://www.arduino.cc/en/Main/OldSoftwareReleases#previous)

* Download and install [Teensyduino](https://www.pjrc.com/teensy/td_download.html)

* Add these lines to the **C:\Program Files (x86)\Arduino\hardware\teensy\avr boards.txt** file and save.

>teensy31.menu.usb.sdvx=SDVX controller
>teensy31.menu.usb.sdvx.build.usbtype=USB_ARCADE
>teensy31.menu.usb.sdvx.fake_serial=teensy_gateway

Then add the 4 **usb_arcade** and **usb_desc** files inside yout **core/teensy3** folder and overwirte existing files.

>Alternatively download the whole set of folders from the github and paste into Program Files.

* Open Arduino IDE v1.8 
* In the *Tools* menu choose Board Type: Teensy 3.2
* In the *Tools* menu choose USB Type: SDVX Controller
* On the Arduino IDE screen press the verification button with a blank file (the verification button looks like a *aprooved tick*)
* It'll open a small Teensyduino screen.
* Hit the "Open HEX file" button on the Teensyduino screen and choose the hex file provided in the github repository.
* Manually click the hardware button that's on top of the Teensy PCB, and it'll upload.
* After a few seconds it'll be done.

>Sometimes windows won't recognize the controller as a USB device to test the buttons.
>For testing the buttons try http://html5gamepad.com/

<hr>

## Part List / Hardware

Here I include all the stuff you'll need to make the controller most important parts. Be sure to read everything before buying so you know what you're getting into. Also use the links described below so you don't end up with any surprises, like cheap chinese buttons or shorter wires. If I missed something you can ask in the Discord server.

Read the notes at the end of each item so you know some negative things about each store or webpage.

### Tools

* Soldering Pen / Soldering Station (this is a must have, buy one or borrow one from a friend)
* 60/40 risin core solder
* Crimper (optional, you can also crimp with pliers, although it's harder)
* Wire cutter
* Wire stripper
* Pliers
* Sandpaper 180 and 100 grit
* Wood glue (carpenter's glue, white glue)
* Small nails and a Hammer
* White matte spray paint can (Rustoleum is a good brand)
* Jigsaw, Hacksaw or a coping saw to make the holes.
* Power drill
	* 1" Spade bit
	* 5mm wood bit

The soldering pen is mandatory for the Teensy board. Buy the risin core solder because it's easier to melt.
The crimper will make your job easier, but you can also crimp using pliers (harder to do).

To make the box a jigsaw is the best tool to make the holes, and the spade bit is good to make round corners in those holes.

<hr>

Next I'll leave a list of things to buy either if you're going to use a Teensy 3.2 or a Leonardo. 

I suggest using the sellers I put there but you're free to chose another one if you don't mind some minor differences.
If a link goes ***404*** ask in the Discord channel or use Google to search an alternative. Amazon, Ebay, Aliexpress and DealExtreme are good places to search for these things.

## For Arduino LEONARDO

| ITEM                           | IMAGE | QUANTITY | LINKS                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | NOTES                                                                                                                     |
|--------------------------------|-------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Arduino Leonardo               | <img source="http://i.imgur.com/U1CyitI.jpg" width="100" /img>     | 1        | [DealExtreme](http://www.dx.com/p/diy-leonardo-r3-module-for-arduino-works-with-official-arduino-boards-blue-376823#.WH4Ie_nhAVA)   [Amazon](https://www.amazon.com/Qunqi-Leonardo-R3-development-Microcontroller/dp/B014H52DT4/ref=sr_1_1?s=electronics&ie=UTF8&qid=1501526944&sr=1-1-spons&keywords=arduino+leonardo&psc=1)            [Ebay](http://www.ebay.com/itm/Official-GENUINE-Arduino-LEONARDO-ATmega32u4-R3-Board-with-Free-USB-Cable-/151757125067?epid=512544962&hash=item23556df5cb:g:6WkAAOSwys5WV7Lb)                                                                                                                                | Try local electronic stuff stores. They're usually cheaper and closer.                                                                     |
| Encoder (600ppr)               | ![encoder](http://i.imgur.com/aQWAdH0.png =100px)     | 2        | [AliExpress](https://es.aliexpress.com/store/product/1-unid-Nueva-Encoder-600-P-R-Incremental-AB-2-Fase-de-5-V-24-V/1305558_32669741048.html)   [Amazon](https://www.amazon.com/Signswise-Incremental-Encoder-Dc5-24v-Voltage/dp/B00UTIFCVA/ref=sr_1_cc_1?s=aps&ie=UTF8&qid=1501527001&sr=1-1-catcorr&keywords=encoder+600+ppr)   [Ebay](http://www.ebay.com/itm/New-Encoder-600-P-R-5V-24V-Incremental-Rotary-AB-2-Phase-6mm-Shaft-/162190810777)                                                                                                                                                                           | If you want to use other type of encoder (like a 400ppr one)   you'll need to change part of the code. Mostly the sensitivity.                    |
| Aluminium Knobs                | ![hifi knobs](http://i.imgur.com/Rn4MUli.png)     | 2        | [AliExpress](https://es.aliexpress.com/store/product/Free-Shipping-diameter-30-High-22-All-aluminum-alloy-knob-Potentiometer-knob-HIFI-audio-amplifier-knob/1799190_32619270123.html)   [Ebay](http://www.ebay.com/itm/1PCS-30mmDIAx22-Aluminum-STEREO-VOLUME-CONTROL-KNOB-/380905947186?pt=LH_DefaultDomain_0&hash=item58afc38032)    [Amazon](https://www.amazon.com/uxcell-Aluminium-Alloy-Speaker-Control/dp/B00X73QARO)                                                                                                                                                                                                       | You can search for "hi-fi knobs" on other stores. They have to be not smaller than 30x22mm.                                                                          |
| Buttons 60x60                  | ![60 button](http://i.imgur.com/mJtIC1y.jpg)     | 4        | [Sanwa Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_080/)    [Aliexpress](https://es.aliexpress.com/item/high-quality-4pcs-lot-Square-60-60mm-Lighted-Buttons-Illuminated-Push-Button-with-Micro-switch-for/32611880107.html)                                                                                                                                                                                                                                                                                                                                                                                               | Sanwas are the real thing but expensive. Chinese are good enough. If you buy SANWAS the shipping will be expensive too. |
| Buttons 30x30                  | ![30x30 button](http://i.imgur.com/ePiRrdP.png)     | 1        | [SANWA Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_016/)    [AliExpress](https://es.aliexpress.com/store/product/32mm-Square-Arcade-Button-LED-Illuminated-Push-Button-with-Microswitch-for-Arcade-Games-DC-12V-5/2812058_32804514696.html)   [Ebay](http://www.ebay.com/itm/33mm-square-game-machine-push-button-arcade-LED-illuminated-push-button-7N-/292149166950)   [Amazon](https://www.amazon.com/BQLZR-Square-Illuminated-Button-Machinery/dp/B00Z5PHXG4)                                                                                                                                                   | Same with the 60x60 buttons. SANWA's are better but don't spend too much on the start button, ok?|
| Buttons 33x50                  | ![33x50 button](http://i.imgur.com/M0USm7A.png)     | 2        | [SANWA Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_098/)  [Aliexpress   10pcs.](https://es.aliexpress.com/item/10x-Beatmania-IIDX-Rectangle-LED-Light-Illuminated-Push-Button-Rectangular-buttons-For-Arcade-Coin-Machine-50/32720629306.html?spm=2114.13010608.0.0.3phRJQ)  [SANWA DENSHI   Rakuten](http://global.rakuten.com/en/store/sanwadenshi/item/ilumb_100/?s-id=borderless_recommend_item_en)   [Amazon](https://www.amazon.com/Easyget-Rectangular-Illuminated-Beatmania-50mm33mm/dp/B00XL1PZZK)   [Ebay](http://www.ebay.com/itm/Arcade-White-LED-Illuminated-Rectangular-Push-Button-For-Beatmania-IIDX-DIY-Kits-/131974107974) | Ok, for rectangle button chinese are good. Try not to buy the cheapest option, sometime they'll sell you buttons that are too tall. |
| Microswitch (D2MV-1C3          | ![Switch D2MV](http://i.imgur.com/gFfBD68.png)     | 7        | [Ebay](http://www.ebay.com/itm/D2MV-01-1C3-D2MV-01-1C3-10Pcs-New-Omron-Micro-Switch-free-shipping-/262495416199)   [SANWA   Rakuten](http://global.rakuten.com/en/store/sanwadenshi/item/ilumb_223/)   [Mouser](http://www.mouser.com/search/ProductDetail.aspx?R=0virtualkey0virtualkeyD2MV-01-1C3)   [Digikey](https://www.digikey.com/product-detail/es/omron-electronics-inc-emc-div/D2MV-01-1C3/Z4708-ND/5236584.)                                                                                                                                                                                                                               | You can either buy the D series or the VX series. I recommend   the VX.                                                   |
| Microswitch (VX-01-1CXX)       | ![Switch VX](http://i.imgur.com/H99h5qY.png)     | 7        | [Digikey](https://www.digikey.com/product-detail/en/omron-electronics-inc-emc-div/VX-01-1C23/VX-01-1C23-ND/369962.)   [Mouser](http://www.mouser.com/ProductDetail/Omron-Electronics/VX-01-1C23/?qs=1tDaWCEHQQ6VqzlIAIMCdA%3D%3D)                                                                                                                                                                                                                                                                                                                                                                                                                     | You can either buy the D series or the VX series. I recommend   the VX.                                                   |
| Stranded wires or Jumper wires | ![wires](http://i.imgur.com/iP6iCxo.png)     | 1        | [DealExtreme (Jumper wires)](http://www.dx.com/p/pvc-male-to-female-arduino-dupont-cables-multicolored-30cm-307052#.WH4I3_nhAVA) [AliExpress](https://es.aliexpress.com/item/10m-20AWG-4-pin-RGB-cable-PVC-insulated-wire-Electric-cable-LED-cable-Free-to-choose/32631719269.html)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Don't use solid wires, they're less flexible and prone to   break more easily with too much movement.                     |
| Crimp Connectors 187           | ![187](http://i.imgur.com/6yPc3EH.png)     | 14       | [AliExpress   50pcs.](https://www.aliexpress.com/item/50-pcs-4-8mm-Faston-Crimp-Terminal-187-Female-Connector-and-Transparent-Sheath-Inserted-Spring-Self/32755341225.html)                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | You'll need 2 for each microswitch                                                                                        |
| Crimp Connectors 250           | ![0](http://i.imgur.com/Gv9X6Rh.png)     | 14       | [AliExpress   25pcs.](https://es.aliexpress.com/item/25-sets-6-3mm-Thickness-0-4mm-Faston-Crimp-Terminal-250-Female-Connector-Transparent-Sheath-insulation/32786820964.html)                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | You'll need 2 for each LED lamp                                                                                           |
| Cable ties/Belkro ties         | ![0](http://i.imgur.com/ViGnOwh.png)     | 1 or 2   | From your local hardware store, or just use tape.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | For cable managment                                                                                                       |
| M5 bolts (lenght: 1" or 25mm)          | ![0](http://i.imgur.com/TUHUlJU.png)     | 24       | [AliExpress   30pcs.](https://es.aliexpress.com/item/30pcs-Lot-Metric-Thread-M5-6-8-10-12-14-16-18-20-25-30-35/32609656316.html)   [Ebay](http://www.ebay.com/itm/New-A2-Stainless-Steel-Button-Head-Screws-Hex-Socket-Bolts-M3-M4-M5-M6-M8-M10-/262781348398)                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                           |
| M5 nuts                        | ![that's nuts!](http://i.imgur.com/di9QSbM.png)     | 24       | [AliExpress   50cps.](https://es.aliexpress.com/item/50pcs-Lot-Free-Shipping-Metric-Thread-M5-304-Stainless-Steel-Hexagon-Nuts-Screw-Nuts-Hex-Nuts/32612699111.html)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                           |

##For TEENSY 3.2

| ITEM                               | IMAGE | QUANTITY | LINKS                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | NOTES                                                                                                                              |
|------------------------------------|-------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Teensy 3.2                         | ![teeeeeeeensy](https://www.pjrc.com/store/teensy32.jpg)     | 1        | [Official site](https://www.pjrc.com/store/teensy32.html)   [Amazon]() [Ebay]()                                                                                                                                                                                                                                                                                                                                                                                             | Dont buy fake ones! Those are poorly made and prone to fail.   If the LED on your Teensy is other than color RED then it's probably a fake. |
| Perforated Board 6x8cm             | 0     | 1        | [AliExpress](https://www.aliexpress.com/item/6-8CM-1-6mm-2-54mm-Pitch-Double-Side-Prototype-PCB-Universal-Printed-Circuit-Board/32323224375.html)                                                                                                                                                                                                                                                                                                                           | Use this one to solder the Teensy on                                                                                    |
| Pin strip                          | ![pinstrip](https://cdn.solarbotics.com/products/photos/d1866cb1e95ada5d14ea0d5b0cf49525/83600-951112-8622-ar.JPG)     | 1        | [AliExpress](https://es.aliexpress.com/store/product/100PCS-LOT-40PIN-11CM-2-54MM-Pitch-Single-Row-Pin/610196_2045909393.html)                                                                                                                                                                                                                                                                                                                                              | Use this to make it easier to solder or mount on the Perfboard                                                                  |
| Encoder (600ppr)                   | ![encoder booiiss](http://i.imgur.com/aQWAdH0.png)     | 2        | [AliExpress](https://es.aliexpress.com/store/product/1-unid-Nueva-Encoder-600-P-R-Incremental-AB-2-Fase-de-5-V-24-V/1305558_32669741048.html)   [Amazon](https://www.amazon.com/Signswise-Incremental-Encoder-Dc5-24v-Voltage/dp/B00UTIFCVA/ref=sr_1_cc_1?s=aps&ie=UTF8&qid=1501527001&sr=1-1-catcorr&keywords=encoder+600+ppr)   [Ebay](http://www.ebay.com/itm/New-Encoder-600-P-R-5V-24V-Incremental-Rotary-AB-2-Phase-6mm-Shaft-/162190810777) | These are standard chinese encoders. They're always $10 each. They're good quality though. Don't listen to COPAL's followers, they'll always tell you that copals are the best.                                                                                  |
| Aluminium Knobs                    | ![yo man, don't be a knob!](http://i.imgur.com/Rn4MUli.png)     | 2        | [AliExpress](https://es.aliexpress.com/store/product/Free-Shipping-diameter-30-High-22-All-aluminum-alloy-knob-Potentiometer-knob-HIFI-audio-amplifier-knob/1799190_32619270123.html)   [Ebay](http://www.ebay.com/itm/1PCS-30mmDIAx22-Aluminum-STEREO-VOLUME-CONTROL-KNOB-/380905947186?pt=LH_DefaultDomain_0&hash=item58afc38032)    [Amazon](https://www.amazon.com/uxcell-Aluminium-Alloy-Speaker-Control/dp/B00X73QARO)                             | You can search for "hi-fi knobs" on other stores. No smaller than 30x22mm                                                                                   |
| Buttons 60x60                      | ![0](http://i.imgur.com/mJtIC1y.jpg)     | 4        | [Sanwa Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_080/)  [Aliexpress]() [Amazon]() [Ebay]()                                                                                                                                                                                                                                                                                                                                                                       | Sanwas are the real thing but expensive. Chinese are good   enough. If you buy SANWAS the shipping will be expensive too.          |
| Buttons 30x30                      | ![reference 30 button](http://i.imgur.com/ePiRrdP.png)     | 1        | [SANWA Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_016/)    [AliExpress](https://es.aliexpress.com/item/high-quality-4pcs-lot-Square-60-60mm-Lighted-Buttons-Illuminated-Push-Button-with-Micro-switch-for/32611880107.html)                                                                                                                                                                                               | Same as with the 60x60 buttons. But don't spend you whole allowance on the start button.         |
| Buttons 25x50                      | ![IIDX button yo!](http://i.imgur.com/M0USm7A.png)     | 2        | [SANWA Rakuten](http://item.rakuten.co.jp/sanwadenshi/ilumb_098/)  [Aliexpress   10pcs.](https://es.aliexpress.com/item/10x-Beatmania-IIDX-Rectangle-LED-Light-Illuminated-Push-Button-Rectangular-buttons-For-Arcade-Coin-Machine-50/32720629306.html?spm=2114.13010608.0.0.3phRJQ)  [SANWA DENSHI   Rakuten](http://global.rakuten.com/en/store/sanwadenshi/item/ilumb_100/?s-id=borderless_recommend_item_en)                                                            | Buy chinese. Chinese are good. Not the cheapest ones though, sometimes they'll sell you taller buttons.         |
| Microswitch (D series)             | ![swtich D](http://i.imgur.com/gFfBD68.png)     | 7        | [Ebay](http://www.ebay.com/itm/D2MV-01-1C3-D2MV-01-1C3-10Pcs-New-Omron-Micro-Switch-free-shipping-/262495416199)   [SANWA   Rakuten](http://global.rakuten.com/en/store/sanwadenshi/item/ilumb_223/)   [Mouser](http://www.mouser.com/search/ProductDetail.aspx?R=0virtualkey0virtualkeyD2MV-01-1C3)   [Digikey](https://www.digikey.com/product-detail/es/omron-electronics-inc-emc-div/D2MV-01-1C3/Z4708-ND/5236584.)                                                     | You can either buy the D series or the VX series. I recommend   the VX.                                                            |
| Microswitch (VX series)            | ![switch V](http://i.imgur.com/H99h5qY.png)     | 7        | [Digikey](https://www.digikey.com/product-detail/en/omron-electronics-inc-emc-div/VX-01-1C23/VX-01-1C23-ND/369962.)   [Mouser](http://www.mouser.com/ProductDetail/Omron-Electronics/VX-01-1C23/?qs=1tDaWCEHQQ6VqzlIAIMCdA%3D%3D)                                                                                                                                                                                                                                           | You can either buy the D series or the VX series. I recommend   the VX.                                                            |
| 4 pin PH connector with 30cm wires | ![4 pin PH wire](http://i.imgur.com/hEbBqOl.jpg?1)     | 9        | [AliExpress](https://es.aliexpress.com/item/10PCS-lot-leng-30cm-Connector-Leads-Header-2-0mm-PH-2P-3P-4P-5P-6P-7P/32786407991.html?spm=a219c.10010108.1000016.1.GX6ntU&isOrigTitle=true)   [Ebay](http://www.ebay.com/itm/30cm-Set-of-2P-3P-4P-5P-6P-8P-10P-PH2-0-2-0mm-Pin-Wire-Cable-Straight-Right-Plug-/263042274891)   [Amazon](https://www.amazon.com/2-0MM-Female-Single-Connector-Wires/dp/B01JG1F0SA)                                                              | I used this connectors that are smaller, but you can try using XH connector wires. Also use 30cm wires, not 15cm wires. **Again, 25 to 30cm wires are what you need** not those puny 15cm wires.         |
| Crimp Connectors 187               | ![187](http://i.imgur.com/6yPc3EH.png)     | 14       | [AliExpress   50pcs.](https://www.aliexpress.com/item/50-pcs-4-8mm-Faston-Crimp-Terminal-187-Female-Connector-and-Transparent-Sheath-Inserted-Spring-Self/32755341225.html)                                                                                                                                                                                                                                                                                                 | You'll need 2 for each microswitch                                                                                                 |
| Crimp Connectors 250               | ![250](http://i.imgur.com/Gv9X6Rh.png)     | 14       | [AliExpress   25pcs.](https://es.aliexpress.com/item/25-sets-6-3mm-Thickness-0-4mm-Faston-Crimp-Terminal-250-Female-Connector-Transparent-Sheath-insulation/32786820964.html)                                                                                                                                                                                                                                                                                               | You'll need 2 for each LED lamp                                                                                                    |
| Cable ties/Belkro ties             | ![cable ties](http://i.imgur.com/ViGnOwh.png)     | 1 or 2   | From your local hardware store, or just use tape.                                                                                                                                                                                                                                                                                                                                                                                                                           | For cable managment                                                                                                                |
| M5 bolts (lenght: 1" or 25mm)              | ![M5 bolt](http://i.imgur.com/TUHUlJU.png)     | 24       | [AliExpress   30pcs.](https://es.aliexpress.com/item/30pcs-Lot-Metric-Thread-M5-6-8-10-12-14-16-18-20-25-30-35/32609656316.html)   [Ebay](http://www.ebay.com/itm/New-A2-Stainless-Steel-Button-Head-Screws-Hex-Socket-Bolts-M3-M4-M5-M6-M8-M10-/262781348398)                                                                                                                                                                                                              |                                                                                                                                    |
| M5 nuts                            | ![that's nuts](http://i.imgur.com/di9QSbM.png)     | 24       | [AliExpress   50cps.](https://es.aliexpress.com/item/50pcs-Lot-Free-Shipping-Metric-Thread-M5-304-Stainless-Steel-Hexagon-Nuts-Screw-Nuts-Hex-Nuts/32612699111.html)                                                                                                                                                                                                                                                                                                        |                                                                                                                                    |

<hr>

## Part List / Building Materials

Building the box for your controller is not an easy task, but I'll try to make it as simple as possible. The basic box is just a rectangle with holes for each button, but for this guide I'll be taking the next step and I'll be using 5mm clear acrylic on top of the controller to make it look as close to a DJDAO SVSE as possible.

If you find that using acrylic / plexiglass is too expensive, you can use the same measures to make it out of wood.

Take a look at the gallery at the bottom to see other controller's made by other people.

![Acrylic laser cut](http://sdvx-diy.pancakeapps.com/pics/pic031.png)
  

**Main Box (Wood stuff)**
The main body of the controller will be made out of MDF wood. MDF is a kind of wood plank that is easy to cut and glue, and they're also light in comparison to wood direct from the tree.
Most hardware stores sell planks of MDF that are 120cm by 240cm, that are too big for a controller and buying a whole plank it's not a good solution, so for this I made a template on a 60 by 60cm piece of MDF wood.

>There's also some hardware stores that sell pieces of defective MDF that are as good as new. Those are cheaper and they'll work too.

>Some hardware stores also have a cutting service, where you can buy the whole MDF plank and ask them to cut it for you. 

You can cut the main rectangles and do the fine cuts yourself at home. 

Keep in mind that this box's measures are 3mm short on each side so you can fit the acrylic on the sides of the controller like the controller I made. If you wished to not use any acrylic on the side please add 6mm to the lenght of each side piece of wood.

![Controller Box](http://sdvx-diy.pancakeapps.com/pics/pic028.jpg)

![box measures](http://sdvx-diy.pancakeapps.com/pics/box%20measures.png)

**Acrylic stuff**

For these project we're using two types of acrylic (a.k.a. plexiglass in the US) to cover the entire box of the controller and to mount the keypad and the turntable.
Since we can't buy a original turntable we'll be making one out of acrylic that works just as good.

For this part I extremely recommend getting the job done by a local acrylic store and not by hand. Acrylic is hard stuff and it's quite toxic to breathe its dust so you're better paying for this. If you don't have the money then it's up to you!

For this job I have a CAD file that includes all the stuff you need in a 60 by 60cm piece of acrylic. Some stores sell you the whole piece + laser cuts, others stores will bill you by piece, that depends on where you're doing the job. I won't recommend any place other than the closest local store you have, since shipping is just as expensive as the laser cut work.

So, to ask the local store how much the work will be, take the CAD file and send it to the store as it is, they'll know what to do with it and will tell you how much it is.

For this we'll have 2 different thickness.

The top plate will be made out of clear 5mm acrylic. This will support better all the strees of pusing the buttons and will be see through to use any kind of artwork you like.

The walls wll be covered in 3mm Black (or white) acrylic. This will be used for protection and to make it look super shiny and cool.

Finally the bottom door will be made of the same 3mm black acrylic.

In the end you'll need:

| ITEM               | THICKNESS | COLOR            | QUANTITY |
|--------------------|-----------|------------------|----------|
| Top plate          | 5 mm      | Clear            | 1        |
| Side cover (Walls) | 3 mm      | Black (or white) | 4        |
| Bottom door        | 3 mm      | Black (or white) | 1        |


![enter image description here](http://i.imgur.com/zNlw3Rd.jpg)

>the brown thing is the protective layer, under that the acrylic is matte black on one side and glossy on the other. Also the clear acrylic is not burned, that's the protective plastic too.

All the acrylic on the top and the sides will not be glued together, they'll be kept in place using the M5 bolts and nuts.
<hr>

## Assembly / Building the controller

Start by drawing all the holes that you're gonna cut. For this you can use a ruler and a pencil and mark each line on top of the wood. Don't worry about messing up the surface with your pencil because you're gonna be cleaning that later with some sandpaper.

If you have a good printer you can print the sketch of the top part on a 1:1 scale, and then glue it on top of the MDF and just cut along the lines.

![enter image description here](http://i.imgur.com/L82N5Tn.jpg)

Start by cutting all the pieces, but dont cut the holes yet, you're gonna do that last.

**Glueing part**

Once you have the 5 main pieces (4 walls and 1 top) put the top upside down and start by gluing one wall to the top. Keep the pieces toghether until the glue dries enough to keep the wall in place.
Then using the first wall as a support glue the second side wall to the top and to the already glued wall.
Finish by gluing the other walls left, wait 5 or 10 minutes until the glue is mid-dry and clean the excess glue with a slightly wet paper towel.

Wait 12 hours for the glue to completly dry and measure everything again. You'll need a perfect sized box or the acrylic won't fit well. If the box is larger by 1 or 2 mm, use the 100 grit sand paper to sand it down 1mm each side. Once the measures are right finish it by sanding it with a 180 grit sandpaper.

**Making the holes**

Now, put the clear top acrylic on top of the box. The acrylic should be 3mm larger on each 4 sides (that's where the 3mm black acrylic on the sides will hide below the clear acrylic. Pretty neat huh). With the top acrylic centered mark with a pencil the 4 corner holes for the bolts.

Take your power drill and drill the 4 holes where the bolts fixing the top acrylic will be.
Put the acrylic again on top and bolt the 4 corners until the acrylic is centered and secured.

With a pencil draw all the holes that you'll need to make on the top MDF plank, then with a ruler make all the holes 2 or 3 mm bigger on each side (to fit the buttons). You'll end up with holes on the MDF that are slightly bigger than the ones on the acrylic.

For this part you're gonna need a **1" spade bit and a drill.**
With the drill and the spade bit make a hole on each corner of the bigger hole so the side of the hole you make align with the lines. Next, use the same spade bit and make 4 holes in a cross figure on the knobs part of the top plate. That'll make it easier to cut these parts with a **copingsaw, jigsaw or hacksaw.**

![spade bit making a hole](http://i.imgur.com/bAeDM1r.jpg)

After the 1" holes are done pick your saw of preference and start cutting the straight lines of the bigger hole. A jigsaw is the best tool for this part, but a copingsaw or hacksaw is just as good. Use the holes you made to put the saw through.

![enter image description here](http://i.imgur.com/CIyvdin.jpg)

![enter image description here](http://i.imgur.com/lIObNY7.jpg)

![enter image description here](http://i.imgur.com/JAoz48r.jpg)

Sand all the exposed edges with a 180 grit sand paper for that smooth finish.

Lastly do the same with the side black acrylic; mark the holes and drill the holes to mount the side plates and you're done!

![enter image description here](http://i.imgur.com/jTnnpll.jpg)

![Controller Box](http://sdvx-diy.pancakeapps.com/pics/pic028.jpg)

If you want to paint the box I suggest sanding the box with a 180 grit sandpaper until it's smooth, then coating the hole box with carpenter's glue (this will give it a nice transparent smooth coat to recieve the paint) and finish it by painting it with a **matte white spray paint can**. Or any other color you'd like.

Paint one layer at a time and wait 20 minutes for it to dry before painting a second layer. Repeat until done.

![enter image description here](http://i.imgur.com/Ks8Qf0Q.jpg)

>I used a third of the can painting this

**Acrylic, buttons, and everything else**

Start by printing the artwork you're gonna use on your controller. If you dont have any you can put some white paper meanwhile to finish the controller. 

>Also, if you don't have a bigger printer or a place to print, you can print a design using 3 pieces of A4 paper, and some tape.

Use a **exacto-knife** or a **cutter** to cut the holes on the artwork. You can do this more easily if you put the acrilic on top and just cut using it as a ruler.

Finally put the artwork on the box, and then the clear acrylic on top of the artwork. Keep it fixed with a bolt on each corner.

The **buttons** are easy to install. Just take the plastic nut out and the holder part, put the button through the hole in the acrylic and put the holder and the nut from the other side back again.

For the **encoders** you'll first need to make a small round dent on each of the 3 screw holes for each encoder. **We need to hide the head of the bolt so it doesn't poke up and scratch our knobs. **

Grab your drill and with a drill bit the size of the bolt head start making a small dent on the same hole the bolt is going to be in. When the hole is halfway in stop. That should give enough space to hide the bolt head.

![enter image description here](http://i.imgur.com/wFSVb5I.jpg)

Each encoder has 6 holes, but we're only gonna use 3 of them, if you put the encoder through the hole you'll notice that only 3 of the holes match with the ones in the acrylic meanwhile the other 3 won't fit. 

![enter image description here](http://i.imgur.com/0eS7OKO.jpg)

>If you have any problem fitting the encoders through the hole grab a piece of 100 grit sandpaper and sand it down a little bit at a time until the encoder fits. The measures are there for a perfect fit, but the laser cutting machines has a tolerance of 0.1mm that could make the hole a little smaller.

<hr>

## Software and Wiring


The wiring process is simple enough but will give you a headache the first time you plug everything and something doesn't work.

I'll give you an introduction to some of the parts of the controller, and then I'll explain how to wire everything for a LEONARDO and a TEENSY board.
<hr>

First let's talk about **microswitches.**

Microswitches can have 2 or 3 contacts depending if they're chinese or Omron brand switches.
The first one usually have 3 contacts: the one from bellow it's the ground (GND) and the lower right one is the input. The third one on the upper right it's normally closed (NC), we won't use it. Omron switches come only with the lower and lower right contacts. Check out this diagram:

<img style='width: 600px' src='http://sdvx-diy.pancakeapps.com/pics/pic014.jpg'></img>

For the LEONARDO we usually daisy-chain all the GROUND/COMMON wires to a single one. This is completly normal and will make the job a lot easier.
>Thanks to LEONARDOjoy tutorial for this image.

<img style='width: 500px' src='http://i.imgur.com/DOZom0Z.jpg'></img>

Then we have the **encoders**.

The high quality encoders (600ppr) have 4 wires coming out: Data A and B (to send the rotating information), 5V input (to give the encoder the power to work) and GND (which is the ground / common), like shown here:

![enter image description here](http://i.imgur.com/n57AcSg.png)

>The image is from the Beatmania IIDX tutorial, but the encoder is the same.

The 2 data wires go to the pins indicated in the PIN LAYOUT as DATA A and B, depending if you're using a Leo or a Teensy. Same with the 5v pin and the Ground pin.

<hr>

**Wiring the Teensy PCB**

The first thing is getting the Teensy board attached to the perfboard, that way we can solder as many times as we want without damaging the expensive Teensy board.

**If you have a Teensy board with the included pins like this:**

![Teensy with pins](https://cdn.sparkfun.com/assets/learn_tutorials/3/8/5/TeensyFlushWithBoard.jpg)

Just put the Teensy over the perfboard, turn it around and solder each pin.

**If you have a teensy board without pins:**

You can buy strip of pins that can be soldered to the Teensy first and the perfboard later. Pin strips are cheaper than water and can be found in most electronic stuff stores.

If you can't find any pin strip on sale or you're good enough with solder that you want to make it on your own:

-- START OF THE RISKY PART OF THE TEENSY BOARD --

**How to attach the Teensy to a perfboard without a pin strip.**

>**I am not responsible if you damage your teensy board doing this without pins. It's difficult, you need good soldering equipment and it'll take a few hours. Go buy pin strips instead!**

Start by putting the teensy in it desired place over the perfboard. Be sure to have enough space between the perfboard and the teensy so the teensy doesn't touch anything below. 

Cut a 4-5 mm solid piece of wire from some scrap wires and solder it to the teensy in one of the corners pin holes leaving enough of the pin to be able to solder it to the perfboard. (I don't have pictures of this, sorry!) Repeat the same process with the pin from the oposite corner. 

Now that you have the Teensy centered and soldered in place with two pins, proceed to solder the other 15 or so pins using more 5mm pieces of solid wire. You'll end up with a Teensy attached to the perfoard in a similar way as I did. (Check out the video below)

-- END OF RISKY PART OF THE TEENSY BOARD --

**Installing the male headers and the other wires.**

Start by soldering each one of the male PH headers. These PH headers are smaller than the board holes, so you'll need to bend the metal pins on the header a little to make them fit, but after soldering you won't have any issues. 

>These smaller PH header can also be changed to normal XH headers but they're bigger and may not fit in a 6x8cm perfboard

Following the next layout solder a thin wire from each pin on the Teensy (from the perfboard, not the teensy itself) to each pin of the header.

The common ground will be a line of solder that will join both center pins on each header, then connected to the Teensy GND pin with a wire. We'll leave the grounds at the center for convenience.

For the **encoders** youll need a common 5V line connected to both headers, and another common ground line besides the pins from the data A and B.

![Teensy Layout](http://imgur.com/SZelUBS.png)

>NOTICE: I had some electric interference that leave the controller not responding. That may be happening because for all the GND connected to the board. But at the same time other people don't have this issue and might be related to my own teensy. Anyway I'm not a electrician in any way, but I read that using capacitors at the end of each ground might help.

**Teensy 3.2 PIN layout**

The pins are assigned to every button and encoder. You'll see that the PCB has many pins from 0 to 33 including some Ground points (GND). We'll be using pins from 0 to 3 for the encoders and 4 to 10 for the buttons, and 13 to 19 for the LED lamps. Check the next picture to see the PCB layout:

<img style='width: 400px' src='http://i.imgur.com/KPp8c6Y.jpg'></img>
<img style='width: 400px' src='http://i.imgur.com/l4PatLE.jpg'></img>


**SOUNDVOLTEX Layout (TEENSY ONLY)**

<table><thead>
<tr>
<th>Button</th>
<th style="text-align: center">Pin #</th>
<th style="text-align: center">Button #</th>
<th style="text-align: center">LED Pin #</th>
</tr>
</thead><tbody>
<tr>
<td>Start</td>
<td style="text-align: center">4</td>
<td style="text-align: center">Button 1</td>
<td style="text-align: center">13</td>
</tr>
<tr>
<td>BT-A</td>
<td style="text-align: center">5</td>
<td style="text-align: center">Button 2</td>
<td style="text-align: center">14</td>
</tr>
<tr>
<td>FX-L</td>
<td style="text-align: center">6</td>
<td style="text-align: center">Button 3</td>
<td style="text-align: center">15</td>
</tr>
<tr>
<td>BT-B</td>
<td style="text-align: center">7</td>
<td style="text-align: center">Button 4</td>
<td style="text-align: center">16</td>
</tr>
<tr>
<td>BT-C</td>
<td style="text-align: center">8</td>
<td style="text-align: center">Button 5</td>
<td style="text-align: center">17</td>
</tr>
<tr>
<td>FX-R</td>
<td style="text-align: center">9</td>
<td style="text-align: center">Button 6</td>
<td style="text-align: center">18</td>
</tr>
<tr>
<td>BT-D</td>
<td style="text-align: center">10</td>
<td style="text-align: center">Button 7</td>
<td style="text-align: center">19</td>
</tr>
</tbody></table>


<table><thead>
<tr>
<th>ENCODERS</th>
<th style="text-align: center">DATA 1</th>
<th style="text-align: center">DATA 2</th>
</tr>
</thead><tbody>
<tr>
<td>Left knob (VOL-L)
<td style="text-align: center">0</td>
<td style="text-align: center">1</td>
</tr>
<tr>
<td>Right knob (VOL-R)
<td style="text-align: center">2</td>
<td style="text-align: center">3</td>
</tr>
</tbody></table>

>Also you have to connect the encoders to the VUSB pin for the 5v input**

>NOTICE: I've noticed that LED's are not that bright using a Teensy. That might be the code or the board I'm not sure since I'm not a coder in any way. I can't fix the code.

**Wires and Crimp connectors**

For this part we'll use the PH 4 pin wires that are 30 cm long. They're harder to get (most sellers only have 15 cm wires) but we'll need all those extra centimeters for this.

Each one of these cables have 4 wires (one for each pin), and we already know the 2 center wires will be the GROUND wires form the buttons and the LED lamps.

By now we also have two kinds of crimp connectors.

The 187 connector is the smaller one, used for the switches on the buttons.

The 250 connector is the bigger one used on the LED lamps.

You could also use the 250 connector on the buttons but that might get some disconnections while playing.

Crimping is an easy process with the right tools. Just grab the crimp head and the wires, put the crimp in the crimper tool and hold it there. Then put the wires inside the space that is gonna be bent and press it with the tool until the wires is grabbed by the crimp head. Then repeat with the wire grabber part of the crimp.

If all 7 buttons have crimped wires then it's a matter of connecting everything and you're done!

> I made a video showing how to mount everything at the end of this page, check it out!

-------------------

**Wiring the Leonardo PCB**

For the LEONARDO circuit board we're gonna be using any kind of stranded wire, usually a thin one so it doesn't use too much space.
We're also be using those cool crimp connectors so we don't have to solder each wire to each button, and desoldering everytime a button or switch breaks. It'll make maintenance easier in the long run.

![enter image description here](http://i.imgur.com/wVEetdk.jpg)

First let's choose a good place for the LEONARDO inside the box. You want it to be in a place where you don't need wires that are too long or put it to close neither. Fix the Leaonardo using 2 or more screws.

Cut some wires so the length of it is enough to reach from each of the buttons to the Arduino Leonardo PCB. For this cut 2 wires of different colors for each button. Those 2 wires will be the positive (+) charge for the Button and the LED.

Strip the tip of each wire and using a crimper, crimp a 250 and a 187 crimp connector to each one. The 250 crimp is for the LED and the 187 crimp is for the microswitch.

Next we're gonna daisy-chain all the grounds / common of each one of the buttons.

Take a long wire but don't cut it yet. Strip the tip and put a crimp connector in it. In this case use a 250 crimp connector for the ground of the LED. Put the connector on the first upper left button and measure how much wire you need to reach the second button on the side. Cut the wire to that lenght and strip the tip of it too.

Now strip the tip of the the wire you had left and then take the 2 wires and twist them together in a single wire. Using the 250 crimp connector crimp both wires with only 1 crimp connector. Be sure that it's firmly crimped or else the button or LED won't work sometimes.

Repeat this process until all the 250 crimp connectors are attached. The other end of the wire that is not crimped is gonna go to the Leonardo so leave a good wire lenght.

Now do the same thing with the 187 crimp connectors for each of the buttons and that'll leave you with two ground wires.

![enter image description here](http://i.imgur.com/BhBj5Rs.png)

For the encoders strip some of the black wire protector back so the lenght of each encoder wire is long enough to reach all 4 pins you'll need in the Leonardo.

Now you'll have 18 single wires (9 LEDS and 9 buttons) and 2 ground wires, and also 4 encoder wires.

Now you need to use a soldering iron and some solder to tin the tip of each wire so the threads of the wires are together in a single solid wire. Try to make it as thin as posible so it fits inside the jumper holes of the PCB. The tinned wires should now be able to go inside the jumper holes for each pin, following the next PIN LAYOUT.

**PIN LAYOUT (LEONARDO ARDUINO)**

<table><thead>
<tr>
<th>Button</th>
<th style="text-align: center">Pin #</th>
<th style="text-align: center">Button #</th>
<th style="text-align: center">LED Pin #</th>
</tr>
</thead><tbody>
<tr>
<td>Start</td>
<td style="text-align: center">13</td>
<td style="text-align: center">Button 1</td>
<td style="text-align: center">6</td>
</tr>
<tr>
<td>BT-A</td>
<td style="text-align: center">A0</td>
<td style="text-align: center">Button 2</td>
<td style="text-align: center">7</td>
</tr>
<tr>
<td>FX-L</td>
<td style="text-align: center">A1</td>
<td style="text-align: center">Button 3</td>
<td style="text-align: center">8</td>
</tr>
<tr>
<td>BT-B</td>
<td style="text-align: center">A2</td>
<td style="text-align: center">Button 4</td>
<td style="text-align: center">9</td>
</tr>
<tr>
<td>BT-C</td>
<td style="text-align: center">A3</td>
<td style="text-align: center">Button 5</td>
<td style="text-align: center">10</td>
</tr>
<tr>
<td>FX-R</td>
<td style="text-align: center">A4</td>
<td style="text-align: center">Button 6</td>
<td style="text-align: center">11</td>
</tr>
<tr>
<td>BT-D</td>
<td style="text-align: center">A5</td>
<td style="text-align: center">Button 7</td>
<td style="text-align: center">12</td>
</tr>
</tbody></table>


<table><thead>
<tr>
<th>ENCODERS</th>
<th style="text-align: center">DATA 1</th>
<th style="text-align: center">DATA 2</th>
</tr>
</thead><tbody>
<tr>
<td>Left knob (VOL-L)
<td style="text-align: center">0</td>
<td style="text-align: center">1</td>
</tr>
<tr>
<td>Right knob (VOL-R)
<td style="text-align: center">2</td>
<td style="text-align: center">3</td>
</tr>
</tbody></table>

>**Also you have to connect the encoders to the 5V pin for the 5v input**

That leaves pins 2 to 10 for LEDS (9 LEDS, enough for each button)
The Leonardo also has 3 ground pins, so use 1 for the encoder, 1 for the buttons and the other one for the LEDS.

With this done you now only need to load the code into the Arduino and it's done!

>I'll make a video about this later, so stay tunned!.

<hr>

## Gallery

[Step by step gallery](http://imgur.com/a/uVgB2)

<blockquote class="imgur-embed-pub" lang="en" data-id="a/uVgB2"><a href="//imgur.com/uVgB2">SDVX DIY</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>

<iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?list=PL1-stUt4e92oJIEkfmvS2MhW4jPTuUhcC" frameborder="0" allowfullscreen></iframe>

**OTHER CONTROLLERS made by you guys and gals**

<blockquote class="imgur-embed-pub" lang="en" data-id="a/nJUs6"><a href="//imgur.com/nJUs6">Other controllers made by YOU</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script> 

## Troubleshooting

Any questions, troubleshooting or tips? Try my Discord server:

https://discord.gg/fknwz8s

## Donations

I give these guides free of charge for everyone to share and use, so you don't need to pay a cent to have this information in your hands. I also give support on my Discord server if you need any help.

BUT if you feel like giving me a beer for my hard work collecting this information you can do it here:
<form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick">
<input type="hidden" name="hosted_button_id" value="ULNDLKTWFE8HC">
<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/es_XC/i/scr/pixel.gif" width="1" height="1">
</form>

--------
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-107694000-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-107694000-1');
</script>




