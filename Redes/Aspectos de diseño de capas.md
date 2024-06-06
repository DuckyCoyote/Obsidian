## Confiabilidad
La confiabilidad en el diseño de redes asegura que una red funcione adecuadamente a pesar de estar compuesta por componentes poco confiables. Para detectar y corregir errores en la información que viaja a través de la red, se utilizan **códigos de detección** y **corrección de errores**, añadiendo información redundante para proteger y verificar los datos recibidos. Además, la confiabilidad implica encontrar rutas funcionales a través de la red. Cuando hay enlaces o enrutadores caídos, la red debe redirigir automáticamente el tráfico por rutas alternativas, un proceso conocido como **enrutamiento**.

Como hay muchas computadoras en la red, cada capa necesita un mecanismo para identificar los emisores y receptores involucrados en un mensaje especifico. Este mecanismo se conoce como **direccionamiento** o **nombramiento** en las capas altas y bajas, respectivamente.

No todos los canales de comunicación preservan el orden de los mensajes que se
envían en ellos, por lo cual es necesario idear soluciones para enumerar los mensajes. Otro ejemplo es el de las diferencias en el tamaño máximo de un mensaje que las redes pueden transmitir. Esto provoca la creación de mecanismos para desensamblar, transmitir y después volver a ensamblar los mensajes. A este tema en general se le conoce como *interconexión de redes* (internetworking).

Muchos diseños de redes utilizan el **multiplexado estadístico**, que comparte dinámicamente el ancho de banda según las necesidades a corto plazo de los hosts, en lugar de asignar una fracción fija a cada uno. Este enfoque se aplica en diversas capas de la red, incluso en aplicaciones específicas. Un desafío común es evitar que un emisor rápido sature a un receptor lento, problema que se maneja con control de flujo mediante retroalimentación del receptor. La **congestión** ocurre cuando muchas computadoras intentan enviar grandes cantidades de datos simultáneamente, superando la capacidad de la red. Una solución es que cada computadora reduzca su demanda durante la congestión, estrategia aplicable en todas las capas. Además del ancho de banda, la red debe ofrecer servicios como la entrega puntual para aplicaciones en tiempo real, manejando las demandas competitivas mediante mecanismos de calidad de servicio.

## Integridad
El último aspecto de diseño importante es asegurar la red y defenderla contra distintos tipos de amenazas. Una de las amenazas que mencionamos antes es la de espiar las comunicaciones. Los mecanismos que proveen confidencialidad nos defienden contra esta amenaza y se utilizan en múltiples capas. Los mecanismos de autenticación evitan que alguien se haga pasar por otra persona. Se pueden usar para di ferenciar los sitios web bancarios falsos de los verdaderos, o para permitir que la red celular verifique que una llamada realmente provenga de nuestro teléfono para pagar la cuenta. Otros mecanismos para la integridad evitan cambios clandestinos a los mensajes, como cuando se altera el mensaje “cargar $10 a mi cuenta” para convertirlo en “cargar $1000 dólares a mi cuenta”. Todos estos diseños se basan en la criptografía.

Las capas de red ofrecen dos tipos de servicio a las capas superiores: orientado a conexión y sin conexión.

1. **Servicio Orientado a Conexión**:
    
    - Se asemeja al sistema telefónico: se establece una conexión, se usa y luego se libera.
    - Funciona como un tubo donde los bits se envían en orden.
    - Puede implicar una negociación sobre parámetros como tamaño de mensaje y calidad del servicio.
    - Similar a un circuito en redes telefónicas, puede tener recursos asociados como ancho de banda fijo.
    - Ejemplo: transferencia de archivos, donde es crucial que todos los bits lleguen en orden y sin errores.
    - Variaciones:
        - **Secuencias de mensajes**: los mensajes mantienen sus límites originales.
        - **Flujos de bytes**: los datos se envían como un flujo continuo de bytes, sin importar los límites de los mensajes.
2. **Servicio Sin Conexión**:
    
    - Se asemeja al sistema postal: cada mensaje lleva la dirección completa y se enruta de manera independiente.
    - Tipos de conmutación:
        - **Almacenamiento y envío**: el mensaje se recibe completo antes de ser enviado al siguiente nodo.
        - **Conmutación al vuelo**: el mensaje se envía antes de ser recibido completamente.
    - La fiabilidad varía:
        - **No fiable** (sin confirmación de recepción): como enviar un telegrama.
        - **Fiable** (con confirmación de recepción): como enviar una carta certificada.
    - Ejemplo de uso no fiable: envío de correo electrónico basura (spam), donde no es crucial la confirmación de entrega.
    - Ejemplo de uso fiable: mensajería de texto en teléfonos móviles, donde la confirmación de recepción asegura la entrega.

La elección entre estos servicios depende de la aplicación específica y sus necesidades en términos de confiabilidad y eficiencia.
## Modelo Cliente Servidor
Hay otro servicio conocido como **servicio de solicitud-respuesta**. En este servicio, el emisor transmite un solo datagrama que contiene una solicitud, y el receptor envía la respuesta. El servicio de solicitud-respuesta se utiliza mucho para implementar la comunicación en el modelo cliente-servidor; el cliente emite una petición y el servidor le responde. Por ejemplo, el cliente de un teléfono móvil podría enviar una consulta a un servidor de mapas para recuperar los datos del mapa de la ubicación actual.
## Ejemplos de servicios Orientados a Conexion y Servicios sin Conexion
![[Screenshot_20240603_175118.png]]
## Primitivas de Servicios
En el contexto de sistemas de comunicación, un servicio se define formalmente como un conjunto de primitivas, es decir, operaciones básicas, disponibles para que los procesos de usuario accedan a dicho servicio. Estas primitivas son las acciones que el usuario puede solicitar al servicio o la información que puede obtener sobre las acciones realizadas por otra entidad involucrada.

