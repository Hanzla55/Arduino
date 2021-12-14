# INSTUMENTO DE TECLADO

# RESUMEN

I did this project with Abril.

In this project we made a cicuit 

by which we can make the sound of a piano 

by pressing the bottons.we put a code into it 

through arduino. While doing this we faced a problem 

but we solved it by doing a little bit changes in 

the code ,hence it is controlled by software so we 

can make many more changes in it by applying different 

types of code.

# IMAGEN
Aqui esta imagen de circuito que hemos hecho

![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/instumento%20de%20teclado.jpg)



# CODIGO

``` C++

int notes[] = {262, 294, 330, 349};

void setup() {
  //start serial communication
  Serial.begin(9600);
}

void loop() {
  // create a local variable to hold the input on pin A0
  int keyVal = analogRead(A0);
  // send the value from A0 to the Serial Monitor
  Serial.println(keyVal);

  // play the note corresponding to each value on A0
  if (keyVal > 1010) {
    // play the first frequency in the array on pin 8
    tone(8, notes[0]);
  } else if (keyVal >= 990 && keyVal <= 1010) {
    // play the second frequency in the array on pin 8
    tone(8, notes[1]);
  } else if (keyVal >= 505 && keyVal <= 515) {
    // play the third frequency in the array on pin 8
    tone(8, notes[2]);
  } else if (keyVal >= 5 && keyVal <= 10) {
    // play the fourth frequency in the array on pin 8
    tone(8, notes[3]);
  } else {
    // if the value is out of range, play no tone
    noTone(8);
  }
}

```


# INSTRUMENTO DE TECLADO CON KILL SWITCH

### RESUMENSerial.println(keyVal);

EN ESTE PROJECTO QUE HECHO CON ABRIL HEMOS 

AÑADIDO UN BOTON QUE ENCIENDA O APAGUE

EL CIRCUITO de INSTRUMENTO DE TECLADO SI 

PULSO BOTON SE ENCIENDA CIRCUITO Y SI 

PULSO EL BOTON OTRA VES EL CIRCUITO SE 

APAGA.

### CODIGO

``` C++

int switchState = 0 ;
bool isTheButtonBeingPressed = false;
bool play = false;
const int buttonPin =6;

// create an array of notes
// the numbers below correspond to the frequencies of middle C, D, E, and F
int notes[] = {262, 294, 330, 349};

void setup() {
  //start serial communication
  Serial.begin(9600);
  pinMode(buttonPin, INPUT);
}

void loop() {
  checkButton();
  if (play) {
   playKeyboard();
  }
}

void checkButtSerial.println(Serial.println(keyVal);keyVal);on(){
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

void playKeyboard() {
    // create a local variable to hold the input on pin A0
  int keyVal = analogRead(A0);
  // send the value from A0 to the Serial Monitor
  Serial.println(keyVal);

  // play the note corresponding to each value on A0
  if (keyVal > 1010) {
    // play the first frequency in the array on pin 8
    tone(8, notes[0]);
  } else if (keyVal >= 990 && keyVal <= 1010) {
    // play the second frequency in the array on pin 8
    tone(8, notes[1]);
  } else if (keyVal >= 505 && keyVal <= 515) {
    // play the third frequency in the array on pin 8
    tone(8, notes[2]);
  } else if (keyVal >= 5 && keyVal <= 10) {
    // play the fourth frequency in the array on pin 8
    tone(8, notes[3]);
  } else {
    // if the value is out of range, play no tone
    noTone(8);
  }
}
```
