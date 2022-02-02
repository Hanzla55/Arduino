# SENSOR DE TEMPERATURA Y HUMEDAD



### RESUMEN


i did this project with Stiven. In this project we made a circuit

in which we connected a KY-015 Sensor with arduino it has three pins one 

which has a ''S'' sign connects with digital pin 8  middle one connects

with 5volts and the last one connects with GROUND (GND). The function

of this sensor is to measure the temperature and humidity of the

surface where it is located.




### IMAGEN

![](https://raw.githubusercontent.com/St1v3n3223/Arduino/f088f14a1550cf7ff36557885fa03086017dc371/WhatsApp%20Image%202022-02-02%20at%2012.35.34.jpeg)




### CODIGO

```C++

#include "DHT.h
  "

const int sensor_pin_ky015 = 10;            //pin por donde entra la señal del KY-015
#define DHT1 DHT11

float humedad_ky015;                        //aqui almacenamos la humedad leida del ky-015
float temperatura_ky015;

DHT dht11(sensor_pin_ky015, DHT11);


void setup() {
   Serial.begin(9600); 
    dht11.begin ();

}

void loop() {
  delay(2000);                              //esperamos 2 segundos antes de empezar

  //Leemos el sensor y almacenamos los valores
  humedad_ky015 = dht11.readHumidity();             //leemos la humedad y almacenamos
  temperatura_ky015 = dht11.readTemperature();      //leemos la temperatura y almacenamos
  //Comprobamos si la lectura a fallado. La instruccion isnan, comprueba si la variable
  //que le pasamos tiene un valor representativo.  
  //Primero al dht11 incluido en la placa ky-015
  if (isnan(humedad_ky015) || isnan(temperatura_ky015)) {
    //Si la lectura es incorrecta
  
  Serial.print ("Error de lectura en KY-015");    //mostramos el mensaje de error en el serial
  }

   else {
    Serial.print("KY-015: ");               //mandamos texto al visor serie
    Serial.print("Humedad = ");             //mandamos texto al visor serie
    Serial.print(humedad_ky015,1);          //mandamos el valor medido de humedad con 1 decimal
    Serial.print(" %\t");                   //mandamos el simbolo % y un tabulador
    Serial.print("Temperatura = ");         //mandamos texto al visor serie
    Serial.print(temperatura_ky015,1);      //mandamos el valor medido de temperatura con 1 decimal
    Serial.println("ºC");                     //mandamos texto al visor serie
  }
   }
```
