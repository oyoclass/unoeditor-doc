#Data Types

Data can be stored in variables. Each variable has a particular type of data it can store, called a data type. Example of data types can be numbers, characters, strings of text, etc. Here is an example of each of the data types reviewed on this page. Continue down for more details.

```c++
int var1 = 5;
long millisecondsInADay = 86400000;
float var1 = 3.14159;
bool isOn = true;
char var1 = 'A';
int myIntArray[] = {9, 8, 7, 6};
```

---

##int

###Description

Int stands for integer. An integer is any whole number, both positive and negative.

###Size

2 bytes

###Range 

-32,768 to 32,767 

###Examples

```c++
int var1 = 5;
int var2 = -3;
int var3 = 0;
int var4; //undefined
```

---

##long

###Description

Any whole number, both positive and negative.A long data type is like an int data type, but takes up twice the data, allowing the storage of larger numbers.

###Size

4 bytes

###Range 

-2,147,483,648 to 2,147,483,647

###Examples

```c++
long millisecondsInADay = 86400000; //86,400,000 milliseconds in a day
long var1 = -1500000000; //-1,500,000,000
long var2; //undefined
```

---

##float

###Description

Float stands for a floating-point number. It is a data type that can store numbers with decimals, 1.5, for example. When doing math with variables of a float data type, you will want to use numbers that are also floats in order to keep the values after the decimal. For example, use 1.0 instead of 1, as 1 is not a float.

Floats only have 6-7 digits of precision. Additionally, floating point calculations take longer to compute.

###Size

4 bytes

###Range 

-3.4028235E+38 to 3.4028235E+38

###Examples

```c++
float var1 = 3.14159;
float var2 = -5.4;
float var3 = 0.0;
float var4; //undefined
```

---

##bool

###Description

A bool, or boolean, is a data type that stores either **true** or **false**.

###Size

1 byte

###Range 

**true** or **false**

##String

###Description

A String data type contains a string of text. The text can have letters, numbers, and special characters. The contents of a String goes within double quotes. 

###Examples

```c++
bool isOn = true;
bool lightsOn = false;
int bool; //undefined
```

---

##char

###Description

Char stands for character. A char data type contains a single character, including letters, numbers, and special characters. The character stored in a char gets written between single quotes.

The characters are actually stored as numbers in memory. These numbers get translated to the characters we recognize according to the ASCII chart. 

###Size

1 byte

###Examples

```c++
char var1 = 'A';
char var2 = 'b';
char var3 = '#';
```

---

##array

###Description

An array is a collection of several variables, organized under one variable name. Each variable within the array is given an index number,its order within the array. All of the values stored within the array must be of the same type.

An item within an array can be retrieved by calling the array name with the index number, starting at 0 for the first item in the array. An example is shown below.

```c++
int myArray[] = {9, 8, 7, 6};
return myArray[2]; //Returns 7, the third item in myArray
```

Arrays can be initialized with values, or can be declared as being empty with a specified length.

###Examples

```c++
int myIntArray[] = {9, 8, 7, 6}; //An int array with 4 indices
float myFloatArray[] = {9.8, 5.7, 7.6, 8.9}; //A float array with 4 indices
char myCharArray[] = {'a', 'b', 'c'}; //A char array with 3 indices
int myArray[6]; //An empty array with 6 indices
```