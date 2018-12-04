#Random

---

##random()

###Description

Generates and returns a pseudo-random number.

###Syntax

random(max)
random(min, max)

* **max**: upper bound of the random value, exclusive
* **min**: lower bound of the random value, inclusive

###Example

```c++
randNum = random(10); 	  //Generate a random number from 0-9
randNum2 = random(20,31); //Generate a random number from 20-31
```

---

##randomSeed()

###Description

Initializes the random number generator with a 'seed' value. It is common to use the analogRead() value of an analog pin as the seed value.

###Syntax

randomSeed(seed)

* **seed**: the number used to initialize the random number generator

###Example

```c++
randomSeed(analogRead(A0));
```

##Example Sketch

```c++
long randNum;

void setup() {
	randomSeed(analogRead(A0));
}

void loop() {
	randNum = random(100, 600);
	digitalWrite(13, HIGH,);
	delay(randNum)
	digitalWrite(13, LOW);
	delay(randNum);
}
```