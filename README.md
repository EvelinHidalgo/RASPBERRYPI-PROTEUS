**TUTORIAL PARA SIMULADOR EN RASPBERRY PI EN PROTEUS**

**RASPBERRY PI 3 **

La Raspberry Pi es una computadora de bajo costo y con un tamaño compacto, del porte de una tarjeta de crédito, puede ser conectada a un monitor de computador o un TV, y usarse con un mouse y teclado estándar. Es un pequeño computador que correo un sistema operativo Linux capaz de permitirle a las personas de todas las edades explorar la computación y aprender a programar lenguajes como Scratch y Python. Es capaz de hacer la mayoría de las tareas típicas de un computador de escritorio, desde navegar en internet, reproducir videos en alta resolución, manipular documentos de ofimática, hasta reproducir juegos.
Raspberry Pi 2 B es un equipo completo en una pequeña placa de circuito, compuesto por un procesador ARMv7, 4 puertos USB, conexión HDMI, Ethernet y mucho más. Gracias a su procesador ARMv7 soporta el rango completo de distribuciones ARM GNU/Linux (Raspbian, XBMC, Snappy Ubuntu Core) y Microsoft Windows 10.  Soporta herramientas de software libre como KOffice, Python, GNU IceCat, etc. Permite un uso flexible en: Juegos, Multimedia, Trabajo, Educación, Proyectos, etc.

**Características**

**•	Microprocesador:** Broadcom BCM2836 de 900 MHz ARM quad core Cortex-A7 de cuatro núcleos
GPU: VideoCore IV de doble núcleo con soporte de Open GL ES 2.0, hardware acelerado OpenVG hasta 1080p30 H.264

**•	RAM:** 1GB SDRAM LPDDR2

**•	Almacenamiento:** tarjeta MicroSD para el Sistema Operativo

**•	Vídeo:**

HDMI 1.3 y 1.4 tamaño estándar a 1080p con soporte CEC para control desde el mando del televisor

Salida de vídeo compuesto (PAL/NTSC) tipo jack de de 3,5 mm 4 polos

**•	Audio:**

Audio digital por salida HDMI

Salida de audio estéreo compartida con la salida de vídeo compuesto

**•	Red:** Ethernet RJ45 10/100 BaseT

**•	USB:** 4 x USB 2.0

**•	Otros:**

Conector MPI CSI-2 de 15 vías para cámara de vídeo HD Raspberry Pi

Conector de interfaz serie de display de 15 vías

**GPIO:** 40 x pin conector macho

**•	Sistemas Operativos disponibles para Raspberry Pi más:**

Snappy Ubuntu Core versión alfa

Windows 10 aún en desarrollo

**•	Alimentación:** +5 V a 2 A a través de conector hembra microUSB

**•	Tamaño:** 86 x 56 x 20 mm

**ESPICIFICACIONES HADWARE RASPBERRY PI 3**

![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img1.jpg)

**1.microUSB:** Es el sistema de alimentación de la Raspberry, con un cargador dé móvil microUSB común podemos darle corriente. Es recomendable que sea de al menos 2A para un funcionamiento estable.

**2.GPIO:** Estos puertos son una de las cosas que diferencia a la Raspberry de un PC clásico. Mediante estas entradas y salidas de propósito general podremos hacer que nuestra Rasp interactue con el exterior abriendo y cerrando contactos, encendiendo LEDs, conociendo el estado de un interruptor, etc. Seguro que algunos Nergizos ya os habréis dado cuenta de por donde van los tiros. Son un total de 40 puertos de los cuales 26 se pueden usar como entradas/salidas.

**3.USB:** La versión 2 B cuenta con 4 puertos USB para lo que lo necesitemos, en mi caso los he usado para un adaptador WIFI y un teclado/ratón inalámbrico, quedando dos libres para discos duros externos, memorias USB, etc…

**4.microSD:** En la cara trasera de la Raspberry debemos insertar una tarjeta microSD donde se guardará el sistema operativo. Nuestros archivos también podemos guardarlos aquí o en una memoria USB (o disco duro) externos. Es recomendable una microSD de al menos 4GB y clase 10.

