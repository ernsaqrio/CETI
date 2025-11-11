
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

