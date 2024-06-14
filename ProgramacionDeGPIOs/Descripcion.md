## Objetivos

• Identificar las líneas de propósito general de entrada y salida que dispone su tarjeta de desarrollo microcontroladora.
• Identificar las palabras reservadas para el IDE de Arduino, que permiten designar una GPIO como entrada o como salida de señales digitales.
• Estructurar un programa de control en lenguaje C++ para que el IDE de Arduino permita utilizar la tarjeta de desarrollo microcontroladora como cerradura electrónica para una palabra clave de ocho bits.
• Estructurar un programa de control en lenguaje C++ para el IDE de Arduino permita utilizar la tarjeta de desarrollo microcontroladora como decodificador de un código binario a código hexadecimal.

## Introducción teórica

Como parte de una buena práctica lo primero que se debe de realizar es consultar cuántas líneas de propósito general de entrada y salida (a continuación, simplemente referidas como GPIO) dispone su tarjeta de desarrollo microcontroladora, para ello se consulta el denominado PINOUT Diagram correspondiente a su tarjeta a utilizar. En la figura 1, se muestra el PINOUT Diagram de la tarjeta ESP32 DEVKIT.

**Figura 1.**

*PINOUT Diagram del Arduino UNO.*

![ESP32 DEVKIT PINOUT](\GitHub\ArduinoPracticasBasicas\ProgramacionDeGPIOs\Imagenes\ESP32 DEVKIT PINOUT.png)