**5.HDMI:** A través de un cable HDMI podemos conectar la Raspberry a la TV u otro monitor para poder interactuar con ella, aunque realmente no es 100% necesario ya que, como veremos más adelante, podemos acceder a ella en remoto desde otro PC, smartphone, etc.

**6.Audio 3,5mm:** Por si queremos conectar unos cascos, altavoces u otro tipo de dispositivo de audio.

**7.Ethernet:** Para dotar a la Raspberry de conexión a internet podemos usar este puerto o un USB WIFI como he hecho yo.
**8.Display DSI:** Existen pequeñas pantallas táctiles con conector de este tipo que podemos acoplar a la Raspberry y hacernos una pseudo-tablet.

**DIAGRAMA PINES RASPBERRY PI**

![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img2.png)

**Pines GPIO para Raspberry Pi 3**

•	Amarillo (2): Alimentación a 3.3V.

•	Rojo (2): Alimentación a 5V.

•	Naranja (26): Entradas / salidas de propósito general. Pueden configurarse como entradas o salidas. Ten presente que el nivel alto es de 3.3V y no son tolerantes a tensiones de 5V.

•	Gris (2): Reservados.

•	Negro (8): Conexión a GND o masa.

•	Azul (2): Comunicación mediante el protocolo I2C para comunicarse con periféricos que siguen este protocolo.

•	Verde (2): Destinados a conexión para UART para puerto serie convencional.

•	Morado (5): Comunicación mediante el protocolo SPI para comunicarse con periféricos que siguen este protocolo.
Es importante saber que todos los pines son de tipo "unbuffered", es decir, no disponen de buffers de protección y puedes dañar la placa con un mal uso.

**Existen 2 formas de numerar los pines de la Raspberry Pi, en modo GPIO o en modo BCM.**

En el modo GPIO, los pines se numeran de forma física por el lugar que ocupan en la placa (representados por el color gris) viene siendo igual para todas las versiones (se comienza a contar desde arriba a la izquierda y finalizamos abajo a la derecha).
En el modo BCM, los pines se numeran por la correspondencia en el chip Broadcom (que es la CPU de la Raspberry Pi).

**NOMENCLATURA GPIO Y BCM**

![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img3.png)

Los pines de la Raspberry Pi 2 modelo B no dispone de ningún convertidor de analógico a digital. Esto quiere decir que para medir valores de sensores analógicos necesita utilizar un convertidor externo o un Arduino en la mayoría de los casos.

**PROTECCIÓN DE GPIO**

Cuando se utilizan los pines de GPIO para interfaz con hardware de cualquier tipo hay que poner mucho cuidado para no dañar la propia Raspberry Pi. Es muy importante comprobar los niveles de tensión y la corriente solicitada. Los pines de GPIO pueden generar y consumir tensiones compatibles con los circuitos de 3.3V (no son tolerantes a 5V) y pueden sacar hasta 16 mA. Eso es suficiente para iluminar un LED.
Sin embargo hay que tener presente que la corriente que sale de esos pines proviene de la fuente de alimentación de 3.3V y esta fuente está diseñada para una carga pico de unos 3 mA por cada pin de GPIO. Es decir, aunque el SoC de Broadcom permita drenar hasta 16 mA por cada pin la fuente no podrá dar más de unos 78 mA en total (51 mA en los modelos originales). 

**PROTEUS**

Proteus es un completo programa quepermite diseñar y simular circuitos electrónicos de forma práctica y accesible. Su competencia más directa son MultiSIM y OrCAD. Cada uno es mejor en algún aspecto, por ejemplo en digital o en analógica o en mayore librerías.
A todos aquellos que trabajen en el ámbito de la electrónica les interesará la aplicación Proteus. Se trata de un completo programa que permite diseñar y simular circuitos electrónicos de forma práctica y accesible. Proteus está formado por dos utilidades principales: ARES e ISIS, y por los módulos Electra y VSM. Si necesitas crear componentes con Proteus e ISIS será una tarea fácil. Prueba las herramientas ARES e ISIS de Proteus al descargar el programa.

![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img27.jpg)

**Se compone de 4 módulos: **	

