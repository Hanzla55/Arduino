## PWM (Pulse width modulation) modulaion por ancho de pulsos 

Problema tengo un arduino que suministara 5v a un led.

a mayor intensidad de corriente(A) El led brilla más

a menor intensidad de corriente el led brilla menos (ver ley de ohm)

Si subimos o bajamos el voltaje , haremos lo mismo con la intensidad

Suponiendo que la resistensia del circuito es la misma 

Entonces si connecto un led con 5v resistencia de 220 ohmios 

A un voltaje de 5v o  de 3'3v
 El led brillara mas con 5v y menos con 3'3v 
 
 ### Que es un pulso
 
 Un pulso electrico es una señal de voltaje medida en el tiempo
 
 Los ojos humanos pedemos detectar cambios hasta entorno a 12hz 
 A partir de 24-30hz no somos capaces visualmente.
 
 Los pulsos modulados en ancho crean la elusion intermedios entre 0 y 5v 
 Para ello usan pulsos muy cortos.
 
 Que usaremos a traves de funcion 
  AnalogWrite(pin, 0-255);
  
  ESta funcion solo funciona en pines con PWM
  
  Los pines con PWM estan marcados con el simbolo ~(La tilde de la eñe)
  
  La funcion nos pide dos cosas 
  por un lado (y lo primero) numero de pin y por otro lado un numero entre 0 y 255.
  
  0   0% de voltaje 
  
  255   100% de voltaje (5v)
  
  
  
  int  integez (numero entero)
  
  significa que nuestra variable es un tipo de dato nemerico no decimal . Le asigna un espacio en memoria otros tipos.
  
  String:  cadena de caracteres
  bod:  booleano y es verdadero o falso
  Char:  1 unico caracter
  float:  numeros decimals
 ### Projecto Lampara de varios colores
 Hoy yo y ![Stiven](https://github.com/St1v3n3223/) hecho un projecto que se llama lampara de varios colores
 
 Aqui esta foto de este projecto 
 
 ![](https://raw.githubusercontent.com/St1v3n3223/Arduino/main/Captura%20de%20pantalla%20de%202021-11-09%2012-05-19.png)
  VARIACIONES
 
                                          HARDWARE 
   

BOTONES:https://raw.githubusercontent.com/St1v3n3223/Arduino/main/Captura%20de%20pantalla%20de%202021-11-09%2013-53-42.png

Envez de Potenciometros

                                        SOFTWARE
Valores Diferentes
Aqui esta codigo de projecto que utilizado:

[Código](https://github.com/Hanzla55/Arduino/blob/main/Lampara_de_varios_colores.ino)

This is the part of the code that lights the LED:

``` C++
 analogWrite(redLEDPin,redValue);
  analogWrite(greenLEDPin,greenValue);
  analogWrite(blueLEDPin,blueValue);
``` 

#### Projecto 2

Imagen de projecto


![](https://raw.githubusercontent.com/St1v3n3223/Arduino/main/Captura%20de%20pantalla%20de%202021-11-09%2013-53-42.png)

