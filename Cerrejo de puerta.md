# CERREJO DE PUERTA





### RESUMEN

I did this project with my classmate 1![Stiven](https://github.com/St1v3n3223/).

The name of the project is Cerrejo de Puerta (KnockLock)

So in this project we made a circuit in which we made 

a prototype model to how to open and close a door.

so as you see in the image of the circuit that is given 

below if we press the button the door closes and red light 

turns on and you also see a sensor in the image if we 

touch that sensor 3 times or knock near the it,the yellow 

light flashes 3 times and then the door is opened and the 

green light turns on.











### IMAGEN


![](https://github.com/St1v3n3223/Arduino/blob/main/WhatsApp%20Image%202022-01-26%20at%2010.24.18.jpeg?raw=true)

### CODIGO



Copiado este codigo por starterkit de arduino que esta dentro de applicacion deArduino.

``` C++



#include <Servo.h>
Servo myServo;

const int piezo = A0;      
const int switchPin = 2;    
const int yellowLed = 3;   
const int greenLed = 4;    
const int redLed = 5;   


int knockVal;
int switchVal;


const int quietKnock = 10;
const int loudKnock = 100;


bool locked = false;
int numberOfKnocks = 0;

void setup() {
  
  myServo.attach(9);
  pinMode(yellowLed, OUTPUT);
  pinMode(redLed, OUTPUT);
  pinMode(greenLed, OUTPUT);
  pinMode(switchPin, INPUT);
  Serial.begin(9600);

  
      Serial.println("the box is unlocked!");

     
    }
  }
}


bool checkForKnock(int value) {
  
  
  if (value > quietKnock && value < loudKnock) {

    
    
    digitalWrite(yellowLed, HIGH);
    delay(50);
    digitalWrite(yellowLed, LOW);
    
  digitalWrite(greenLed, HIGH); 
  myServo.write(0);
  Serial.println("the box is unlocked!");
}

void loop() {

  
  if (locked == false) {
    switchVal = digitalRead(switchPin);

    
    if (switchVal == HIGH) {
      locked = true;
      digitalWrite(greenLed, LOW);
      digitalWrite(redLed, HIGH);
      myServo.write(90);
      Serial.println("the box is locked!");
      delay(1000);
    }
  }

  
  if (locked == true) {
    knockVal = analogRead(piezo);
    if (numberOfKnocks < 3 && knockVal > 0) {
      if (checkForKnock(knockVal) == true) {
         numberOfK
      Serial.println("the box is unlocked!");

     
    }
  }
}


bool checkForKnock(int value)// unlock the box
 locked = false;
// move the servo to the unlo// unlock the box
 locked = false;
// move the servo to the unlocked position
 myServo.write(0);
// wait for it to move
 delay(20);
// change status LEDs
 digitalWrite(greenLed,HIGH);
 digitalWrite(redLed,LOW);
 Serial.println("the box is unlocked!");cked position
 myServo.write(0);
// wait for it to move
 delay(20);
// change status LEDs
 digitalWrite(greenLed,HIGH);
 digitalWrite(redLed,LOW);
 Serial.println("the box is unlocked!"); {
  
  
  if (value > quietKnock && value < loudKnock) {

    
    
    digitalWrite(yellowLed, HIGH);
    delay(50);
    digitalWrite(yellowLed, LOW);
    nocks++;
      }

      
      Serial.print(3 - numberOfKnocks);
      Serial.println(" more knocks to go");
    }

    
    if (numberOfKnocks >= 3) {
      locked = false;
      myServo.write(0);
      delay(20);
      digitalWrite(greenLed, HIGH);
      digitalWrite(redLed, LOW);
      Serial.println("the box is unlocked!");

     
    }
  }
}


bool checkForKnock(int value) {
  
  
  if (value > quietKnock && value < loudKnock) {

    
    
    digitalWrite(yellowLed, HIGH);
    delay(50);
    digitalWrite(yellowLed, LOW);
    
    Serial.print("Valid knock of value ");
    Serial.println(value);
    
    return true;
  }
  
  else {
    // print status
    Serial.print("Bad knock value ");
    Serial.println(value);
    
    return false;
  }
}
```
