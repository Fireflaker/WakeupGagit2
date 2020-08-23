# WakeupGadget2

Important! Make sure the Vcc of the RTC module is connected correctly and has a stable voltage. The circuit will work even when its Vcc is at high impedance. Current will be drown from the data pins to keep the battery charged. But this is bad and will result in inaccurate time keeping up to several minutes per day. 

I hate waking up in the dark. I hate being forced to get out of bed in general. So I made this thing 1 day after daylight saving plan to turn on a projector before the alarm goes off. For such efficiency, I shamelessly pasted df99 in CircuitsArduino linked below so THANK YOU!

It has been tested working. I recommend connecting your projector to a chromebook that has a alarm to go off 1 minute after the projector turns on. So you get the best audio visual experiance. 

A very ambitious goal is to synthesis video signal from arduino to drive the projector to just display some colors.

Arduino RTC OLED alarm clock that turns on an projector via IR remote every morning. 

https://www.instructables.com/id/DS3231-OLED-clock-with-2-button-menu-setting-and-t/


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
     +8800, -4400     + 550, - 550     + 550, - 550     + 500, - 600
     + 500, -1650     + 550, - 550     + 550, - 550     + 550, - 550
     + 500, - 600     + 500, -1650     + 550, -1650     + 550, - 550
     + 500, - 600     + 500, -1650     + 550, - 550     + 550, - 550
     + 500, - 600     + 500, -1650     + 550, -1650     + 550, -1650
     + 500, - 600     + 500, - 550     + 550, - 550     + 550, - 550
     + 550, -1650     + 500, - 600     + 500, - 550     + 550, - 550
     + 550, -1650     + 500, -1650     + 550, -1650     + 550, -1650
     + 500, - 550     + 550
unsigned int  rawData[67] = {8800,4400, 550,550, 550,550, 500,600, 500,1650, 550,550, 550,550, 550,550, 500,600, 500,1650, 550,1650, 550,550, 500,600, 500,1650, 550,550, 550,550, 500,600, 500,1650, 550,1650, 550,1650, 500,600, 500,550, 550,550, 550,550, 550,1650, 500,600, 500,550, 550,550, 550,1650, 500,1650, 550,1650, 550,1650, 500,550, 550};  // NEC 10C8E11E
unsigned int  data = 0x10C8E11E;

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

Encoding  : NEC
Code      : 10C821DE (32 bits)
Timing[67]: 
     +8800, -4400     + 550, - 550     + 550, - 550     + 500, - 600
     + 500, -1650     + 550, - 550     + 500, - 600     + 500, - 550
     + 550, - 550     + 500, -1700     + 500, -1650     + 550, - 550
     + 500, - 600     + 500, -1650     + 550, - 550     + 550, - 550
     + 500, - 550     + 550, - 550     + 550, - 550     + 500, -1650
     + 550, - 550     + 550, - 550     + 500, - 600     + 500, - 550
     + 550, -1650     + 500, -1650     + 550, -1650     + 550, - 550
     + 500, -1650     + 550, -1650     + 550, -1650     + 500, -1650
     + 550, - 550     + 500
unsigned int  rawData[67] = {8800,4400, 550,550, 550,550, 500,600, 500,1650, 550,550, 500,600, 500,550, 550,550, 500,1700, 500,1650, 550,550, 500,600, 500,1650, 550,550, 550,550, 500,550, 550,550, 550,550, 500,1650, 550,550, 550,550, 500,600, 500,550, 550,1650, 500,1650, 550,1650, 550,550, 500,1650, 550,1650, 550,1650, 500,1650, 550,550, 500};  // NEC 10C821DE
unsigned int  data = 0x10C821DE;

