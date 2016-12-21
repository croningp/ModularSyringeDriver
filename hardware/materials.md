# Bill of Materials
These are the materials needed to create the modular syringe driver and where to source them.

## Screws & Quantities
Screw | Quantity | Vendor
--- | --- | ---
M2.5 x 6mm | 6 | [RS Components](http://uk.rs-online.com/web/p/socket-screws/4838124/)
M3 x 6mm | 5 | [RS Components](http://uk.rs-online.com/web/p/socket-screws/1871207/)
M2.5 x 12mm | 5 | [RS Components](http://uk.rs-online.com/web/p/socket-screws/4838130/)
M3 x 10mm | 2 | [RS Components](http://uk.rs-online.com/web/p/socket-screws/2328366/)
M3 x 12mm | 4 | [RS Components](http://uk.rs-online.com/web/p/socket-screws/1871229/)


## Stepper Motor

The stepper motor used is a Nema 11, sourced from [Stepper Online](http://www.omc-stepperonline.com/threaded-rod-nema-11-external-linear-stepper-motor34mm-body-100mm-t5-x-2-p-203.html).

An alternative is a [custom-made stepper motor](custom_stepper/) from Heason (This is the preferred motor for this setup).

Contact [Paul Sorrell](mailto:psorrell@heason.com) for more information.

The motor from Stepper Online:

![Alt text](http://www.omc-stepperonline.com/images/11LS13-0754E-100B.jpg)



## Stop Switch
The switch used on the syringe driver is a D2F Ultra Subminature Basic Switch, sourced from [Omron](http://uk.farnell.com/omron-electronic-components/d2f01lt/microswitch-hinge-lever-0-1/dp/1961085)

[Data Sheet](https://www.omron.com/ecb/products/pdf/en-d2f.pdf) for the D2F switch.


## Arduino Mega + RAMPS Shield
The syringe driver is controlled via an Arduino Mega 2560 board fitted with a RAMPS v1.4 shield.

* The Arduino Mega can be sourced from the [Arduino website](https://www.arduino.cc/en/Main/ArduinoBoardMega2560) or from many electronics retailers.
![Alt text](https://a.pololu-files.com/picture/0J3807.1200.jpg?e5e6ed1dcbd127a24220d4ed455510a2)

* The RAMPS v1.4 shield can be sourced from [Ooznest](http://ooznest.co.uk/RAMPS-14-Controller-Board-Premium&currency=GBP&language=en?gclid=Cj0KEQiAyuPCBRCimuayhb3qqvwBEiQAgz62kVp1GNCQKYvTIFOcvpG9ZQ0eJvKzC2Tw6_trZBFtpCMaAlxl8P8HAQ)
![Alt text](http://ooznest.co.uk/image/cache/data/products/RAMPS-Premium/RAMPS-PREMIUM-3-746x1000.jpg)


## Stepper Motor Drivers for RAMPS v1.4
The stepper drivers used to control the stepper motor are [DRV8825 Drivers](https://www.pololu.com/product/2982)
![Alt text](https://a.pololu-files.com/picture/0J5806.1200.jpg?c8b077547880443247671b2d4d534ef4_)


## Linear Guide Rail
The syringe is guided by a linear rail, sourced at [RS Components](http://uk.rs-online.com/web/p/linear-guides-rails/6192391/)
![Alt text](http://uk.rs-online.com/largeimages/F6192391-01.jpg)


## Linear Guide Carraige
Attached to the linear rail is a guide carraige, also sourced at [RS Components](http://uk.rs-online.com/web/p/linear-guides-guide-blocks-carriages/6192442/)
![Alt text](http://uk.rs-online.com/largeimages/R619244-01.jpg)


## 3D Prints
Many of the parts needed to create this driver can be 3D printed. Please see the [Basic Driver](basic_driver_stls/) and [Modular Additions](modular_additions_stls/) folders for the appropriate STL files.
