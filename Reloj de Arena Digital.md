# Relloj de Arena Digital

### Resumen

I did this project with ![Alejandro](https://github.com/Baelyn1/1-Trimestre/commits?author=Baelyn1) 


In this project we made a circuit ìn which if we do movement near the board or if we touch the board


all the leds turn off and after some delay they start turning on one by one. it is because it has 


a sensor(tilt switch) in the board of black colour that you can see in the photos 


given below.



### Imagenes



![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/reloj%201.jpg)




![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/reloj%202.jpg)





![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/reloj%203.jpg)






![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/reloj%204.jpg)







### Codigo

``` C++

const int switchPin = 8;

unsigned long previousTime = 0;

int switchState = 0;
int prevSwitchState = 0;

int led = 2;

long interval = 200;

void setup() {
  for (int x = 2; x < 8; x++) {
    pinMode(x, OUTPUT);
  }
  pinMode(switchPin, INPUT);
}
void loop() {
  unsigned long currentTime = millis();

  if (currentTime - previousTime > interval) {
    previousTime = currentTime;

    digitalWrite(led, HIGH);
    led++;
    if (led == 7) {
    }

  }
  switchState = digitalRead(switchPin);

  if (switchState != prevSwitchState) {
    for (int x = 2; x < 8; x++) {
      digitalWrite(x, LOW);
    }
    led = 2;
    previousTime = currentTime;
  }
  prevSwitchState = switchState;
}
```



### Variacion 1


### Resumen


In this variation the circuit is same but we make a


little bit changes in the code like in the 5th line we wrote


int led = 7;  instead of int led = 2 and then


in the 18th line we wrote led--;  instead of led++;


and at last in the 27th line we wrote led = 7; instead of led = 2;


### Codigo


``` C++


const int switchPin = 8;

unsigned long previousTime = 0;

int switchState = 0;
int prevSwitchState = 0;

int led = 7;

long interval = 200;

void setup() {
  for (int x = 2; x < 8; x++) {
    pinMode(x, OUTPUT);
  }
  pinMode(switchPin, INPUT);
}
void loop() {
  unsigned long currentTime = millis();

  if (currentTime - previousTime > interval) {
    previousTime = currentTime;

    digitalWrite(led, HIGH);
    led--;
    if (led == 7) {
    }

  }
  switchState = digitalRead(switchPin);

  if (switchState != prevSwitchState) {
    for (int x = 2; x < 8; x++) {
      digitalWrite(x, LOW);
    }
    led = 7;
    previousTime = currentTime;
  }
  prevSwitchState = switchState;
}
```