**ISIS:** es el encargado de realizar el modelo esquemático del circuito, para ello cuenta conuna librería de más de 6,000 dispositivos tanto analógicos como digitales. 

**ARES:** se encarga de hacer la placa de circuito impreso (PCB) además de que puede posicionar automáticamente los componentes y hacer las pistas. 

**Prospice:** tal vez el componente más importante, pues se encarga de simular el comportamiento del circuito. 

**VSM:** los que han trabajado con micro-controladores en Proteus sabrán lo útil que es este módulo. Te permite simular el comportamiento de un micro-controlador de las familias PIC, AVR, y otras, sólo le cargas el archivo HEX y Proteus lo simula, ademas puede interactuar con diferentes periféricos. 

**Principales características**

•	La aplicación ISIS permite generar circuitos reales, y comprobar su funcionamiento en un PCB (printed circuit board).

•	Entorno de diseño gráfico de esquemas electrónicos fácil de utilizar y con efectivas herramientas.

•	Entorno de simulación con la tecnología exclusiva de Proteus de modelación de sistemas virtuales (VSM).

•	Herramienta ARES para el enrutado, ubicación y edición de componentes, utilizado para la fabricación de placas de circuito impreso.

•	Interfaz intuitivo y atractivo estandarizado para todos los componentes de Proteus.

•	Proteus cuenta con una gran cantidad de funciones para trabajar con circuitos electrónicos. Por ejemplo, permite generar pistas de cobre de forma automática. Además, permite la simulación de PICs casi a tiempo real, de forma que podemos comprobar si el circuito creado funciona de la forma que esperábamos.

•	No esperes más para probar ARES e ISIS de Proteus. Descarga la aplicación y comprueba sus múltiples ventajas.

**MANUAL DE USUARIO**

**1.** Ingresar al programa Proteus.Click en New Project

![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img4.png)

**2.** Ingresar el nombre con el que queremos guardar la simulación en este caso “Simulación Raspberry Pi” y el lugar donde se va a guardar el archivo.Click en next.

   ![](https://github.com/EvelinHidalgo/RASPBERRYPI-PROTEUS/blob/master/img/img4.png)

**3.**  Click en Create a schematic from the selected template-Landscape A2.Click en next.


**4.** Click en Do not create a PCB layout from the select template.Click en next.

**5.** Click en Create Flowchart Project.Click en next.

**6.** Click en Create Flowchart Project.

**7.** En el espacio Family escoger Raspberry Pi. Click en next.  Click en Finish.

**8.** Se abrirá una nueva ventana y para ejemplificar una simulación con una raspberry pi se utilizará un led y un botón .Click derecho en RPI3(U1) – Add Peripheal.

**9.** Se abrirá una nueva ventana.Click en Breakout Peripherals.

**10.** Se abrirá una nueva ventana.Elegir LED(Blue) y Momentary Action Push Button.Click en add.

**11.** Se puede observar que en la parte izquierda de la ventana Visual Designer ya se añadió el botón y el led y en la ventana Schematic Capture también.

**12.** Es importante elegir los pines a utilizarse de la Rapberry Pi en este caso el pin GPIO5 para el led Y GPIO21 para el botón.

**13.** En la ventana Visual designer es necesario generar el diagrama de flujo para representar el proceso que realizará la Raspberry Pi

**14.** Al terminar el diagrama de flujo click en la parte izquierda para simular.Se observa que se abre una nueva ventana donde aparecen los componentes añadidos con anterioridad.

**15.** Finalmente se puede observar la simulación de la Raspberry Pi ejemplificada con un led que se prende cada vez que se pulse el botón.

**BIBLIOGRAFÍA**

[1]Rodríguez,E.(2018).De cero a maker todo lo necesario para empezar con Raspberry Pi.Recuperado de: https://www.xataka.com/makers/cero-maker-todo-necesario-para-empezar-raspberry-pi

[2]Ortega & Gasset.(2020).enerxia.net.PROTEUS(ARES e ISIS)Control de GPIO con Python en Raspberry Pi.Recuperado de: https://www.enerxia.net/portal/index.php?option=com_content&view=article&id=406:electronica-proteus-simulador-digital-y-analogico&catid=61&Itemid=142
