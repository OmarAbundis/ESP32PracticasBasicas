# Cerradura electrónica básica controlada mediante un ESP32DEVKIT

## Objetivos

• Identificar las líneas de propósito general de entrada y salida que dispone su tarjeta de desarrollo microcontroladora.

• Identificar las palabras reservadas para el IDE de Arduino, que permiten designar una GPIO como entrada o como salida de señales digitales.

• Estructurar un programa de control en lenguaje C++ para que el IDE de Arduino permita utilizar la tarjeta de desarrollo microcontroladora como cerradura electrónica para una palabra clave de ocho bits.

• Estructurar un programa de control en lenguaje C++ para el IDE de Arduino permita utilizar la tarjeta de desarrollo microcontroladora como decodificador de un código binario a código hexadecimal.


## Introducción teórica

Como parte de una buena práctica lo primero que se debe de realizar es consultar cuántas líneas de propósito general de entrada y salida (a continuación, simplemente referidas como GPIO) dispone su tarjeta de desarrollo microcontroladora, para ello se consulta el denominado PINOUT Diagram correspondiente a su tarjeta a utilizar. En la figura 1, se muestra el PINOUT Diagram de la tarjeta ESP32 DEVKIT.

**Figura 1.**

*PINOUT Diagram del Arduino UNO.*

![ESP32 DEVKIT PINOUT](https://github.com/OmarAbundis/ArduinoPracticasBasicas/blob/main/ProgramacionDeGPIOs/Imagenes/ESP32%20DEVKIT%20PINOUT.png)

Generalmente a la agrupación de las líneas que permiten la entrada o salida de señales digitales al microcontrolador se le denominan puertos, en algunos microcontroladores se puede realizar su programación en bloque, pero en el caso del ESP32 DEVKIT, su configuración se realiza línea a línea, indicando de qué manera se pretende utilizar.
La configuración se hace de la siguiente manera:

1.	Se realiza en la parte del programa correspondiente a void setup ()
2.	Para configurar un pin específico como INPUT (entrada) o como OUTPUT (salida), con la palabra reservada pinMode, después entre paréntesis se indica el número o el nombre del pin seguido de una coma y por último el cómo se quiere utilizar el pin como entrada o salida.

~~~
pinMode(pin,OUTPUT);          //ajusta “pin” como salida.
pinMode(pin,INPUT);          //ajusta “pin” como entrada.
pinMode(pin,INPUT_PULLUP);   //ajusta “pin” como entrada pull-up.
~~~

3.	Y en la parte de ejecución void loop (), se hace uso de las líneas de la siguiente manera:

~~~~
digitalWrite(pin,HIGH);		//”pin” configurado como salida mandará 1 lógico.
digitalWrite(pin,LOW);		//”pin” configurado como salida mandará 0 lógico.
digitalRead (pin);		    //”pin” configurado como entrada efectuara la lectura de la señal.
~~~~

## Equipo

* Fuente de voltaje de 5 Volts
* Multímetro
* Computadora Personal
* IDE de Arduino

## Materiales

1 Arduino UNO u otra tarjeta de desarrollo con microcontrolador compatible.
1 Dip Switch de 8 posiciones.
8 resistores de 10K
1 resistor de 330
1 resistor de 120
1 Display de 7 segmentos cátodo común
Protoboard
Alambre con aislante para el armado del circuito electrónico (UTP) o jumpers MM
Pinzas de punta y de corte

## Desarrollo

Para poner en práctica sus conocimientos en programación en lenguaje C++, configuración de GPIOs y desarrollo de funciones, tiene que realizar lo siguiente:

### Cerradura electrónica

Implementar una cerradura electrónica, la cual sólo activará la salida si por medio de un dip switch se pone la combinación 10101010b. Para indicar que se ha introducido la combinación correcta se deberá de activar un LED.

**Figura 2.**

*Circuito Electrónico de la Cerradura con el ESP32DEVKIT.*

![Circuito Cerradura ESP32DEVKIT](https://github.com/OmarAbundis/ArduinoPracticasBasicas/blob/main/ProgramacionDeGPIOs/Imagenes/CircuitoCerraduraElectronicaESP32DEVKIT.JPG)

### Procedimiento

Cuando se debe dar solución a un problema combinando circuitos electrónicos y programación es conveniente ser metódico en el planteamiento de la solución, a continuación se sugieren una serie de pasos que resultan útiles para obtener la solución al problema de manera simple.

1 Identificar los datos indicados en el enunciado del problema.

2 Analizar el circuito electrónico que se va a controlar.

3 Describir una serie de pasos ordenados o un diagrama de flujo que guíe en la solución del problema de una manera simple.

4 Escribir el código de programa.

5 Compilar el código para encontrar errores de sintaxis.

6 En la manera de lo posible simular el programa obtenido para identificar errores de lógica.

7 Cargar el programa en la tarjeta microcontroladora y comprobar el correcto funcionamiento del prototipo.

8 Generar un registro con las observaciones del circuito funcionando.

En base a los puntos sugeridos para la solución del problema, identificación de datos y analisis del circuito, se ha realizado el diagrama de flujo mostrado en la figura 3, el cual dentro de sus elementos ya cuenta con pseudocódigo que simplificará la tarea de la programación y de una manera grafica mostrará el camino de la solución.

**Figura 3.**

*Diagrama de Flujo para la Cerradura Electrónica Básica con el ESP32DEVKIT.*

![Circuito Cerradura ESP32DEVKIT](https://github.com/OmarAbundis/ArduinoPracticasBasicas/blob/main/ProgramacionDeGPIOs/Imagenes/DiagramaFlujoCerradura.png)



En la siguiente dirección electrónica se puede observar la simulación en Wokwi del funcionamiento de la cerradura electrónica, utilizando el ESP32DEVKIT para el control. 

[ESP32 DEVKIT Simulación](https://wokwi.com/projects/376260178423500801)
