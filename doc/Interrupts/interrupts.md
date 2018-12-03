#External Interrupts

An external interrupt - sometimes called a hardware interrupt - is a piece of hardware that, when triggered, runs an interrupt service routine, ISR. An interrupt service routine is simply a user defined function that gets attached to an interrupt. When the interrupt is triggered, it stops the code the Arduino is running and runs the ISR. Once the ISR is finished running, the Arduino returns to running the code where it left off.

A simple example is a button connected to an interrupt that switches the direction of a motor any time it's pushed, regardless of where the Arduino is in the code.

The Arduino has two interrupts, 0 and 1, connected to pins 2 and 3, respectively. The can ge triggered by four different modes:

* **Low**: trigger the interrupt whenever the pin is low, 0V-3V.
* **Falling**: trigger the interrupt whenever the pin goes from high to low.
* **Rising**: trigger the interrupt whenever the pin goes from low to high.
* **Change**: trigger the interrupt whenever the pin changes from low to high, or vice versa.

## attachInterrupt()

### Description

To set up an interrupt, you need to create an ISR, attach it to an interrupt pin, and choose the mode. You do this using the method **attachInterrupt()**.

**attachInterrupt()** is typically used within the **setup()**. *Note that you should use pinMode() to set up your interrupt pin as an input as well.*

### Syntax

**attachInterrupt(digitalPinToInterrupt(pin), ISR, mode);**

* **pin**: the number of the pin being used
* **ISR**: the name of the interrupt service routine your create at the bottom of your code
* **mode**: LOW, FALLING, RISING, or CHANGE
* **digitalPinToInterrupt()**: a function that takes in a pin number and returns the respective interrupt number (different versions of the Arduino have different interrupt pins).

###Examples

```c++
int led = 13;
int button = 2;
int on = LOW;

void setup() {
  pinMode(led, OUTPUT);
  pinMode(button, INPUT);
  attachInterrupt(digitalPinToInterrupt(button), ledChange, CHANGE);
}

void loop() {
  digitalWrite(ledPin, on);
}

void ledChange() { //ledChange is the name of the ISR
  on = !on; 	   //Change the value of 'on' between LOW and HIGH
}
```