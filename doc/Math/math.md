#Math

Mathematical operations can be performed within your code. In addition to basic operations, there are a few shorthand ways to do simple math. Look below to see some examples.

##Addition

Denoted by the **+** sign.

```c++
x = 5 + 6; //x = 11
x = x + 1; //Increment x by 1; Add 1 to x and overwrite the old value of x with the new one
x++; 	   //Increment x by 1; shorthand version of the line above
x += 3;    //Add 3 to x; compound addition
```

##Subtraction

Denoted by the **-** sign.

```c++
x = 7 - 2; //x = 5 
x = x - 1; //Decrement x by 1; Add 1 to x and overwrite the old value of x with the new one
x--;       //Decrement x by 1; shorthand version of the line above
x -= 3;    //Subtract 3 from x; compound subtraction
```

##Multiplication

Denoted by the *****.

```c++
x = 3 * 2; //x = 6
x = x * 3; //Multiply x by 3 and overwrite the old value of x with the new one
x *= 5;    //Multiply x by 5; compound multiplication
```

##Division

Denoted by the **/**.

```c++
x = 8 / 2; //x = 4 
x = x / 3; //Divide x by 3 and overwrite the old value of x with the new one
x /= 5;    //Divide x by 5; compound division
```

##Mod

The modulus - mod for short - is the remainder found when doing division. It is denoted using the **%** sign. 

```c++
x = 7 % 5;  //x = 2 
x = 10 % 5; //x = 0
x = 9 % 5;  //x = 4
```

---
#Math Functions

##max()

###Description

Calculates and returns the maximum value of two numbers

###Syntax

z = max(x, y); 

* **x**: first value
* **y**: second value

###Example

```c++
x = max(5, 3); //x = 5
```

---

##min()

###Description

Calculates and returns the minimum value of two numbers

###Syntax

z = min(x, y); 

* **x**: first value
* **y**: second value

###Example

```c++
x = min(6, 4); //x = 4
```

---

##map()

###Description

The map() function converts an input value from one scale to another scale. A common use for this function is converting from the analog input scale, 0-1023, to the analog output scale, 0-255.

###Syntax

x = map(value, lowInput, highInput, lowOutput, highOutput);

* **value**: input value
* **lowInput**: lower bound of the input scale
* **highInput**: upper bound of the input scale
* **lowOutput**: lower bound of the output scale
* **highOutput**: upper bound of the output scale

###Example

```c++
value = map(value, 0, 10, 0, 100); //Convert 'value' from a scale of 0-10 to a 
//scale of 0-100 and overwrite the old value of 'value' with the new one
```

---

##abs()

###Description

Calculates and returns the absolute value of a number.

###Syntax

x = abs(y)

* **y**: input value

###Example

```c++
x = abs(-5); //take the absolute value of -5 and save it into x; x = 5
```

---

##constrain()

###Description

Constrains, or restricts, the input value to a certain range.

###Syntax

x = constrain(x, low, high)

* **x**: the input
* **low**: the lower bound
* **high**: the upper bound

###Examples

```c++
x = constrain(14, 0, 10); //x = 10; 
y = constraint(54, 20, 100); //y = 54; the 54 is within the constrained range
```  

---

#Trigonometric Functions

##cos()

###Description

Calculates and returns the cosine of an angle. The function takes angles measured in radians, not degrees.

###Syntax

x = cos(rad);

* **rad** is the angle in radians. It accepts floating point numbers

###Examples

```c++
x = cos(0.523599); //x = 0.866
```

---

##sin()

###Description

Calculates and returns the sine of an angle. The function takes angles measured in radians, not degrees.

###Syntax

x = sin(rad);

* **rad** is the angle in radians. It accepts floating point numbers

###Examples

```c++
x = sin(0.523599); //x = 0.5
```

---

##tan()

###Description

Calculates and returns the tangent of an angle. The function takes angles measured in radians, not degrees.

###Syntax

x = tan(rad);

* **rad** is the angle in radians. It accepts floating point numbers

###Examples

```c++
x = tan(0.523599); //x = 0.57735027
```