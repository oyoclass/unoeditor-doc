#Builtin Functions and Methods
##pinMode()
###Description
Sets up a pin to be either an input or output. This allows the Arduino to allocate current appropriately 
###Syntax
pinMode(pin, mode)

* pin: the number of the pin being used
* mode: INPUT or OUTPUT
###Example

##digitalWrite()
###Description
Sets a pin to be either HIGH, 5V, or LOW, 0V or ground. The pin should be set to be an output using pinMode().
###Syntax
digitalWrite(pin, value)

* pin: the number of the pin being used
* value: HIGH or LOW (5V or GND)
###Example


##digitalRead()
###Description
Reads and returns the value of a pin; either HIGH or LOW. The value of a pin is determined by it's voltage with 0-3V being LOW and 3-5V being HIGH.
Syntax
digitalRead(pin)

* pin: the number of the pin being used	
###Example


##analogWrite()
###Description
Uses PWM to set a pin to a voltage between 0V and 5V. PWM, pusle width modulation, turns the pin on and off quickly, simulating an in between value. The pin should be set to be an output using pinMode().
###Syntax
analogWrite(pin, value)

* pin: the number of the pin being used
* value: 0-255 (0V-5V)
###Example


##analogRead()
###Description
Reads and returns the value of an analog pin on a range of 0-1023. The value of the pin changes with voltage with 0V being returned as 0 and 5V being returned as 1023. Analog pins are pins A0-A5
###Syntax
analogRead(pin)

* pin: the number of the pin being used	
###Example