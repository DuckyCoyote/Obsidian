## Red LAN
Una red de area local, es una red contenida dentreo de una peque;a zona geografica, normalmente dentro del mismo edificio. Las redes WIFI domesticas y las redes de pqueñas empresas son algunos ejemplos comunes de LAN.
![[Pasted image 20240524183109.png]]
### Como funcionan las LAN?
La mayoriab de las LAN se conectan a internet en un punto central: un enrutador. Las LAN domesticas suelen utilizar un unico enrutador, mientras que las LAN en espacios mas grandes pueden utilizar ademas conmutadores de red para una entrga de paquetes mas eficiente.

Las redes LAN casi siempre utilizarn Ethernet, WIFI o ambas para conectar los dispositivos de la red. Ethernet es un protocolo de conexion fisica a la red que require el uso de cables Ethernet. WIFI es un protocolo para conectar a una red mediante ondas de radio.
### ¿Qué es una LAN virtual?
Las LAN virtuales, o VLAN, son una forma de dividir el tráfico de una misma red física en dos redes. Imaginemos que se instalan dos redes LAN distintas, cada una con su propio enrutador y conexión a Internet, en la misma habitación. Las VLAN son así, pero se dividen virtualmente mediante software en lugar de físicamente mediante hardware: solo se necesita un enrutador con una conexión a Internet.

