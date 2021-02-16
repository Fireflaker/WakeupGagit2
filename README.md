# WakeupGadget3
The new update addes dimming display and turning on another orijector at the cost of removing a few pretty pictires. 


The V3 with cat displays well and has all prior features. All you need is an Arduino UNO, a DS3231_I2C real time clock module, a 1306 or 1106 OLED, and an IR led. Optionally you need two more leds that plugs straight into your arduino uno, two push buttons(I use lose wire), and an IR reciever that can record your personalized IR message to do things. 

Im working on designing a 3d printed box for this
and and record some more IR messages to automate things like ECO mode, brightness, etc. 

Important! Make sure the Vcc of the RTC module is connected correctly and has a stable voltage. The circuit will work even when its Vcc is at high impedance. Current will be drown from the data pins to keep the battery charged. But this is bad and will result in inaccurate time keeping up to several minutes per day. 

In response to having to waking up in the dark and be forced to get out of bed in general, I made this thing 1 day after daylight saving plan to turn on a projector before the alarm goes off. Clock code is from df99 in CircuitsArduino linked below.

It has been tested working. I recommend connecting your projector to a chromebook that has a alarm to go off 1 minute after the projector turns on. So you get the best audio visual experiance. 

A very ambitious goal is to synthesis video signal from arduino to drive the projector to just display some colors.
(Will not happen because the arduino is already filled to the brim)

Arduino RTC OLED alarm clock that turns on an projector via IR remote every morning. 

Huge credit goes to df99 linked below!!
https://www.instructables.com/id/DS3231-OLED-clock-with-2-button-menu-setting-and-t/
And those who wrote the libraries!
Espacially the 1106 librariy linked below!
https://github.com/wonho-maker/Adafruit_SH1106

Most things are gathered online I am just keeping my progress on git. 


![Test Image 1](/IMG_20200823_010739.jpg)
![Test Image 1](/IMG_20200823_010745.jpg)
![Test Image 1](/IMG_20200823_010756.jpg)


Acer
Power：10C8E11E
Menu： 10C821DE

Encoding  : NEC
Code      : 10C8E11E (32 bits)
Timing[67]: 
     +8850, -4400     + 550, - 550     + 500, - 600     + 500, - 550
     + 550, -1650     + 550, - 550     + 500, - 600     + 500, - 550
     + 550, - 550     + 550, -1650     + 500, -1700     + 500, - 550
     + 550, - 550     + 550, -1650     + 500, - 600     + 500, - 600
     + 500, - 550     + 550, -1650     + 550, -1650     + 500, -1650
     + 550, - 550     + 550, - 550     + 550, - 550     + 500, - 600
     + 500, -1650     + 550, - 550     + 550, - 550     + 500, - 600
     + 500, -1650     + 550, -1650     + 550, -1650     + 500, -1650
     + 550, - 550     + 550
unsigned int  rawData[67] = {8850,4400, 550,550, 500,600, 500,550, 550,1650, 550,550, 500,600, 500,550, 550,550, 550,1650, 500,1700, 500,550, 550,550, 550,1650, 500,600, 500,600, 500,550, 550,1650, 550,1650, 500,1650, 550,550, 550,550, 550,550, 500,600, 500,1650, 550,550, 550,550, 500,600, 500,1650, 550,1650, 550,1650, 500,1650, 550,550, 550};  // NEC 10C8E11E
unsigned int  data = 0x10C8E11E;

Encoding  : NEC
Code      : 10C821DE (32 bits)
Timing[67]: 
     +8800, -4400     + 550, - 550     + 550, - 550     + 500, - 550
     + 550, -1650     + 550, - 550     + 500, - 550     + 550, - 550
     + 550, - 550     + 500, -1650     + 550, -1650     + 550, - 550
     + 500, - 550     + 550, -1650     + 550, - 550     + 500, - 600
     + 500, - 550     + 550, - 550     + 500, - 600     + 500, -1650
     + 550, - 550     + 550, - 550     + 500, - 550     + 550, - 550
     + 550, -1650     + 500, -1650     + 550, -1650     + 550, - 550
     + 500, -1650     + 550, -1650     + 500, -1650     + 550, -1650
     + 550, - 550     + 500
