# Recopilado de información

Podemos distinguir 3 tipos de formas de recopilación de información
- Pasiva
- Semiactiva
- Activa

# Reconocimiento semiactivo

Recolección de información sobre un objetivo determinado utilizando métodos que se tomen como el tráfico de red y comportamiento normal que suele recibir.
Dentro del alcance se encuentran actividades como:
- Consulta a servidores DNS.
- Acceso a recursos internos de las aplicaciones web.
- Análisis a metadatos de documentos.
Actuamos sin realizar actividades que generen un tráfico anómalo.

# Herramientas

**FOCA**

Herramienta enfocada a encontrar metadatos y información oculta en documentos en aplicaciones web.

Analiza gran variedad de documentos como .docx, .pdf, etc.

Hace uso de 3 buscadores: Google, Bing y DuckDuckGo.

Estos metadatos nos permite averiguar detalles acerca de la empresa: sofware empleado, autor, correos electrónicos, nombres de equipos y versión del propio software. [Repositorio]().

**Exiftool**

Software libre y de código abierto para leer, escribir y manipular metadatos de archivos.
Desarrollado por Phil Harvey. 

# Esteganografía

Ciencia o el procedimiento de incluir mensajes o información secretos dentro de otros datos, a los que se les llama portadores o carriers (texto, imágenes, videos, etc.).

Su objetivo principal es la comunicación confidencial e incógnita entre un emisor y receptor (los cuales pueden cambiar de roles). El acto de transmisión del mensaje debe pasar inadvertido por quienes puedan acceder al medio por el que se transmite, basándose fuertemente en el concepto de seguridad por oscuridad: si nadie sabe que hay un mensaje escondido, nadie lo va a intentar obtener.

**Herramientas**

Dos de las herramientas más conocidas son:
- [Steghide](): diseñada para ocultar datos en otros archivos.  [Repositorio](). [Tutorial]().
- [Stegcracker](): herramienta de fuerza bruta para el descubrimiento de datos ocultos en archivos. [Repositorio]().
Existen otras herramientas en desarrollo como Stegseek y Stegbrute que muestran mayor potencial a la hora de aplicar fuerza bruta.

# Sniffers

Software diseñado para la monitorización y captura de paquetes de red a través de las interfaces de un sistema.
- [TCPDUMP](): rastreador de paquetes de línea de comandos que puede capturar e interpretar directamente tramas de datos desde un archivo o una interfaz de red. Fue creado para su uso en cualquier sistema operativo similar a Unix y tenía un gemelo de Windows llamado WinDump.
- [Wireshark](): analizador de paquetes de red más famoso del mundo. Empleado en todos los ámbitos que requieren el análisis de tráfico de red.
- [NetworkMiner](): herramienta similar a Wireshark orientada al análisis forense automatizado como la extracción de archivos.