Las VLAN ayudan a la gestión de la red, especialmente en el caso de las LAN muy grandes. Al subdividir la red, los administradores pueden gestionar la red de forma mucho más fácil. (Las VLAN son muy diferentes de las [subredes](https://www.cloudflare.com/learning/network-layer/what-is-a-subnet/), que son otra forma de subdividir las redes para conseguir una mayor eficiencia).

### ¿Cuál es la diferencia entre una LAN y una WAN?
Una WAN, o red de área amplia, es un conjunto de LAN conectadas. Es una red amplia de redes locales. Una WAN puede tener cualquier tamaño, incluso miles de kilómetros de ancho; no está restringida a un área determinada.
### ¿Cómo se relacionan las LAN con el resto de Internet?

Internet es una red de redes. Las LAN suelen conectarse a una red mucho más grande, un [sistema autónomo (AS)](https://www.cloudflare.com/learning/network-layer/what-is-an-autonomous-system/). Los AS son redes muy grandes con sus propias políticas de [enrutamiento](https://www.cloudflare.com/learning/network-layer/what-is-routing/) y con control sobre ciertas direcciones IP. Un proveedor de acceso de Internet (ISP) es un ejemplo de AS.

Imaginemos que una LAN es una red pequeña que se conecta a una red mucho más grande, que se conecta a otras redes muy grandes, todas las cuales contienen LAN. Esto es Internet, y dos ordenadores conectados a dos LAN diferentes, separadas por miles de kilómetros, pueden comunicarse entre sí al enviar datos a través de estas conexiones entre redes.
[CLOUDFLARE](https://www.cloudflare.com/es-es/learning/network-layer/what-is-a-lan/)

## Red WAN
Una red de area amplia (WAN) es la tecnologia que conecta entre si a las oficinas, los centros de datos, las aplicaciones en la nube y el almacenamiento en la nube. Se denomina red de area amplia porque se extiende mas alla de un solo edificio o un gran recinto para incluit multiples ubicaciones repartidas a lo largo de una zona gerografica concreta, o incluso del mundo. Por ejemplo, las empresas con muchas sucursales internacionales utilizan una WAN para conectar las redes de las oficinas entre si. La WAN mas grande del mundo es Internet, puesto que se trata de un conjunto de muchas redes internacionales que se conectan entre si.
![[Pasted image 20240524185012.png]]
### Cual es el objetivo de una conexion WAN?
Las redes de area amplia WAN son en la actualidad el eje central de las empresas. Ante la digitalizacion de los recursos, las empresas utilizarn las WAN para hacer lo siguiente:
- Comunicarse mediante voz y video.
- Compartir los recursos entre los empleados y los clientes.
- Acceder al almacenamiento de datos y realizar copias de seguridad remotas.
- Conectar con las aplicaciones que se ejecutan en la nube.
- Ejecutar y alojar aplicaciones internas.
Las innovaciones tecnologicas de la WAN ayudan a las organizaciones a acceder a la informacion de forma segura, rapida y fiable.
Las redes WAN son importantes para la productividad y la continuidad del negocio.

### ¿En qué consiste la arquitectura de la WAN?
Las arquitecturas de redes de área amplia (WAN) se basan en el modelo de Interconexión de Sistemas Abiertos (OSI) que define y estandariza conceptualmente todas las telecomunicaciones. El modelo OSI visualiza que cualquier red informática funciona en siete capas. Diferentes tecnologías de red operan en cada una de estas diferentes capas y juntas forman una WAN que funciona.

Mostraremos estas capas en un enfoque descendente y proporcionaremos un ejemplo para facilitar su comprensión:
#### Capa 7: capa de la aplicación
La capa de aplicación es la más cercana al usuario y define cómo este interactúa con la red. Contiene la lógica de la aplicación y desconoce la implementación de la red. Por ejemplo, si tiene un sistema de reservas de calendario en la empresa, esta capa administra la lógica de las reservas, como el envío de invitaciones, la conversión de zonas horarias, etc.
#### Capa 6: capa de presentación
La capa de presentación prepara los datos para su transmisión a través de la red. Por ejemplo, incorpora cierto cifrado de manera que los delincuentes cibernéticos que vigilan la WAN no puedan hackear los datos confidenciales de las reuniones.
#### Capa 5: capa de la sesión
La capa de la sesión administra las conexiones o sesiones entre las aplicaciones locales y remotas. Puede abrir, cerrar o terminar la conexión entre dos dispositivos. Por ejemplo, el sistema de reservas se encuentra en un servidor web en la oficina central, pero usted trabaja desde casa. La capa de la sesión abre una conexión entre su computadora y el servidor web después de la autenticación. Esta conexión es una conexión lógica, no una conexión física real.
#### Capa 4: capa de transporte
La capa de transporte define las funciones y procedimientos para la transmisión de datos. Clasifica y envía los datos para su transferencia. También puede empaquetar los datos en paquetes de datos. Por ejemplo, al visitar el sitio de reservas, el protocolo de control de transmisión (TCP) administra la comunicación clasificándola en paquetes de solicitud y respuesta.
#### Capa 3: capa de red
La capa de red administra el modo en que los paquetes de datos recorren la red. Por ejemplo, define las reglas para el enrutamiento de paquetes, el equilibrio de carga y la pérdida de paquetes.
#### Capa 2: capa de enlace de datos
La capa de enlace de datos se encarga de establecer las reglas o protocolos de comunicación sobre las operaciones de la capa física. Por ejemplo, decide cuándo iniciar o finalizar una conexión directa. Esta función de capa reenvía los paquetes de un dispositivo a otro hasta que llegan a su destino.
#### Capa 1: capa física
La capa física administra la transferencia de datos sin procesar en forma de bits digitales, señales ópticas u ondas electromagnéticas a través de los diferentes medios de transmisión de la red, como las fibras ópticas y las tecnologías inalámbricas.
### ¿En qué consisten son los protocolos WAN?
Los protocolos de red de área amplia (WAN), o protocolos de red, definen las reglas de comunicación a través de cualquier red. A continuación, se muestran algunos ejemplos:
#### Retransmisión de tramas
La retransmisión de tramas es una tecnología inicial que empaqueta los datos en forma de tramas y los transmite por una línea privada a un nodo de retransmisión de tramas. La retransmisión de tramas funciona en las capas 1 y 2 y facilita la transferencia de información de una LAN a otra a través de múltiples conmutadores y enrutadores.
#### Modo de transferencia asíncrono
El modo de transferencia asíncrono (ATM) es también una de las primeras tecnologías WAN que formatea los datos en celdas de datos de 53 bytes. Los dispositivos de la red del modo ATM utilizan la multiplexación por división de tiempo, que convierte las señales digitales en celdas de tamaño fijo, las transmite y luego las vuelve a ensamblar en su destino.
#### Paquete sobre SONET/SDH
Paquete sobre SONET/SDH (POS) se trata de un protocolo de comunicación que define cómo se comunican los enlaces punto a punto cuando se utiliza la fibra óptica.
#### TCP/IP
El Protocolo de control de transmisión/protocolo de Internet (TCP/IP) define la comunicación de extremo a extremo al especificar cómo los datos se deben empaquetar, direccionar, transmitir, enrutar y recibir. IPv6 es la versión más reciente del método más utilizado.
### ¿Qué son las redes de área local?
Las redes de área local (LAN) son los componentes básicos de una WAN. Una LAN está formada por computadoras interconectadas y otros dispositivos limitados a un lugar pequeño, como un edificio, una escuela o una oficina.
#### LAN frente a WAN
Las LAN son redes más pequeñas con capacidad limitada pero con mayor velocidad. Es más fácil y más rentable diseñarlas, configurarlas y administrarlas. Son redes privadas que habitualmente utilizan una única tecnología de conexión.

Por otro lado, las WAN conectan las LAN entre sí. Una única WAN puede tener diferentes tipos de tecnologías de red para comunicarse a través de las LAN. Su velocidad de comunicación es lenta, pero su capacidad es alta. Dado que una WAN es una red de gran tamaño, puede resultar más compleja de configurar y administrar.
### ¿Cómo funciona una WAN?
Las empresas disponen de recursos que se ejecutan en diferentes centros de datos locales, sucursales y nubes virtuales privadas (VPC). Para establecer la conexión entre estos recursos, las empresas utilizan múltiples conexiones de red y servicios de Internet. Dado que las empresas no pueden construir su propia infraestructura de red a través de múltiples fronteras geográficas, suelen alquilarla a un proveedor de servicios externo.
Estos son algunos de los tipos de conexiones más comunes:
#### Líneas alquiladas
Una línea alquilada es una conexión de red directa que se puede alquilar a un proveedor de red grande, como un proveedor de servicios de Internet (ISP). Puede conectar dos puntos de conexión LAN entre sí. Las líneas alquiladas no son necesariamente líneas físicas. Es posible que sean conexiones virtuales que los proveedores de servicios implementan sobre otra infraestructura de red.
#### Túnel
El túnel es una forma de cifrar los paquetes de datos a medida que se desplazan por la Internet pública. Con la técnica del túnel, se utiliza una conexión a Internet para acceder a los servidores de la empresa en otro país. Pero se envían como paquetes encapsulados, con lo que se forma una red privada virtual (VPN) propia.
#### Conmutación de etiquetas multiprotocolo
La conmutación de etiquetas multiprotocolo (MPLS) es una técnica que dirige el tráfico de datos en función de etiquetas predeterminadas. Intenta dirigir el tráfico de datos críticos a través de rutas de red más cortas o más rápidas, lo que mejora el rendimiento de la red. Funciona entre las capas 2 y 3 de la interconexión de sistemas abiertos (OSI). Se puede utilizar para crear una red unificada en la infraestructura existente, como IPv6, retransmisión de tramas, ATM o ethernet. Se pueden utilizar líneas alquiladas de MPLS o MPLS con VPN para crear redes eficaces y seguras.
#### WAN definida por software
La red de área amplia definida por software (SD-WAN) es la evolución posterior de la tecnología MPLS. Abstrae las funciones del MPLS a una capa de software. Dado que la WAN definida por software funciona a través de conexiones de Internet de banda ancha de uso común, normalmente puede reducir los costos de la red y proporcionar una mayor flexibilidad que una conexión fija.
#### MPLS frente a la WAN definida por software
MPLS puede ralentizar la integración de la nube porque dirige el tráfico a través de las sedes corporativas, que actúan como puntos de estrangulamiento centrales. Por otra parte, la WAN definida por software es compatible con la nube y se integra mucho mejor con la infraestructura moderna en la nube. La WAN definida por software también es rentable. Puede funcionar a través de MPLS de modo que sea posible utilizar el ancho de banda de forma más eficiente en las costosas líneas de alquiler de MPLS.
### ¿En qué consiste la optimización de la WAN?
La optimización de la red de área amplia (WAN) es un conjunto de técnicas que mejoran las métricas de funcionamiento de la WAN, como el rendimiento, la congestión y la latencia. El diseño de la WAN, la tecnología elegida y la disposición del flujo de tráfico afectan al rendimiento de la WAN. A continuación se describen algunas técnicas comunes para la optimización de la WAN.
#### Administración del flujo de tráfico
La administración del flujo de tráfico incluye técnicas que minimizan la cantidad de datos enviados a través de la red. A continuación, se indican algunos ejemplos:

- Almacenamiento en caché de la información que se almacena con frecuencia en los servidores locales
- Identificación y eliminación de las copias de datos redundantes para las aplicaciones de copia de seguridad de datos y recuperación de desastres
- Reducción del volumen o compresión mediante zip de archivos de datos
#### Aceleración de protocolos
Algunos protocolos de la WAN presentan un exceso de intercambio de información, es decir, pueden requerir una gran cantidad de comunicación de datos de ida y vuelta para una sola solicitud. Por ejemplo, tanto el cliente como el servidor pueden enviar datos de acuse de recibo para confirmar que han recibido datos. La aceleración de protocolos agrupa las comunicaciones de los protocolos con exceso de intercambio de información para reducir el número de paquetes de datos en la red.
#### Límites de velocidad y conexión
Los administradores de la red pueden limitar el número de enlaces de acceso a Internet abiertos, el número de usuarios y la cantidad de ancho de banda a la que puede acceder cada usuario a la vez. Por ejemplo, pueden establecer reglas para evitar que los empleados transmitan videos en la WAN de la empresa.
#### Segmentación de la red
La conformación del tráfico controla el flujo de datos para aplicaciones específicas, lo que reparte el ancho de banda de la red de forma óptima entre las aplicaciones. El operador de la red puede optar por priorizar determinadas aplicaciones críticas para mejorar su rendimiento.
## Clasificacion de las redes por su alcance
| Distancia hasta | Ejemplo                                                        | Tipo de Red              |
| --------------- | -------------------------------------------------------------- | ------------------------ |
| 10 m            | Bluetooth, USB, Ethernet corto alcance                         | PAN (Personal)           |
| 100 m           | Wifi, Ethernet en cobre y fibra optica                         | LAN (Edificio)           |
| 2 Km            | Ethernet en fibra optica                                       | LAN (Campus)             |
| 80 Km           | Redes, CATV, ADSL, FTTH, WiMAX, servicios fibra oscura         | MAN (Metropolitan)       |
| 20,000 Km       | Enlaces telefonicos, fibra optica, telefonia celular, satelite | WAN                      |
| > 20,000 Km     | Transmision de datos por sondas espaciales                     | Internet Interplanetaria |
![[Pasted image 20240524191701.png]]

## Escenario LAN-WAN tipico
![[Pasted image 20240524191252.png]]
![[Pasted image 20240524191331.png]]
