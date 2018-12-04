#Servo

To include the library into the sketch you're working on, include the library shown below at the top of your sketch.

```c++
#include <Servo.h>
```

##Object

To create a Servo object, follow the line of code below. 

```c++
Servo myservo;
```

##Methods

###myservo.attach(pin);

* **pin**: the pin the signal pin of the servo is connected to

The attach() method sets up the servo object and connects it to a digital pin. The digital pin **MUST** be one of the PWM enabled pins.

###myservo.write(pos)

* **pos**: the angle in degrees, from 0 to 180

The write() method turns the servo motor to a specific angle, between 0 and 180 degrees.

```c++
/* Sweep
 by BARRAGAN <http://barraganstudio.com>
 This example code is in the public domain.

 modified 8 Nov 2013
 by Scott Fitzgerald
 http://www.arduino.cc/en/Tutorial/Sweep
*/

#include <Servo.h>

Servo myservo;  // create servo object to control a servo
// twelve servo objects can be created on most boards

int pos = 0;    // variable to store the servo position

void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object
}

void loop() {
  for (pos = 0; pos <= 180; pos += 1) { // goes from 0 degrees to 180 degrees
    // in steps of 1 degree
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
  for (pos = 180; pos >= 0; pos -= 1) { // goes from 180 degrees to 0 degrees
    myservo.write(pos);              // tell servo to go to position in variable 'pos'
    delay(15);                       // waits 15ms for the servo to reach the position
  }
}
```