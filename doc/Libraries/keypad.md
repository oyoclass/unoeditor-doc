#Keypad

The keypad library makes using button matrix keypads easy to use with the Arduino. To properly read from a keypad, you have to scan through the rows and columns of the button matrix setting some as high or low outputs, and reading from others. To do so while trying to also detect other sensors and events is difficult. The keypad library does these processes for you, allowing you to read which key is pressed with a simple method, getKey().

To use the keypad library, you first need to include it at the top of your code.

```c++
#include <Keypad.h>
```

##2D Array

Now it's best to store the keys of the keypad in a 2D array. This will change depending on how your keypad is labled and how many keys it has. For example, your keypad may be a 4x4 or a 3x4 matrix.

The example below is of a 4x4 keypad.

```c++
int numRows = 4;
int numCols = 4;

char keys[numRows][numCols] = {
  {'1', '2', '3', 'A'},
  {'4', '5', '6', 'B'},
  {'7', '8', '9', 'C'},
  {'*', '0', '#', 'D'}
};
```

##Pinouts

You also need to map the pinouts. To do this, we'll use two array, one for the rows and one for the columns. 

```c++
byte rowPins[] = {9, 8, 7, 6}; 
byte colPins[] = {5, 4, 3, 2}; 
```

##Object

To create an LCD object, follow the line of code below. 

```c++
Keypad keypadObj = Keypad(makeKeymap(keys), rowPins, colPins, rows, cols);
```

##Methods

###keypadObj.getKey()

The .getKey() method returns the key pressed based on the 2D array you set up. This method returns a char. See below for an example of how to use the method.

```c++
char key = keypadObj.getKey();
```

###keypadObj.waitForKey()

The .waitForKey() method waits until a key is pressed, and prevents all other code from running. The only exception is interrupt service routines, which will run when triggered, regarless of the .waitForKey() method.


####Credit
[Library by Mark Stanley, Alexander Brevig](https://playground.arduino.cc/Code/Keypad/)
