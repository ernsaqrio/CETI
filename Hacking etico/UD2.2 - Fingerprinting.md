
# Recursos

- [Metasploitable3](https://github.com/rapid7/metasploitable3)
- [Vagrant](https://developer.hashicorp.com/vagrant/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

# Introducción

Se persiguen los siguientes objetivos:

- Identificar los hosts activos: filtrar esos rangos de IP que se tienen y quedarse solo con los de las máquinas activas.
    
- Determinar los puertos abiertos en esos hosts, es decir, qué servicios están ejecutándose, qué software en concreto y qué versión.
    
- Una vez identificados los servicios expuestos, hacer un reconocimiento más profundo. Por ejemplo, en el caso de SMB, tratar de obtener cuentas, grupos de usuarios y posibles _shares;_ en el caso de HTTP, realizar _fuzzing_ para obte­ner rutas y ficheros interesantes.
    
- Asimismo, también pueden hacerse pruebas para obtener detalles del siste­ma operativo de cada _host.

# Técnicas de análisis de hosts y puertos


Un puerto en un host activo puede estar, desde el punto de vista de otro _host,_ en uno de los siguientes estados:

- Abierto: puerto disponible y con un servicio detrás a la espera de conexiones.
    
- Cerrado: puerto accesible, pero sin aplicación o servicio detrás que responda.
    
- Filtrado: puerto no alcanzable porque hay un cortafuegos impidiendo su ac­ceso. Tras el cortafuegos, el puerto podría estar abierto o cerrado.
    

Algunas herramientas, como `nmap`, ofrecen otros estados adicionales bajo ciertas circunstancias, y que se deben principalmente a la imposibilidad de dic­taminar de manera fehaciente el estado del puerto. Un ejemplo de esto se tiene con ciertos servicios **UDP** que, aunque estén abiertos, no responden a las prue­bas enviadas.

Descubrir el estado de un puerto es fundamental, no solo para catalogar los puertos abiertos de un objetivo, sino también porque es comúnmente usado para identificar si un _host_ está activo o no. En los siguientes subapartados se describirán de modo general las principales técnicas usadas. Es recomendable tener un conocimiento básico del funcionamiento de las diferentes capas de red y de la pila de protocolos `TCP/IP`.

# 1. Análisis TCP de conexión completo

El análisis TCP de conexión completa es conocido también corno _TCP Full-connect o TCP Connect._ Se usa para conocer el estado de un puerto TCP. Consiste en realizar el proceso de establecimiento de conexión en TCP: el algoritmo _**Three-way-handshake**__._ Ante esto, el puerto puede responder de varias mane­ras:

![](https://chemaduran.gitbook.io/hacking-etico/~gitbook/image?url=https%3A%2F%2F1432776198-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FyedUXOYEcSd0dvsQz3ZR%252Fuploads%252FYejjsGADIJOhUAn28xZ8%252Fimage.png%3Falt%3Dmedia%26token%3Dec5bacc4-42d1-4635-bbb8-233d9415c03c&width=768&dpr=4&quality=100&sign=5b93d68c&sv=2)

Si se completa la conexión, el puerto está abierto. Si ante la solicitud de cone­xión devuelve un segmento con el _flag_ `RST` _(reset)_ activo, estará cerrado. Si hay ausencia de respuesta o se devuelve un error ICMP indicando que el puerto no es alcanzable, se considerará que está filtrado.

Un aspecto importante para tener en cuenta, _y_ que será la base del uso de esta técnica en el descubrimiento de _hosts,_ es que tanto si el puerto está abierto como cerrado, se puede asegurar que el _host_ está activo, ya que está respon­diendo explícitamente. En cambio, si no se recibe respuesta, no se puede ase­gurar esto.

# 2. Análisis TCP Half-connect

También conocido como análisis **SYN** o **TCP SYN**. Consiste en realizar un inicio de sesión o _**Three-Way-Handshake**_ parcial y, ante el envio del paquete con los _flags_ `SYN+ACK`, se responde con un paquete `RST` para abortar el inicio de se­sión. Las tres posibles respuestas por parte del objetivo se muestran abajo. Según esta, se clasifica el puerto como:

- **Abierto**: si se recibe un segmento con los _flags_ `SYN+ACK`. Inmediatamente después de esto, el cliente abortará el inicio de conexión con un segmento `RST`.
    
- **Cerrado**: si el objetivo responde con un segmento con el _flag_ `RST` activo.
    
- **Filtrado**: si no se recibe respuesta, o bien, se recibe un error `ICMP`. Solo en caso de un error `ICMP` de tipo _host unreachable_ se podría afirmar que el ob­jetivo está activo.

![](https://chemaduran.gitbook.io/hacking-etico/~gitbook/image?url=https%3A%2F%2F1432776198-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FyedUXOYEcSd0dvsQz3ZR%252Fuploads%252FIWfC5VwQpjAnxkw8hkOg%252Fimage.png%3Falt%3Dmedia%26token%3D1654701b-a4f6-4f97-bcf5-e6ed5c7c14ae&width=768&dpr=4&quality=100&sign=8a7fccc0&sv=2)

No terminar el proceso de inicio de conexión aporta dos ventajas respecto al análisis de conexión completa:

- **Eficiencia**: si no se completa el proceso, el servidor elimina rápidamente la conexión sin dejar registro en los _logs_ de eventos (las completadas puede que si, y además se les reservan recursos durante un tiempo determinado hasta producir un _timeout)._
    
- **Sigilo**: aumenta ligeramente la posibilidad de pasar desapercibido ante sis­temas `IDS/IPS` (aunque un detector de intrusos correctamente configurado lo va a detectar).
    

Este tipo de análisis suele requerir permisos de _**root**_ _o_ administrador, ya que re­quiere de la capacidad de forjar segmentos a medida.

# 3. Análisis TCP ACK

Consiste en enviar un segmento al objetivo con el _flag_ `ACK` activado y estudiar su reacción. Se usa principalmente para ver si un _post_ está activo y para com­probar si un determinado puerto está filtrado por un cortafuegos. En estos ca­sos, es una buena alternativa al `TCP SYN`, ya que penetra con más probabilidad cortafuegos e `IDS`, debido a los siguientes motivos:

- Normalmente, cortafuegos e `IDS` están configurados para descartar inicios de sesión entrantes no solicitados (segmentos entrantes con el flag `SYN` activo).
    
- El ACK suele llamar menos la atención que un _flag_ `SYN` y, por supuesto, que un _ping_ `ICMP`.
    

La imagen de abajo representa las dos posibles respuestas del objetivo. Según estas el _host_ estará:

- Activo, si se recibe de respuesta un segmento con el _flag_ `RST` activo.
    
- Inactivo, si no se recibe respuesta.
    

![](https://chemaduran.gitbook.io/hacking-etico/~gitbook/image?url=https%3A%2F%2F1432776198-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FyedUXOYEcSd0dvsQz3ZR%252Fuploads%252FGCOKlh46BIp0bHMq8evM%252Fimage.png%3Falt%3Dmedia%26token%3D075ebd75-12af-4250-8479-fd8fe31c5fbb&width=768&dpr=4&quality=100&sign=b0ca18f0&sv=2)

# 4. Análisis UDP

Las técnicas anteriores solo sirven para detectar el estado de puertos TCP, y no valen, por tanto, para determinar si un puerto UDP está abierto. Además, res­pecto al descubrimiento de equipos puede ser una buena alternativa a los aná­lisis basados en TCP ya que, en configuraciones deficientes de cortafuegos e IDS, se suele focalizar demasiado en TCP y descuidar UDP.

Es preciso recordar que UDP es un protocolo no orientado a conexión, por tanto no hay Three-Way-Handshake. De ahí que los métodos de detección sean me­nos precisos. En este caso, se envían datagramas UDP a un puerto determinado y, según la respuesta, se procede de la siguiente manera

- Si la respuesta es un mensaje _**ICMP Port Unreachable**__,_ el puerto se declara como cerrado y, además, se tiene la seguridad de que el _host_ está activo.
    
- Si es un error de otro tipo (por ejemplo, _**HostNetwork Unreachable**__,_ o TTL agotado), la respuesta es interpretable. En el caso de `nmap`, respecto al des­cubrimiento de _hosts_ se considerará que el _host_ no está activo (no hay host tras esa IP).
    
- Si no devuelve nada, en el caso de `nmap`, se marca como abierto | filtrado _(open | filtered)._ No es posible diferenciar si hay un cortafuegos rechazando los paquetes para que el servicio UDP no devuelva respuesta.

# 5. Otros análisis especiales

Manipulando los bits de control de un segmento TCP se pueden forjar segmentos con distintos propósitos. Existen algunas configuraciones típicas como:

- **Escáner FIN**: se envía al objetivo un segmento con el bit FIN activado solamente
    
- **Escáner XMAS**: consiste en un segmento con los flags FIN, URG y PUSH activos.
    
- **Escáner NULL**: se trata de un segmento con todos los bits de control a cero
    

Todas estas técnicas, usadas normalmente para el análisis de puertos, pretenden ser una alternativa al intento de creación de una sesión TCP, es decir, al uso del flag SYN, debido a que suele estar fuertemente controlado por cortafuegos e IDS. También puede ser buena idea recurrir a estos escaneos en caso de que se sospeche de que los resultados arrojados por las técnicas convencionales no son correctos.

Los análisis **FIN, XMAS** y **NULL** suelen dar buenos resultados contra sistemas Linux y BSD, pero no tanto con Windows y Cisco. La razón es que estos últimos no son tan estrictos en la implementación del protocolo TCP (RFC 793), por lo que la respuesta a segmentos forjados puede no ser la esperada.

En general, para los tres métodos (aunque su fundamento es distinto) la interpretación de las respuestas es la misma:

- Si se recibe un segmento con el flag **RST: puerto cerrado** (pero **host activo**)
    
- Si se recibe un **ICMP unreachable** (tipo 3, códigos 1,2,3,9,10 o 13): puerto **filtrado**
    
- Si no se recibe respuesta, aplicaciones como **nmap** consideran el puerto como **open | filtered** debido a la imposibilidad de determinar si el puerto está en un estado u otro.

