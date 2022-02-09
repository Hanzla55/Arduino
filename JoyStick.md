# JOY STICK



### RESUMEN

I did this project with ![STIVEN](https://github.com/St1v3n3223).  In this project 


we connected a joystick and a small loud speaker with arduino. So when we move the 


joystick in the different directions the speaker make the different sounds in the each direction,


because of the code that we had put in the arduino.





### IMAGEN

![](https://raw.githubusercontent.com/St1v3n3223/1er-Trimestre/37cba7a43616c5e94d251392e592e30d3704f4d9/WhatsApp%20Image%202022-02-02%20at%2010.06.47.jpeg)





### CODIGO

``` c++
const int pinBoton = 3; 
const int pinEjeY = A1; 
const int pinEjeX = A0; 

int xaxisValue = 0;
int yaxisValue = 0;
const int freqs[] = {261.63, 293.66, 329.63, 349.23, 392, 440, 466.16, 523.25, 587.33, 587.33, 659.25,698.46, 783.99, 880, 932.33, 1046.50};

 
void setup() {
  pinMode(pinBoton, INPUT);
  digitalWrite(pinBoton, HIGH);
  Serial.begin(9600);
}
 
void loop() {
  yaxisValue = digitalRead(pinEjeY);
  Serial.print("Boton:  ");
  Serial.print(digitalRead(pinBoton));
  Serial.print("\n");
  Serial.print("Eje X: ");
  Serial.print(xaxisValue);
  Serial.print("\n"); //esto es un salto de linea
  Serial.print("Eje Y: ");
  Serial.println(analogRead(pinEjeY));
  Serial.print("\n\n");
  int noteNumber = map(yaxisValue, 1024,0,15,0);
  Serial.print(noteNumber);
  tone(8, freqs[noteNumber]);
  delay(150);
}
```
