# Umbral de nivel
mercury project

## DESCRIPCION

Descripcion del proyecto
Proyecto de control de nivel a través de un botón/switch de mercurio. 


|Item|Respuesta|
|----|-------|
|Nombre de proyecto|Umbral de nivel|
|Case|El prototipo no posee case|
|Solar o alimentación alternativa|Batería lipo|
|Entrada de datos por el usuario|SSID de access point (ESP32) / Password de access point (ESP32) / On - Off en browser (activación desactivación de lectura de sensor)|
|Etapa: 1.|Cargar el código en la ESP32 que le permita ser un access point |
|Etapa: 2.|Añadir el segmento de código a la ESP32, que le permita ser access point y obtener lecturas con el sensor a la vez |
|Etapa: 3.|Crear condicional para que el sensor solo se habilite una vez que desde un browser de un dispositivo conectado al access point de la ESP32, se haga clikc/tap en On (se deshabilita el sensor en Off) |
|2.|Producción : Agregar batería externa para brindar autonomía|
|3.|Futuro: Agregar case y sistema de flotabilidad para controlar el nivel de un fluido |
|Hardware: Dispositivo Sensor|TTGO-ESP32 con pantalla|
|Hardware: Dispositivo de Alerta|Mercury opening module con led (indicador visual) de umbral de inclinación|
|Posibles problemas|Impermeabilización del case para que se pueda conseguir contacto mínimo con líquidos|

## COMO ENSAMBLAR

El sensor de mercurio tiene 4 terminales (-, +, D, L). La conexión con la ESP32 debe ser de la siguiente manera: 

|Sensor de mercurio|Board ESP32|
|----|-------|
|Terminal -|Puerto GRD|
|Terminal +|Puerto +|
|Terminal D|Puerto 23|
|Terminal L|Puerto 5|

## COMO CARGAR EL SOFTWARE 

A través de Arduino IDE, cargar el proyecto: "test_03.ino" con las siguientes configuraciones de IDE: 

* Tools --> Board: "TTGO LoRa32-OLED V1" 
* Tools --> Frequency: "80MHz"
* Tools --> Upload speed: "115200"

##  Se documenta el uso general del proyecto

El objetivo del prototipo es que, a través de un sensor de apertura de mercurio, adaptado como "sensor de movimiento" podamos determinar el nivel de un liquido en un recipiente. 
El sensor estará anclado a un material flotante (estereofon o por definir) y a una varilla de longitud conveniente, que le permita cambiar el nivel de inclinación a través de la flotación del estereofon y de esta forma, indicar a través de un led si el líquido llegó a cierto umbral.
La alerta de umbral de nivel (inclinación) debe ser activada a través del llamado en un browser de la IP http://192.168.4.1/. 
El switch permitirá, según la opción seleccionada, habilitar (on) o deshabilitar (off) la lectura del sensor de mercurio. 
SSID y contraseña para conectarse al access point de la ESP32: 
* ssid = "test01_andres"
* password = "test123456"