Cuando la pila de protocolos está implementada en el sistema operativo, como suele ser el caso, estas primitivas se llaman generalmente "llamadas al sistema". Estas llamadas provocan un cambio al modo kernel del sistema operativo, lo que permite que el sistema realice las acciones necesarias, como enviar paquetes de datos a través de la red.

El conjunto de primitivas disponibles varía según la naturaleza del servicio que se esté ofreciendo. Por ejemplo, las primitivas para un servicio orientado a conexión serán diferentes de las primitivas para un servicio sin conexión.
![[Screenshot_20240603_180227.png]]
## Diagrama de Peticiones al Servidor desde un Client
- **Servidor escucha**:
    - El servidor ejecuta LISTEN para indicar que está listo para aceptar conexiones entrantes.
    - Esto bloquea al proceso del servidor hasta que llegue una petición de conexión.
- **Cliente se conecta**:
    - El proceso cliente ejecuta CONNECT para establecer una conexión con el servidor.
    - Se especifica la dirección del servidor en la llamada a CONNECT.
    - El sistema operativo envía un paquete al servidor solicitando la conexión.
    - El proceso cliente se suspende hasta recibir una respuesta.
- **Servidor acepta la conexión**:
    - Cuando el paquete llega al servidor, el sistema operativo verifica si hay alguien escuchando.
    - Si el servidor está escuchando, se desbloquea y puede establecer la conexión con ACCEPT.
    - ACCEPT envía una respuesta al proceso cliente para aceptar la conexión.
    - El cliente se libera y en este punto, el cliente y el servidor están conectados.
- **Analogía con la vida real**:
    - La analogía es como un cliente que llama al gerente de servicio al cliente de una empresa.
    - El gerente de servicio espera a que el teléfono suene, similar a cómo el servidor espera una conexión.
    - Cuando el cliente llama, se establece la conexión, como cuando el gerente responde al teléfono.
- **Servidor se prepara para recibir**:
    - Después de establecer la conexión, el servidor ejecuta RECEIVE para prepararse para la primera solicitud.
    - Esto generalmente se hace justo después de la primitiva LISTEN, antes de que la confirmación de recepción pueda regresar al cliente.
    - La llamada a RECEIVE bloquea al servidor hasta que llegue una solicitud.

![[Screenshot_20240603_181008.png]]
- **Cliente envía petición**:
    
    - El cliente ejecuta SEND para transmitir su petición después de haber ejecutado RECEIVE para obtener la respuesta.
    - La llegada del paquete solicitado a la máquina servidor desbloquea al servidor para manejar la petición.
- **Servidor envía respuesta**:
    
    - Después de realizar su trabajo, el servidor usa SEND para devolver la respuesta al cliente.
    - Al llegar este paquete, se desbloquea al cliente, que ahora puede inspeccionar la respuesta.
    - Si el cliente tiene peticiones adicionales, puede hacerlas ahora.
- **Cliente termina la conexión**:
    
    - Cuando el cliente ha completado sus acciones, ejecuta DISCONNECT para terminar la conexión.
    - La primitiva DISCONNECT puede ser una llamada de bloqueo, suspendiendo al cliente y enviando un paquete al servidor para indicar el cierre de la conexión.
- **Servidor cierra la conexión**:
    
    - Cuando el servidor recibe el paquete de cierre de conexión, emite su propia primitiva DISCONNECT, envía una confirmación de recepción al cliente y libera la conexión.
    - Al llegar el paquete del servidor a la máquina cliente, se libera el proceso cliente y se interrumpe la conexión.
## Relación entre servicios y protocolos
Los servicios y los protocolos son conceptos distintos y es crucial resaltar esta distinción. Un servicio se refiere a un conjunto de primitivas (operaciones) que una capa proporciona a la capa superior. Define qué operaciones puede realizar la capa en beneficio de sus usuarios, pero no especifica cómo se implementan estas operaciones. La relación entre un servicio y una capa se establece a través de una interfaz, donde la capa inferior actúa como proveedor del servicio y la capa superior como usuario.

Por otro lado, un protocolo consiste en un conjunto de reglas que gobiernan el formato y el significado de los paquetes o mensajes intercambiados por entidades iguales en una capa. Las entidades utilizan protocolos para implementar las definiciones de servicios, pudiendo modificar los protocolos según lo deseen, siempre y cuando no afecten el servicio visible para los usuarios. Por lo tanto, el servicio y el protocolo son independientes entre sí, un concepto clave que todo diseñador de redes debe comprender.

Para enfatizar este punto importante, los servicios están relacionados con las interfaces entre capas, mientras que los protocolos se relacionan con los paquetes enviados entre entidades pares en distintas máquinas. Es crucial no confundir estos dos conceptos.
![[Screenshot_20240603_182045.png]]
