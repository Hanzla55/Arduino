# Relloj de Arena Digital

### Resumen

I did this project[Reloj de Arena Digital](https://github.com/Hanzla55/Arduino/blob/main/Reloj%20de%20Arena%20Digital.md) with Alejandro 


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
