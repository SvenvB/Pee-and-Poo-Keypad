# Pee-and-Poo-Keypad
A 4x2 button keypad for recording diaper changes, naps, and control lights.

* The keypad design is based on the great work from sfgabe: [Baby_Buddy_Keypad ](https://github.com/sfgabe/OITProjects/tree/e61a645ab1767e26cc00c47ae1d6af3861b3626a/Baby_Buddy_Keypad), but since I am by far not a woodworking expert, I designed a similar casing in FreeCAD that can be 3D printed. 
* The keypad is connected to HomeAssistant via [ESPHome](https://www.home-assistant.io/integrations/esphome/)
* The keypad automation is integrated with the NodeRED BabyBuddy project of [tango259](https://github.com/tango2590/baby-buddy)

<img src="https://github.com/SvenvB/Pee-and-Poo-Keypad/blob/main/photos/photo1.jpg" width="500">


## **Ingredients** 
* 1x [Lolin NodeMCU v3 ESP8266 ](https://www.aliexpress.us/item/3256807436237237.html?spm=a2g0o.order_list.order_list_main.50.21ef1802GzlgdW&gatewayAdapt=glo2usa)
* 8x [Blank Keypad Buttons](https://www.aliexpress.us/item/3256807496928162.html?spm=a2g0o.order_list.order_list_main.44.21ef1802GzlgdW&gatewayAdapt=glo2usa)
* 8x [Mechanical keyboard switches](https://www.aliexpress.us/item/3256807318817256.html?spm=a2g0o.order_list.order_list_main.38.21ef1802GzlgdW&gatewayAdapt=glo2usa)
* (2x M3 screws to fix the microcontroller in the box)

## Electrical connections
The buttons are connected to D1 through D8 on the ESP8266. 

* Buttons connected to D1 through D7 make use of internal pullup resistors and can therefore be connected to GND.
* The D8 pin has an internal pull-down resistor, and D8 **must** be low at boot. Therefore, the button connected to D8 should be connected to the +3.3V pin, and not GND.

<img src="https://github.com/SvenvB/Pee-and-Poo-Keypad/blob/main/photos/Schematic.jpg" width="500">
<img src="https://github.com/SvenvB/Pee-and-Poo-Keypad/blob/main/photos/photo3.jpg" width="300">

## CAD Design
* The casing is designed using [FreeCAD](https://www.freecad.org/). 
* The microcontroller is screwed down using 2x M3 screws. 
* The USB cable is more or less fixed using a glue pistol. 
* The lid is fixed using double-sided permanent tape.
* The buttons are printed on a 4"x6" glossy photo at a CVS store.

<img src="https://github.com/SvenvB/Pee-and-Poo-Keypad/blob/main/CAD%20files/buttons/buttons.png" width="300">

## Programming
I won't cover this part in much detail. 
* The microcontroller is added to ESPHome via a basic configuration: [epshome_code.yaml](https://github.com/SvenvB/Pee-and-Poo-Keypad/blob/main/esphome_code.yaml)
* The button automations are integrated with an already existing [BabbyBuddy integration](https://github.com/tango2590/baby-buddy) in HomeAssistant.