unsigned int  rawData[67] = {8800,4400, 550,550, 550,550, 500,550, 550,1650, 550,550, 500,550, 550,550, 550,550, 500,1650, 550,1650, 550,550, 500,550, 550,1650, 550,550, 500,600, 500,550, 550,550, 500,600, 500,1650, 550,550, 550,550, 500,550, 550,550, 550,1650, 500,1650, 550,1650, 550,550, 500,1650, 550,1650, 500,1650, 550,1650, 550,550, 500};  // NEC 10C821DE
unsigned int  data = 0x10C821DE;






Infocus in42:
Power：E172E817

Menu: E17240BF

Down: E17228D7

OK: E1724CB3

Up: E172C837

Left: E1728877

Right: E17248B7

Leave: E1720AF5

mute: E172946B

Vol up: E17210EF

Vol down: E17220DF


Encoding  : NEC
Code      : E172E817 (32 bits)
Timing[67]: 
     +9000, -4400     + 600, -1600     + 600, -1600     + 600, -1650
     + 600, - 500     + 600, - 500     + 600, - 500     + 600, - 500
     + 600, -1600     + 600, - 550     + 550, -1650     + 600, -1600
     + 600, -1650     + 550, - 550     + 550, - 550     + 600, -1600
     + 600, - 550     + 550, -1600     + 600, -1650     + 600, -1600
     + 600, - 500     + 600, -1600     + 600, - 550     + 550, - 550
     + 600, - 500     + 600, - 500     + 600, - 500     + 600, - 500
     + 600, -1600     + 600, - 550     + 550, -1650     + 600, -1600
     + 600, -1600     + 600
unsigned int  rawData[67] = {9000,4400, 600,1600, 600,1600, 600,1650, 600,500, 600,500, 600,500, 600,500, 600,1600, 600,550, 550,1650, 600,1600, 600,1650, 550,550, 550,550, 600,1600, 600,550, 550,1600, 600,1650, 600,1600, 600,500, 600,1600, 600,550, 550,550, 600,500, 600,500, 600,500, 600,500, 600,1600, 600,550, 550,1650, 600,1600, 600,1600, 600};  // NEC E172E817
unsigned int  data = 0xE172E817;

Encoding  : NEC
Code      : E17240BF (32 bits)
Timing[67]: 
     +8900, -4500     + 550, -1650     + 550, -1650     + 550, -1700
     + 550, - 550     + 550, - 550     + 550, - 550     + 550, - 550
     + 550, -1650     + 550, - 550     + 550, -1700     + 550, -1650
     + 550, -1650     + 550, - 550     + 600, - 550     + 500, -1700
     + 550, - 550     + 550, - 550     + 550, -1650     + 600, - 550
     + 550, - 550     + 550, - 550     + 550, - 550     + 550, - 550
     + 550, - 550     + 550, -1650     + 600, - 550     + 550, -1650
     + 550, -1650     + 550, -1700     + 550, -1650     + 550, -1650
     + 550, -1650     + 550
unsigned int  rawData[67] = {8900,4500, 550,1650, 550,1650, 550,1700, 550,550, 550,550, 550,550, 550,550, 550,1650, 550,550, 550,1700, 550,1650, 550,1650, 550,550, 600,550, 500,1700, 550,550, 550,550, 550,1650, 600,550, 550,550, 550,550, 550,550, 550,550, 550,550, 550,1650, 600,550, 550,1650, 550,1650, 550,1700, 550,1650, 550,1650, 550,1650, 550};  // NEC E17240BF
unsigned int  data = 0xE17240BF;





