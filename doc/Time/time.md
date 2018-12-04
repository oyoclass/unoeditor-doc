#Time

The functions below allow you to wait for a period of time or return the current time.

---

##delay()

###Description

Wait a speicified number of milliseconds. The Arduino does not run any other code while it is busy delaying.

###Syntax

delay(milliseconds);

* **milliseconds**: the number of milliseconds you wish to delay. There are 1,000 milliseconds in a second.

###Example

```c++
digitalWrite(13,HIGH);
delay(1000); //Delay one second.
digitalWrite(13,LOW);
delay(1000); //Delay one second.
```

---

##delayMicroseconds

###Description

Wait a speicified number of microseconds. The Arduino does not run any other code while it is busy delaying. Delays greater than 16,383 microseconds may not be accurate with this function.

###Syntax

delayMicroseconds(microseconds);

* **microseconds**: the number of microseconds you wish to delay. There are 1,000,000 microseconds in a second.

###Example

```c++
digitalWrite(13,HIGH);
delayMicroseconds(1000000); //Delay one second.
digitalWrite(13,LOW);
delayMicroseconds(500);     //Delay 500 microseconds
```

---

##millis()

###Description

Returns the time, in milliseconds, since the Arduino began running. After about 49.7 days the millis() function will reset to 0. This is because the data type returned, an unsigned long, can only hold 49.7 days worth of milliseconds.

###Syntax

currentTime = millis();

###Example

```c++
unsigned long currentTime = millis();

void setup(){
}

void loop() {
	currentTime = millis()
	//Turn the LED on after 1 second passes
    if (currentTime >= 1000) {
    	digitalWrite(13, HIGH);
    }
}
```

---

##micros()

###Description

Returns the time, in microseconds, since the Arduino began running. After about 70 minutes the micros() function will reset to 0. The resolution of the micros() function is 4 microseconds.

###Syntax

currentTime = micros();

###Example

```c++
unsigned long currentTime = micros();

void setup(){
}

void loop() {
	currentTime = micros()
	//Turn the LED on after 500 μs pass
    if (currentTime >= 1000) {
    	digitalWrite(13, HIGH);
    }
}
```