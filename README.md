# Practica ESP32 con DHT22
Este repositorio muestra la segunda practica del diplomado de como podemos programar una ESP32 con el sensor DHT11.

## Introducción

### Descripción

La ```Esp32``` la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (```DTH22```) para obtener temperatura y humedad; Esta practica se usara un simulador llamado [WOKWI](https://wokwi.com/).


## Material Necesario

A continuacion se utilizaron los siguientes materiales.

- [WOKWI](https://https://wokwi.com/)
- Tarjeta ESP 32
- Sensor DHT22



## Instrucciones

### Requisitos previos

Para realizar la practica de este repositorio se necesita entrar a la plataforma [WOKWI](https://https://wokwi.com/).


### Instrucciones de preparación de entorno 

1. Abrir la terminal de programación y colocar la siguente codigo:

```
#include "DHTesp.h"
#include <LiquidCrystal_I2C.h>

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}

```


2. Instalar la libreria de **DHT sensor library for ESPx**.
   - Seleccionar pestaña de Librery Manager --> Add a New library --> Colocamos el nombre de libreria 

![](https://github.com/YasminZagal/PRACTICA-N-2/blob/main/agregar%20libreria.jpg)

3. Realizar la conexion de **DHT22** con la **ESP32** de la siguiente manera.

![](https://github.com/YasminZagal/PRACTICA-N-2/blob/main/conexion%20esp32.jpg)

### Instrucciónes de operación

1. Iniciar simulador.
2. Visualizar los datos en el monitor serial.
3. Colocar la temperatura y humedad dando *doble click* al sensor **DHT22** 

## Resultados

Una vez terminado iniciamos simulacion y se observaran los valores dentro del monitor serial.

![](https://github.com/YasminZagal/PRACTICA-N-2/blob/main/resultado%20practica.jpg)
