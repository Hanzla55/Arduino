# JOY STICK



### RESUMEN





### IMAGEN






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
