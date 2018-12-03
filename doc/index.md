
The Arduino is a microcontroller board that can be programmed to control electrical devices such as lights and motors. They're often used to make quadcopters, thermostats, 3D printers, and more.

The Arduino language is based on C/C++, but also has a many of its own special functions and constants. The main structure of an Arduino program, called a sketch, includes a setup function and a continuous loop function. The setup runs once, and the loop runs continuously after that for as long as the Arduino is powered. 

It looks like this:

```c++
//The setup runs once when the Arduino is powered/turned on
void setup() {
	//Your setup code goes in here
}
//The loop runs continuously, starting after the setup is finished running.
void loop() {
	//The rest of your code goes in here
}
```

The Arduino can be programmed using the Arduino IDE when using PCs, Macs, or Linux computers. When using a Chromebook, the Arduino can be programmed using the UNO editor on the OYOclass platform.

##UNO Editor
 
The UNO editor is a development environment that can compile and upload your code to an Arduino UNO type board when used with the associated Chromebook app. The editor is only able to upload code to a board when used on a Chromebook. It can, however, be used to compile and verify code, as well as share code when using both Chromebook and non-Chromebook computers.

Another benefit of the UNO editor, it's lightning fast! The libraries are pre-compiled, so only the code you type has to be compiled.

##User Interface

###File

The **File** button is where you will find the new file, open, save, rename, and download options. This is also where you can manage and delete your files, and view your saving histories (older versions).

###Verify

The **Verify** button checks your code for syntax errors and compiles it. Compilation is the process of translating one language to another. In this case, the Arduino code is translated into the machine code that the Arduino understands.

###Upload to board

The **Upload to board** button will compile your code, then upload, or flash, your code to the board. 

###Compiling Status

The **compiling status** is shown in the window in the lower left hand

