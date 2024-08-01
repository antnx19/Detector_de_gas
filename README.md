# Detector_de_gas
Repositorio de proyecto IoT

Repositorio del Proyecto Detector de aire en interiores y deteccion de fugas de gas 
Por Jesus Garcia Antunez y Omar Gabriel Rosas Ortega

## Contenidos
* [Introduccion](#Introduccion)
* [Objetivo](#Objetivo)
* [Objetivos-Especificos](#Objetivos-Especificos)
* [Materiales](#Materiales)
* [Hardware](#Hardware)
* [Sofware](#Software)
* [Coneccion](#Coneccion)
* [Configuracion_en_ArduinoIDE](#Configuracion_en_ArduinoIDE)
* [Bot](#Bot_telegram)
* [Node-Red](#Node-Red)
  

<a id="Introduccion"></a>
# Introduccion 

El monitoreo de gases es un aspecto fundamental en diversas aplicaciones de Internet de las Cosas (IoT), desde la domotica hasta el monitoreo de la calidad del aire en las ciudade o areas de trabajo. 
Los sensores de gas desempenan un papel esencial en estas aplicaciones, proporcionando datos cruciales sobre la concentracion de gases especificos en el ambiente para la prevencion de accidentes o enfermedades causadas por la mala calidad del aire.
 
 Este proyecto se centra en la creacion de un dispositivo que sea capaz de detectar la calidad del aire y detectar fugaz de gas; mediante la utilizacion de los sensores de gas MQ6 y MQ135.

 Estos sensores se integran a un microcontrolador ESP32CAM para dar lecturas en tiempo real.
 Tambien para su utilizacion sin coneccion a internet se le agregan tres leds (verde, amarilllo y rojo).
 Verde indicando niveles normales de gas 
 Amarillo indicando niveles moderados   
 Rojo indicando niveles nocivos para la salud 

 Tambien se integra un bot de Telegram que dara un alerta a un dispositivo movil, indicando las posibles accion a tomar.




<a id="Objetivo"></a>
# Objetivo 

Brindar una solución para monitorear la calidad del aire en interiores, en las industrias y hogares. Promoviendo un ambiente más saludable y seguro asi como en la prevención de accidentes por fugas de gas. 

<a id="Objetivos-Especificos"></a>
# Objetivos-Especificos

1.-Introducir en edificios corporativos y lugares cerrados, una herramienta capaz  para analizar  el trabajo y el correcto funcionamiento del aire acondicionado y la circulación para mejorar la  calidad del aire.

2.-Ofrecer un servicio que mejore las condiciones de   seguridad  en  industrias y coconas   donde se utilice gas LP o gas inflamable entre otros  y es necesario un monitoreo continuo.

3.-Implementar en el ámbito de la salud  y la medicina, el monitoreo constante de la calidad del aire en hospitales y entornos de cuidados de la salud donde es esencial para mejorar la condición de  salud de los pacientes.

4.-Adaptar  nuestro producto en el hogar  para mejorar las condiciones del aire y evitar muertes prematuras o enfermedades relacionadas con este a causa de intoxicaciones por gases o partículas.


<a id="Materiales"></a>
# Materiales 

    1 Protoboard
    1 ESP32CAM
    1 Sensor MQ6
    1 Sensor MQ135 
    1 LED verde
    1 LED amarillo 
    1 LED rojo 
    1 Cable USB
    1 Modulo FTDI
    3 Resistencias de 220 ohms
    Varios Cables jumper 

<a id="Hardware"></a>
## Hardware 

    Protoboard
    ESP32CAM
    Sensor MQ6
    Sensor MQ135 
    LED verde
    LED amarillo 
    LED rojo 
    Cable USB
    Modulo FTDI
    Resistencias de 220 ohms
    Cables jumper 

<a id="Software"></a>
# Software <a id="Software"></a>

    - IDE arduino 
    - Telegram 
    - Node-red 

<a id="Coneccion"></a>
## Coneccion
![Opera Captura de pantalla_2024-07-28_192537_edu codigoiot com](https://github.com/user-attachments/assets/03087381-c1b1-4bec-9a60-1fce1c39b509)

<a id="Configuracion_en_ArduinoIDE"></a>
## Configuracion_en_ArduinoIDE 
Ir a "Tools", seleccionar "All thinker ESP32-CAM"

En "port" seleccionar la salida USB que exista  
![bad90acf-a21b-44ee-a16a-177bbfd1dd45](https://github.com/user-attachments/assets/605a1df5-522f-4569-ab5e-51f2d5ba5449)

Puedes encontrar el código en el siguiente repositorio:

https://github.com/codigo-iot/detector-gases/tree/main/ESP32/detector-gases

Este programa establece el semáforo en verde cuanto los valores del sensor MQ6 estan debajo de 20 PPM y cuando el valor del sensor MQ135 está debajo de 400 PPM. Para el estado amarillo, los valores del MQ6 deben estar entre 20 y 50 PPM y los valores del MQ135 entre 400 y 600 PPM. Por encima de estos valores, el semáforo se vuelve rojo.

Una vez copiado el codigo, correrlo para cargarlo en la ESP32-CAM correctamente.

![4f73ab84-18bb-4edf-91e6-2f8850a51cc6](https://github.com/user-attachments/assets/752c7d00-d314-43f3-ad07-237cb073b3b2)

Comprobar el funcionamiento en la terminal serial, donde dara las lecturas del sensor MQ6 y del sensor MQ135
![image](https://github.com/user-attachments/assets/10993951-1538-4b92-9bac-ac1da9e29bd7)

<a id="Bot_telegram"></a>
# Bot_telegram
Para la configuracion de telegram revise el siguiente link: 
https://aprendiendoarduino.wordpress.com/2020/04/11/crea-un-bot-de-telegram-con-node-red/

<a id="Node-Red"></a>
# Node-Red
Se realizara un flow en node-red esto con la finalidad de que se lean los datos del microcontralador y se enviara a un bloker para poder visualizar los datos de forma coleccitiva, a la vez que tambien en dado caso se superar cierto nivel de PPM, se mandara un mensaje por medio de un bot telegram al movil.

Para eso se necesitan los siguientes nodos para que funcione correctamente:

  --Node-Red

  --Nodos Dashboard

  --Nodos Serial

  --Nodos String

  --Nodo Telegram 
![Opera Captura de pantalla_2024-07-30_143423_127 0 0 1](https://github.com/user-attachments/assets/083ccae3-2b4d-4054-8ab8-ac00355d93a4)
![Opera Captura de pantalla_2024-07-29_194259_127 0 0 1](https://github.com/user-attachments/assets/8608ac0f-1663-4179-9a31-12e753da0b56)

## Flow
Ya instalados los nodos necesarios importar el JNSON que esta en el repositorio 
![image](https://github.com/user-attachments/assets/bbf46ad0-fd4e-4354-bdd4-2e7078437523)

Para ver el dashboard de este flow, dirigete a localhost:1880/ui y selecciona la pestaña de este flow en caso de que tengas mas de 1 dashboard funcionando.

![image](https://github.com/user-attachments/assets/be5a7219-6a71-4649-b62d-400f0491b6c5)

Cada vez que se detectan mas de 1,200 PPM el bot de telegram automaticamente se manda un mensaje de alerta al movil.

![image](https://github.com/user-attachments/assets/4b87ea91-de40-4222-a4af-15ae45aa5443)
![image](https://github.com/user-attachments/assets/7f69cc01-217b-449a-a2be-83d5d2899397)
![image](https://github.com/user-attachments/assets/0adac4a7-85ae-4dc3-bc8c-1bd1549488d9)
![image](https://github.com/user-attachments/assets/b3f625b8-ec4b-4875-8f04-a03de5ea2079)
![image](https://github.com/user-attachments/assets/e0e964ca-7697-4a4b-90ea-6a01a606a1a1)

Este proyecto fue realizado en el marco del curso IoT Essentials Developer impartido por [Codigo IoT ](https://www.codigoiot.com/) y organizado por la [Asociación Mexicana del Internet de las Cosas](https://www.asociacioniot.org/).
