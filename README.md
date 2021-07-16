# NHD-12864AZ-Display-KS0108-style-controller-Arduino
Eveyrthing you need to know to controll the NHD-12864AZ Display with the u8g2 library


i struggeled with this Display because Documentation was extremely poor and i didnt know much about this subject.
The u8g2 Library is extremly good but it has so many constructors for so many different Displays and none of them worked for me
because the wiring never matched completley to my Display.

Thanks to david_prentice who really helped me to get that display running. https://forum.arduino.cc/t/nhd-12864az-with-aip31108/877219

Thanks to him i finally found out that this Display runs on a KS0108 style controller. i changed the wiring a little and made it work
on my Arduino Uno R3.

The constructor you have to use for that wiring and that controller is:
U8G2_KS0108_128X64_1 u8g2(U8G2_R0, 11, 10, 9, 8, 7, 6, 5, 4, /*enable=*/ 12, /*dc=*/ 13, /*cs0=*/ 3, /*cs1=*/ 1, /*cs2=*/ U8X8_PIN_NONE, /* reset=*/  0);   // Set R/W to low!

Below is a simple wiring diagram. If you want to adjust the contrast you have to put a potentiometer between the Vout and the Vo Pin.
I hope this will help people like me.

![Sketch Empfänger_Schaltplan](https://user-images.githubusercontent.com/43731826/125895257-fdd8a30a-8f2c-4d55-bbb0-e5ea96f235b1.png)
