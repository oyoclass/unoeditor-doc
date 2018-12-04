#DHT Sensor

The DHT line of sensors are temperature and humidity sensors. The kidOYO prototyping kits features a DHT11 sensor. 


To include the library into the sketch you're working on, include the library shown below at the top of your sketch.

```c++
#include "DHT.h"
```

##Object

To create an LCD object, follow the line of code below. 

```c++
DHT dht(DHTPIN, DHTTYPE);
```

* **DHTPIN**: the Arduino pin the DHT sensor is connected to
* **DHTTYPE**: DHT type (the kit uses the DHT11)


The first argument is the address of your LCD screen. This can be found by using the scanner script at the bottom of this page.

##Methods

###dht.begin();

Start and initialize the dht object

###dht.readHumidity()

Read and return the relative humidity as a percentage

###dht.readTemperature()

Read and return temperature in degrees Celcius

###dht.readTemperature(true)

Read and return temperature in degrees Fahrenheit. The argument 'true' changes the output from Celcius to Fahrenheit.

###dht.computeHeatIndex(f, h)

Compute and return the heat index in degrees Fahrenheit. The heat index is the measure of how hot it feels based on the temperature and humidity.

###dht.computeHeatIndex(t, h, false)

Compute and return the heat index in degrees Celcius. The heat index is the measure of how hot it feels based on the temperature and humidity. The last argument, 'false,' changes the output to Celcius.

```c++
// Example testing sketch for various DHT humidity/temperature sensors
// Written by ladyada, public domain

#include "DHT.h"

#define DHTPIN 2     // what digital pin we're connected to

// Uncomment whatever type you're using!
#define DHTTYPE DHT11   // DHT 11
//#define DHTTYPE DHT22   // DHT 22  (AM2302), AM2321
//#define DHTTYPE DHT21   // DHT 21 (AM2301)

// Connect pin 1 (on the left) of the sensor to +5V
// NOTE, if using a board with 3.3V logic like an Arduino Due connect pin 1
// to 3.3V instead of 5V!
// Connect pin 2 of the sensor to whatever your DHTPIN is
// Connect pin 4 (on the right) of the sensor to GROUND
// Connect a 10K resistor from pin 2 (data) to pin 1 (power) of the sensor

// Initialize DHT sensor.
// Note that older versions of this library took an optional third parameter to
// tweak the timings for faster processors.  This parameter is no longer needed
// as the current DHT reading algorithm adjusts itself to work on faster procs.
DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  Serial.println("DHTxx test!");

  dht.begin();
}

void loop() {
  // Wait a few seconds between measurements.
  delay(2000);

  // Reading temperature or humidity takes about 250 milliseconds!
  // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
  float h = dht.readHumidity();
  // Read temperature as Celsius (the default)
  float t = dht.readTemperature();
  // Read temperature as Fahrenheit (isFahrenheit = true)
  float f = dht.readTemperature(true);

  // Check if any reads failed and exit early (to try again).
  if (isnan(h) || isnan(t) || isnan(f)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Compute heat index in Fahrenheit (the default)
  float hif = dht.computeHeatIndex(f, h);
  // Compute heat index in Celsius (isFahreheit = false)
  float hic = dht.computeHeatIndex(t, h, false);

  Serial.print("Humidity: ");
  Serial.print(h);
  Serial.print(" %\t");
  Serial.print("Temperature: ");
  Serial.print(t);
  Serial.print(" *C ");
  Serial.print(f);
  Serial.print(" *F\t");
  Serial.print("Heat index: ");
  Serial.print(hic);
  Serial.print(" *C ");
  Serial.print(hif);
  Serial.println(" *F");
}
```

####Credit

[Library by Adafruit/Lady Ada](https://github.com/adafruit/DHT-sensor-library)
