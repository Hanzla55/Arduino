



## CODIGO 
``` C++

int switchState = 0 ;
bool isTheButtonBeingPressed = false;
bool play = false;

int buttonPin = 6;
void setup(){
 pinMode (3, OUTPUT);
 pinMode (4, OUTPUT);
 pinMode (5,OUTPUT);
 pinMode (2,INPUT);
 pinMode(buttonPin, INPUT);
}

void loop(){
  checkButton();
  if (play) {
  encenderLuces(); 
  }
  else {
    apagarLuces();
  }
}
 
void apagarLuces(){
    digitalWrite (3, LOW);
  digitalWrite (4,LOW );
  digitalWrite (5,LOW);
}

void encenderLuces(){
  
switchState = digitalRead (2);


// esto es un comentario  

if  (switchState == LOW ){
  // el boton no esta pulsado 





  digitalWrite (3, HIGH);
  digitalWrite (4,LOW );
  digitalWrite (5,LOW);
}
  else {
    digitalWrite (3, LOW);
    digitalWrite (4,LOW);
    digitalWrite(5,HIGH);
    delay (250);
    digitalWrite (4,HIGH);
    digitalWrite (5,LOW);
    delay (250);
  }
}

void checkButton(){
  switchState = digitalRead(buttonPin);
  if (switchState == HIGH && !isTheButtonBeingPressed){
    play = !play;
    isTheButtonBeingPressed = true;
  }
  
  if (switchState == LOW)
  {
  isTheButtonBeingPressed = false;
  }
}
```
