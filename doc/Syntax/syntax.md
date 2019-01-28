#Syntax

Many programming languages share a similar set of coding tools and operations. However, they often differ in how these operations get written; their **syntax**. Look below to see some of the syntax of the Arduino language.

---

##Structure

Every Arduino sketch must have a setup and loop function. Beyond that, you will often include libraries, global variables, and user defined functions. Look below for an example of how this will typically look.

```c++
//Included Libraries
#include <Servo.h>

//Global variables
int angle = 90;
int var = 0;

void setup() {
  // put your setup code here, to run once:
}

void loop() {
  // put your main code here, to run repeatedly:
}

void myFunction() {
  // my code
}
```

---

##Comments

Comments are used in your code to explain it for yourselves and for others to read. 

**Single line comments** are written by starting a line with **//**

```c++
//This is a single line comment
```

**Block comments** are written by surrounding a comment with */* **/ 

```c++
/*This is a 
block comment */
```

---

##Conditional Statements

**Conditional statements** are ways to evaluate if something is true or false. Is p equal to q? Is 5 > 4? Conditional statements are often used in programming to determine what should happen in the code. Look below to see how various conditional statements are written.

```c++
== (equal to) 
!= (not equal to) 
< (less than) 
<= (less than or equal to) 
> (greater than) 
>= (greater than or equal to) 
```

---

##If Statements

**If statements** are coding tools that run a block of code *if* a conditional statement is true. If a statement is not true, that code block will be skipped over. After an if statement you may have an **else if** or **else** statment. An else if statment is an if statment that gets evaluated only if the preceeding if or else if statement evaluates as false. An else statement runs if the preceeding if or else if statement evaluates as false. The code block that runs if one of these statements is true is contained within the curly brackets, like this: **{*//code block*}**.

```c++
if (var == 5) {
    //do something
}
else if (var < 5) {
    //do something else
}
else {
    //do something different
}
```

---

##While Loops

A while loop repeats a code block as long as the conditional statement evaluates as true. You need to be careful to write code within the while loop that will eventually cause the while loop to evaluate as false. Otherwise, your code can get stuck in a never ending loop.

```c++
while (condition == true) {
	//do things
}
```

---

##For Loops

For loops allow you to repeat a code block a certain number of times while incrementing a variable, called a *counter*, each time the for loop goes through a cycle. 

The three arguments are the initialization, condition, and increment, respectively. The initialization step initializes the counter variable. The condition specifies the condition under which the for loop keeps operating. Once the condition evaluates as false, the for loop stops running. The increment either increases or decreases, decrements, the counter. The shorthand way of doing this is counter++ or counter--.

```c++
for (int i = 0; i < 10; i++) {
    Serial.println(i);
}
```

---

##Switch Case

A switch case works, essentially, like several else if statements. An argument is fed in and is evaluated against several cases. If the argument is equal to any of the cases, the code contained within that case will run. If no cases are true, the optional default will run or, if there is no default defined, the switch case will be skipped over.

```c++
switch (var) {
    case 1:
      //do something when var equals 1
      break;
    case 2:
      //do something when var equals 2
      break;
    default:
      // if nothing else matches, do the default
      // default is optional
      break;
}
```

---

####Credit

https://www.arduino.cc/reference/en/