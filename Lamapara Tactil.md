# LAMPARA TACTIL



### RESUMEN


I did this project with ![STIVEN](https://github.com/St1v3n3223). In this project we connected



a led and an aluminium foil with circuit and arduino. The basic funcion of this is 




when we touch the aluminium foil the Led turns on and when we take away our hand from 


the foil the LED turns off.







### IMAGEN

![](https://raw.githubusercontent.com/St1v3n3223/Arduino/main/WhatsApp%20Image%202022-01-26%20at%2013.05.50.jpeg)



### CODIGO

``` c++

#include <CapacitiveSensor.h>
CapacitiveSensor capSensor = CapacitiveSensor(4, 2);


int threshold = 100;
const int ledPin = 12;


void setup() {
 Serial.begin(9600);
 pinMode(ledPin, OUTPUT);
}

void loop() {
 
  long sensorValue = capSensor.capacitiveSensor(30);

   Serial.println(sensorValue);

  


  if (sensorValue > threshold) {
    
    digitalWrite(ledPin, HIGH);
  }https://github.com/St1v3n3223
  
  else {
    
    digitalWrite(ledPin, LOW);
  }

  delay(10);
}
```
