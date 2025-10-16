**Necesidad**

Es necesario hacer bastionado para:
- mantener las famosas 3 dimensiones de la seguridad de la información: confidencialidad, integridad y disponibilidad; y en segundo, porque existen, aunque no a nivel global, numerosos requerimientos legales que precisan de la protección de las infraestructuras tecnológicas que almacenan la información, como por ejemplo los datos de carácter personal.
- En segundo lugar, por todas las amenazas a las que están sujetos tanto los servicios como las tecnologías.

**Amenazas:**
- Malware
	- Ransomware: Malware capaz de secuestrar nuestro dispositivo mediante el cifrado de los archivos principalmente.
	- Spyware: son aplicaciones que se dedican a recopilar información del sistema en el que se encuentran instaladas para luego enviarla a través de Internet.
	- Troyanos: es una pieza de software dañino disfrazado de software legítimo. Este malware no es capaz de replicarse por sí mismos y pueden ser adjuntados con cualquier tipo de software.
	- Gusanos: similares a los virus, pero no dependen de archivos portadores para poder contaminar otros sistemas. Pueden modificar el sistema operativo con el fin de auto ejecutarse como parte del proceso de inicialización del sistema.
	- Bots: son programas que a través de órdenes enviadas desde otra computadora controlan el equipo personal de la víctima, es decir convirtiéndola en un "Zombi“, formando una red para ataques DDoS, robo de credenciales, envío de SPAM, etc.
	- Keylogger: que una vez infectado el equipo, roba información registrando las pulsaciones del teclado o clics de ratón, para robar todo tipo de información.
	- Rootkit: programas que son insertados en una computadora después de que algún atacante ha ganado el control de un sistema. Los rootkit generalmente incluyen funciones para ocultar los rastros del ataque, como es borrar los log de entradas o encubrir los procesos del atacante.
	- Fileless malware: en este caso el atacante se aprovecha de funcionalidad del sistema operativo para llevar a cabo la infección, con comandos de powershell o msdos.
	- Software conejo: es un tipo de malware que  replica procesos del sistema de forma descontrolada, consumiendo recursos (procesador, memoria, espacio en disco, etc.) hasta saturarlo. 
	- Bombas lógicas: es una parte de un código insertado intencionalmente en un programa informático que permanece oculto hasta cumplirse una o más condiciones preprogramadas, en ese momento se ejecuta una acción maliciosa. (EJ:  un programador puede ocultar una pieza de código que comience a borrar archivos cuando sea despedido de la compañía.
- Vulnerabilidades: podemos definir este concepto como “un fallo en el código o en la configuración de un software o en el diseño e implementación de un sistema hardware o físico, que permite a un atacante comprometer la seguridad del activo y hacer que muestre y realice funciones anti producentes y para el que no está autorizado”.
	- CVE: lista de información registrada sobre vulnerabilidades de seguridad conocidas, en la que cada referencia tiene un número de identificación CVE-ID, descripción de la vulnerabilidad, que versiones del software están afectadas, posible solución al fallo (si existe) o como configurar para mitigar la vulnerabilidad y referencias a publicaciones o entradas de foros o blog donde se ha hecho pública la vulnerabilidad o se demuestra su explotación. 
	- CVSS: es un estándar de la industria, libre y abierto, para evaluar la gravedad de las vulnerabilidades en los sistemas informáticos. CVSS intenta asignar puntuaciones de gravedad a las vulnerabilidades, permitiendo a los respondedores priorizar respuestas y recursos según la amenaza. Las puntuaciones se calculan basándose en una fórmula que depende de varios parámetros que aproximan la facilidad y el impacto de un exploit. Las puntuaciones varían de 0 a 10, siendo 10 la más grave. Aunque muchos solo utilizan la puntuación base de CVSS para determinar la gravedad, también existen puntuaciones temporales y ambientales, que consideran la disponibilidad de mitigaciones y cuán extendidos están los sistemas vulnerables dentro de una organización, respectivamente.
- Fraude: pueden llegar de varias maneras y pueden poner en compromiso sistemas y arquitecturas ya que dentro de este tipo de incidente, también se contemplan las suplantaciones de correo electrónico o web también conocidas como phishing.
- Insiders: se trata de una amenaza que aunque no reciente, en la actualidad se ha puesto gran interés en mitigar. Básicamente se trata de un ataque generalmente interno, llevado a cabo por un empleado o alguien dentro o con acceso a los sistemas de la organización que, con un propósito trata de realizar alguna acción que podría perjudicarla como el robo de información, la des habilitación de servicios, etc. 
- Ataques externos: que podrían ser intencionados o no. Algunos que entrarían dentro de esta tipología podrían ser los escaneos indiscriminados con herramientas de enumeración como NMAP ; la identificación de vulnerabilidades con herramientas como Nessus o Acunetix, etc.

**Q1: ¿Cuál de lo siguiente no es un motivo para implementar bastionado o configuración segura?**

- Por normativa legal
- La seguridad es un requisito indispensable del sistema
- RGPD
- ==Los técnicos lo consideran necesario==

**Bastionado**

Este concepto se refiere a todo lo que tiene que ver con la protección de los activos que
soportan los sistemas de información, es decir, dotar de las defensas necesarias a los
sistemas y redes para evitar que las amenazas que les afectan, se puedan materializar.
También es posible que encontremos este término en referencia a los propios usuarios. 

En este caso se trataría de dotar de las capacidades a los mismos para que sean capaces de
identificar amenazas, reportar incidentes, etc.

Es en este punto donde hemos de diferenciar los conceptos de amenaza y vulnerabilidad. 
El primero hace referencia a algo que podría representar un daño potencial sobre un activo,
mientras que el segundo, es un estado o condición que tiene el activo y que podría hacer que
el daño se materializara. 

Trasladándolo a un ejemplo, en un sistema Windows con el servicio
de escritorio remoto habilitado, tendríamos la potencial amenaza de que un atacante que
conozca la IP, podría llevar a cabo intentos de conexión para intentar acceder. 

Una vulnerabilidad en este sentido, sería que el servicio utilizara credenciales por defecto o
credenciales poco robustas donde un ataque de fuerza bruta podría tener éxito.

Algunas de las características que contempla el bastionado pasarían por:
- Eliminación de cuentas innecesarias.
- Eliminación de contraseñas por defecto.
- Instalación de tecnologías de seguridad como firewalls, WAFs (Web Application Firewalls, etc.)
- Implementar política de actualizaciones para mantener los sistemas seguros.
- Des habilitación de puertos y servicios que no se usen y elevar la seguridad al máximo de los que sí se utilizan.
- Desarrollar planes de contingencia que incluyan políticas de copia de seguridad y recuperación de sistemas.
- Elevar la seguridad en redes inalámbricas y usarlas únicamente si es necesario.

Un nuevo paradigma que se está extendiendo que se podría considerar la evolución del
“mínimo privilegio”, es lo que se conoce como “Zero Trust Security”. A grandes rasgos, este
nuevo modelo representa un nuevo modo de proteger la información. En algunas referencias
encontramos que esto pasaría por disponer de una red interna confiable y una red externa no
confiable. No se puede confiar incluso en los que confiamos.

Algunas de las cuestiones que aborda es:
- Doble factor de autenticación (2FA ) o multi factor de autenticación (MFA): minimizando el posible compromiso de la barrera clásica formada por usuario/contraseña.
- Control del flujo de red entre los activos.
- Acceso discrección a aplicaciones frente a la red completa.
- Acceso por parte de los usuarios con mínimos privilegios.
- Mejora de las estrategias existentes en cibersegurida con mecanismos avanzados de detección de amenazas incluidas vulnerabilidades “zero day”.
- Implementación de VPNs transparentes para el usuario

**¿Por donde empiezo?**

Aunque suene a respuesta típica, antes de comenzar a implementar acciones que permitan
reforzar la seguridad de una organización, es necesario llevar a cabo un análisis de riesgos.

Esta tarea nos dará la información necesaria para identificar dónde tenemos que poner
atención para conseguir elevar el nivel de ciberseguridad de aquellos procesos más
importantes para la organización o empresa. 

Un principio que no debemos olvidar en este punto, es que la ciberseguridad se ha de alinear con el negocio, nunca se debe priorizar las medidas de seguridad frente a la operativa o la actividad de la empresa. 

La ciberseguridad ha de acompañar a la estrategia de la organización. Teniendo esto claro, existen numerosas metodologías, normas y estándares para llevar a cabo esta tarea, pero una cosa está clara, “si no sé dónde me encuentro, difícilmente voy a poder mejorar”.

*herramienta de autodiagnóstico*

De manera básica y para aproximarnos a esta actividad, podríamos utilizar la
herramienta de autodiagnóstico de INCIBE. 

Se trata de una herramienta muy sencilla que considera tres elementos: personas, procesos y tecnologías sobre cinco aspectos que la mayor parte de organizaciones tiene como una página
web, el trabajo en movilidad, servidores propios, correo electrónico y posibilidad de teletrabajar.

Mediante las respuestas a las preguntas del cuestionario interactivo, iremos conociendo el apetito de riesgo que tiene la organización en relación a los tres elementos mencionados anteriormente. Al finalizar el análisis, obtendremos ayuda para saber cómo reducir el nivel de riesgo en relación a las personas, los procesos o las tecnologías.

**Q2: Para aplicar seguridad a un sistema por dónde empiezo**

- Configurando los firewall
- ==Análisis de riesgos==
- Tener el presupuesto de los equipos que protegen el sistema.