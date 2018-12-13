# **![](http://i64.tinypic.com/qpqm45.png) AmiiBomb - Amiibo Cloning**

AmiiBomb is a tool for Windows, using cheap components, to create Amiibo Tags (NTAG215) and much more...

## What do you need?

- *1x* Windows PC
- *1x* Arduino Uno R3 *(around $4)*
- *1x* USB Cable Type AB *(pretty sure you already have it)*
- *1x* RFID Module RC522 *(around $2)*
- *7x* Pin Wire Male-Female *(around $1 for x20)*
- *1x* Soldering Iron Kit *(and a little soldering skills)*
- As many NTAG215 as you want Amiibo tags *(around $34 for x100)*

## What do you have to do?

You have to solder the pins on the RC522 Module and connect them following this schematic. Connect the Arduino Uno (or Nano) to the PC by USB, and that's it! (People with soldering skills already know how to do this, but I prefer to explain for anyone who needs it!)

![Arduino / RC255 PinOut](http://i66.tinypic.com/2ng8zv9.jpg)

Signal    | RC522 Pin | Arduino Pin
--------- | --------- | -----------
RST/Reset | RST       | 9
SPI SS    | SDA(SS)   | 10
SPI MOSI  | MOSI      | 11 / ICSP-4 
SPI MISO  | MISO      | 12 / ICSP-1 
SPI SCK   | SCK       | 13 / ICSP-3 
VCC       | 3.3V      | 3.3V
GND       | GND       | GND

## After the hardware is set up?

Run AmiiBomb, set the Amiibo folder (*.bin files), select the Amiibo Keys, flash the AmiiBombuino Firmware to the Arduino, and you are ready to Read and Write Amiibo Tag.

 - ***.bin folder**

It's the folder where you can put your Amiibo dumps (previously dumped with AmiiBomb or found on internet, Google is your friend for that).
You can also read Amiibo data, to write onto another NTAG. You don't need to re-execute AmiiBomb, as it finds folder changes automatically.

 - **Amiibo Keys**

You probably already have them if you know a little about how Amiibo cloning works. If not, a little helper is here in AmiiBomb. Due to Copyright reasons, we can't distribute them, but there are many places to find them online. AmiiBomb sends you to the right website; you just have to highlight the key chars and copy them to your clipboard. AmiiBomb will check if the keys inside are valid, and will ask if you want to save them. If you have already them, you just need to select the key file.

 - **AmiiBombuino Firmware**

Just an Arduino program that communicates with AmiiBomb. You can flash it through avrdude by yourself, use the Internal Flasher in AmiiBomb, or use XLoader.

## Overview

![](http://i68.tinypic.com/dwe7g6.png) 
![](http://i67.tinypic.com/4sjvd3.png) 
![](http://i66.tinypic.com/21mtao8.jpg) 
![](http://i66.tinypic.com/1z6z0o1.png) 

## What is done?
- Grab the info from an Amiibo Dump via http://Amiibo.life website.
- Cache system for Amiibo Dump informations in a file.
- Enable/Disable and Reset Informations Caching files.
- Reconize encrypted/decrypted Amiibo Dump.
- Decrypt/Encrypt Amiibo Dump.
- Able to fix the incorrect size of one type of Amiibo Dump (Power Saves or N2? I don't know:/)
- Dump and Write AppData of an Amiibo Dump.
- Help to find Amiibo keys and autodetect them in clipboard to save them in a file.
- Multiple languages.
- Read NTAG215 data and save it to an Amiibo Dump file.
- Write an Amiibo Dump file to an NTAG215 tag.
- Flash AmiiBombuino firmware inside AmiiBomb.
- Get Amiibo tag basic info.
- and more...

## What's Next?
- Many little things to make AmiiBomb more user-friendly.
- Clean up the code.
- It works really fine with an NTAG215 but I don't know if it's work with an Amiibo ^^'!
- AppData editor (for SSB Amiibo or any others who have interesting things inside).
- Support PN532 NFC Module in AmiiBombuino.
- Improve the docs.

In a future, I'd like to own an N2 and PowerSaves to add more functionality to AmiiBomb. If you have any kind of ideas or suggestions, just let me know :)! You feel free to donate to me at my PayPal address: ackeedy@gmail.com

Thanks, and enjoy!
