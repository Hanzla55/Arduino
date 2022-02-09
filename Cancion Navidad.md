# CANCION DE NAVIDAD


## RESUMEN

I have done this project with ![UMER](https://github.com/umershahzad12)



in which we made a circuit to play



a chrismis song sound it can not possible only



with hardware but also with software



by putting a code into it by the



help of arduino.So how the song 



play when we turn on the button the 



song starts playing.






### IMAGEN


![](https://github.com/Hanzla55/Arduino/blob/main/cancion%20navidad.jpg?raw=true)




### CODIGO

``` C++
int switchStateKill = 0;
bool isTheButtonBeingPressed = false;
bool play = false;
// el pin 2 no sera siempre el boton
int buttonPin=6;
const int pinAltavoz = 8;
const int freqs[] = {261.63, 293.66, 329.63, 349.23, 392, 440, 466.16, 523.25, 587.33, 587.33, 659.25,698.46, 783.99, 880, 932.33, 1046.50};
const int duracionNegra = 667; 
void setup() {
  
 
  
   pinMode(buttonPin, INPUT);
}


void loop(){
    checkButton();
 if (play) {
     tocarMelodia();
  }
  

 }
/*
 * Funcion para tocar melodia
 */
 void tocarMelodia(){
     tocarNota(1,0.5);
      tocarNota(3,2);
       tocarNota(-1,1);
   }

void tocarNota(int numeroNota, float duracionNota) {
      const int pin = pinAltavoz;
      int duracionMilisegundos = duracionNegra * duracionNota;
      //
      if (numeroNota == -1){
          // tocar un silencio
          noTone(pin);
          delay(duracionMilisegundos);
      }
      else {
          // tocar una nota
          int frecuencia = freqs[numeroNota];
          
          tone(pin,frecuencia,duracionMilisegundos);
          delay(duracionMilisegundos);
    }
}


void checkButton(){
  switchStateKill = digitalRead(buttonPin);
  if (switchStateKill == HIGH){
    if (isTheButtonBeingPressed == false){
      play = !play;
      isTheButtonBeingPressed = true;
  }
}
else{
  isTheButtonBeingPressed = false;
}
}
 //vuelve al inicio del bucle
