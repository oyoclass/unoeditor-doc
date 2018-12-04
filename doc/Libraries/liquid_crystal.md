#Liquid Crystal I2C

The LiquidCrystal_I2C library allows you to program an Arduino to print messages to an LCD screen using an I2C backpack. I2C is a communication protocol that allows you to communicate with multiple devices using only a few pins. 

To include the library into the sketch you're working on, include the two libraries shown below at the top of your sketch.

```c++
#include <LCD.h>
#include <LiquidCrystal_I2C.h>
```

##Object

To create an LCD object, follow the line of code below. 

```c++
LiquidCrystal_I2C lcd(0x3f, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);
```

The first argument is the address of your LCD screen. This can be found by using the scanner script at the bottom of this page.

##Methods

###lcd.begin(x,y)

* **x**: the number of horizontal characters of the lcd screen
* **y**: the number of vertical characters of the lcd screen

Initialize the LCD screen with the height and width of the displays

###lcd.clear()

Clear all characters from the LCD screen

###lcd.print(var)

* **var**: any String or number data type

Prints characters to the LCD screen starting at the current location of the cursor. This method does not skip to the next line when it reaches the end of the line.

###lcd.setCursor(x,y)

* **x**: the horizontal space number, starting at 0
* **y**: the vertical space number, starting at 0

###lcd.home()

Places the cursor at the (0,0) point (upper left-hand corner)

##Examples

```c++
//Print "Starting..." on the second line of the LCD screen.
#include <LCD.h>
#include <LiquidCrystal_I2C.h>

//Create liquid crystal object called 'lcd'
LiquidCrystal_I2C lcd(0x3f, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);

void setup() {
  lcd.begin(16, 2); //Start and initialize the lcd display
  lcd.clear(); //Clear any text from the screen
  lcd.setCursor(0,1);
  lcd.print("Starting..."); //Print 'Starting...'
  delay(1000); //Give a second to display the message.
}

void loop() {

}
```

##Scanner script

```c++
// --------------------------------------
// i2c_scanner
//
// Version 1
//    This program (or code that looks like it)
//    can be found in many places.
//    For example on the Arduino.cc forum.
//    The original author is not know.
// Version 2, Juni 2012, Using Arduino 1.0.1
//     Adapted to be as simple as possible by Arduino.cc user Krodal
// Version 3, Feb 26  2013
//    V3 by louarnold
// Version 4, March 3, 2013, Using Arduino 1.0.3
//    by Arduino.cc user Krodal.
//    Changes by louarnold removed.
//    Scanning addresses changed from 0...127 to 1...119,
//    according to the i2c scanner by Nick Gammon
//    http://www.gammon.com.au/forum/?id=10896
// Version 5, March 28, 2013
//    As version 4, but address scans now to 127.
//    A sensor seems to use address 120.
// Version 6, November 27, 2015.
//    Added waiting for the Leonardo serial communication.
//
//
// This sketch tests the standard 7-bit addresses
// Devices with higher bit address might not be seen properly.
//
 
#include <Wire.h>
 
 
void setup()
{
  Wire.begin();
 
  Serial.begin(9600);
  while (!Serial);             // Leonardo: wait for serial monitor
  Serial.println("\nI2C Scanner");
}
 
 
void loop()
{
  byte error, address;
  int nDevices;
 
  Serial.println("Scanning...");
 
  nDevices = 0;
  for(address = 1; address < 127; address++ )
  {
    // The i2c_scanner uses the return value of
    // the Write.endTransmisstion to see if
    // a device did acknowledge to the address.
    Wire.beginTransmission(address);
    error = Wire.endTransmission();
 
    if (error == 0)
    {
      Serial.print("I2C device found at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.print(address,HEX);
      Serial.println("  !");
 
      nDevices++;
    }
    else if (error==4)
    {
      Serial.print("Unknown error at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.println(address,HEX);
    }    
  }
  if (nDevices == 0)
    Serial.println("No I2C devices found\n");
  else
    Serial.println("done\n");
 
  delay(5000);           // wait 5 seconds for next scan
}
```

####Credit
[Library by Francisco Malpartida](https://bitbucket.org/fmalpartida/new-liquidcrystal/overview)
