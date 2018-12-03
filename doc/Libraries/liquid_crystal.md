#Liquid Crystal I2C


```c++
#include <LCD.h>
#include <LiquidCrystal_I2C.h>
```

##Methods

lcd.begin()
Args:
-start the lcd screen. 16x2

clear

- clear everything from the lcd screen

print

setCursor

home

##Examples

```c++
#include <LCD.h>
#include <LiquidCrystal_I2C.h>

//Create liquid crystal object called 'lcd'
LiquidCrystal_I2C lcd(0x3f, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);

void setup() {
  lcd.begin(16, 2); //Start and initialize the lcd display
  lcd.clear(); //Clear any text from the scree
  lcd.setCursor(0,1);
  lcd.print("Starting..."); //Print 'Starting...'
  delay(1000); //Give a second to display the message.
}

void loop() {

}
```