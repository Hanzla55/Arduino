# Interfaz De Nave Espacial


## Resumen





## Processo de montaje
Materials necessario 
circuito
foto del circuito


## Codigo


``` C++
int switchState = 0 ;

void setup(){
 pinMode (3, OUTPUT);
 pinMode (4, OUTPUT);
 pinMode (5,OUTPUT);
 pinMode (2,INPUT);
}

void loop(){
 
switchState = digitalRead (2);


// esto es un comentario  

;if  (switchState == LOW ){
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
```



## Resultado
Aqui hay fotos al final
![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/Interfaz%20DE%20nave.jpg)
![](https://raw.githubusercontent.com/Hanzla55/Arduino/main/interfaz%20de%20nave.jpg)




## Variaciones
anadir boton por hardware 
vamos anadir un boton pin 3 de tal forma que solo cuando se pulse  el led 3 se encendero. el visto de proyecto (hardware y software) es mismo.






