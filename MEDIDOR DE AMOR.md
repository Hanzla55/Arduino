# LOVE-O-METER

# INTRODUCCIÓN

Este es un programa que mide la temperatura y enciende LEDs.

## Resumen/Montaje

 Tal como lo ha estado haciendo en proyectos anteriores, conectar la placa de 
 pruebas a la alimentación y a masa.
 Conectar el cátodo (terminal corto) de cada diodo LED a masa a través de una 
 resistencia en serie de 220 ohmios. Conectar los ánodos de los LEDs  a los 
 terminales 2, 3 y 4 respectivamente. Estos diodos serán los indicadores de este 
 proyecto.
 Colocar el sensor de temperatura TMP36 sobre la placa de pruebas con la parte 
 curvada de su cuerpo mirando hacía el lado contrario de la placa Arduino (la 
 colocación de los terminales es importante) como se muestra en la figura 2. 
 Conectar el terminal de la izquierda de la cara plana del cuerpo a la alimentación 
 y el terminal derecho a masa. Conectar el pin central al pin A0 de la placa 
 Arduino. Este pin es la entrada analógica 0.

 ## El código 

 Las constantes son similares a las variables (guardar información) las cuales permiten usar
un único nombre con los datos del programa, pero a diferencia de las variables su 
contenido no se puede cambiar.

Dentro del bloque de la configuración “setup()” vamos a usar un nuevo comando, 
Serial.begin()

La siguiente instrucción for() define algunos de los pins como salidas digitales dentro de 
un bucle. Algunos de estos pins ya se han usado con los LEDs en el proyecto anterior. 

El siguiente bloque de código es el programa en sí, el cual comienza con la función loop(). 
Aquí se usa una variable llamada Valor_del_Sensor en donde se guarda la lectura del 
sensor.

``` C++

const int sensorPin = A0;
const float baselineTemp=32.0;

void setup(){

Serial.begin(9600); // abre un puerto en serie

for(int pinNumber = 2; pinNumber<5; pinNumber++){
  
pinMode(pinNumber,OUTPUT);

digitalWrite(pinNumber, LOW);

}
}

void loop(){

int sensorVal = analogRead(sensorPin);
Serial.print("Sensor Value: ");

Serial.print(sensorVal);

// convierte la lectura del ADC a voltaje

float voltage = (sensorVal/1024.0) * 5.0;

Serial.print(", Volts: ");

Serial.print(voltage);

Serial.print(",degrees C: ");

// convierte el voltaje a temperatura en grados

float temperature = (voltage - 0.5) * 100;

Serial.println(temperature);

if(temperature < baselineTemp){

digitalWrite(2,LOW);

digitalWrite(3,LOW);

digitalWrite(4, LOW);

}else if(temperature >= baselineTemp+2 && temperature < baselineTemp+4){

digitalWrite(2, HIGH);

digitalWrite(3, LOW);

digitalWrite(4, LOW);

}else if(temperature >= baselineTemp+4 && temperature < baselineTemp+6){

digitalWrite(2, HIGH);

digitalWrite(3, HIGH);

digitalWrite(4, LOW);

}else if(temperature >= baselineTemp+6){


digitalWrite(2, HIGH);

digitalWrite(3, HIGH);

digitalWrite(4, HIGH);
}
delay(1);
}
```
### IMAGENS

If we push some force on the sensor

the temperature goes above 32degrees centigrade

that is baseline temperature the leds turn on.

![](https://github.com/Hanzla55/Arduino/blob/main/MEDIDOR%201.png?raw=true)

And if we don't push the sensor

the temperature goes down 32degrees centigrades

that is baseline temperaturethe leds turn off.

![](https://github.com/Hanzla55/Arduino/blob/main/MEDIDOR%202%20.png?raw=true)
