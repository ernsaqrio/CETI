**Definiciones básicas**

- Amenazas: una amenaza es cualquier elemento susceptible de causar daño. Aquí podemos
	distinguir entre amenazas físicas (incendios, terremotos, cortes eléctricos, fallos de hardware,
	etc.) y amenazas lógicas (intrusiones, malware, etc.) que pueden provenir de personas
	individuales, grupos o organizaciones gubernamentales.
	
- Vulnerabilidad: una vulnerabilidad es una debilidad existente en un sistema que puede ser
	utilizada por una persona malintencionada para comprometer su seguridad. Estas pueden
	provenir de fallos en el diseño software o del hardware o humanos. Asociado habitualmente al software.
	
- Vector de ataque: termino que proviene del ámbito bélico. Se refiere a la ruta, camino, medio
	del que hace uso un atacante para vulnerar nuestros sistemas. P. ej., Phishing, vulnerabilidades, malas prácticas de seguridad, etc.
	
- Riesgo: es la posibilidad de que una amenaza explote una vulnerabilidad mediante un vector
	de ataque.
	
- Impacto: consecuencias de que una amenaza explote una vulnerabilidad provocando un
	cambio en el estado del elemento afectado.
	
- Tipos de análisis de seguridad: en el mundo del software cuando ponemos a
	prueba una aplicación mediante testing o sometemos a una autoría de seguridad
	a una organización podemos distinguir tres tipos de pruebas:
	
	- Prueba caja negra: no conocemos el funcionamiento interno del objeto de prueba,
		introducimos una entrada y recibimos una salida como feedback. Evalúa el rendimiento
		y la seguridad del sistema pero no como funciona.
		
	- Prueba caja blanca: poseemos todo el conocimiento interno acerca del objeto de
	 prueba, incluso se nos puede proporcionar credenciales con privilegios para someterlo
		a pruebas. Evalúa el funcionamiento interno del sistema proponiendo medidas
		especificas para su corrección.
		
	- Prueba caja gris: combinación de las dos anteriores, conocemos detalles internos pero
		no tenemos pleno acceso a ellos.

**Principios seguridad de la información**

Para quebrantar esta seguridad se busca romper uno o varios de las dimensiones
que sustentan esta seguridad (CIA Triad):

- Confidencialidad: asegurar el acceso a la información solo a las personas autorizadas. Se deben
	proteger los sistemas que procesan, transmiten o almacenan dicha información, además de
	asegurarnos de limitar dicha información a la mínima imprescindible. No pueden sustraerte
	aquella información que te es desconocida.
	
- Integridad: evitar que la integridad de la información sea comprometida. Evitar
	cambios no autorizados en la naturaleza de la misma. Por ejemplo: modificación
	de datos personales.
	
- Disponibilidad: garantizar el acceso de las personas autorizadas a la
	información cuando este sea requerido. La información debe poder ser
	accedida cuando sea necesario. 
	
- También añadimos los principios de:
	- Autenticidad: arantizar la procedencia y veracidad de la información. Se
		verifica la fuente de la información y la autenticidad de la misma. Una
		suplantación de identidad mediante phishing sería una vulneración de este
		principio.
		
	- Trazabilidad: registro de cambios en la información hasta llegar a la entidad
		autora de dichos cambios. Poder determinar cuando y quien ha realizado
		modificaciones.
		
	- No repudio: El receptor no puede negar que recibió el mensaje porque el emisor tiene pruebas de la recepción. Este servicio proporciona al emisor la prueba de que el destinatario legítimo de un envío, realmente lo recibió, evitando que el receptor lo niegue posteriormente. En este caso la prueba irrefutable la crea el receptor y la recibe el emisor.

Un incidente de seguridad a cualquier suceso que afecte a la confidencialidad, integridad o disponibilidad de los activos de información de la empresa, por ejemplo: acceso o intento de acceso a los sistemas, uso, divulgación, modificación o destrucción no autorizada de información. 
[[IC1]]

**Principio del menor privilegio:** consiste en minimizar el impacto de cualquier fallo,
accidente o vulnerabilidad del sistema, reduciendo los privilegios de los
trabajadores al mínimo necesario para el desempeño de sus tareas autorizadas.

**Defensa en profundidad:** es una terminología común en las prácticas de ciberseguridad actuales. Es una estrategia que emplea una serie de mecanismos, también conocidos como controles, para detener un ataque a su organización.

Cada capa ofrece una protección adicional, de modo que si una capa es violada, la siguiente capa de protección estará en su lugar para evitar una mayor exposición de los datos a partes no autorizadas.

**Tipos de seguridad**
- En función de lo que se quiere proteger:
	- Seguridad física: Protección de la organización frente a accesos no autorizados y ataques físicos a los equipos e instalaciones. Hardware.
	
	- Seguridad lógica: Mecanismos y barreras que protegen la información de un sistema informático. Por ejemplo:
		- Limitar el acceso a través de cifrados o claves.
		- Otorgar privilegios mínimos a los usuarios.
		- Controlar que información entra y sale del sistema de información.
- En función de la forma de protección:
	- Seguridad activa: medidas de protección preventivas. Minimizan el riesgo de un
		ataque o lo evitan.
		- Contraseñas seguras.
		- Cifrado de información.
		- Uso de software de seguridad. Antivirus, IDS (Intrusion detection system ), IPS (Intrusion prevention system), etc.
	- Seguridad pasiva:  medidas de control de daños una vez estos se han producido.
		Tienen el objetivo de minimizar los mismos.
		- Escanear y desinfectar de malware.
		- Restauración de copias de seguridad.
		- Utilización de distintas particiones para el almacenamiento de esas copias de seguridad.

**Deep web y dark web**

- Surface web (4%): Indexada y fácil de buscar (wikipedia, google, bing, yahoo)
- Deep web (90%): No indexada y algo difícil de encontrar (4chan, craiglist, reddit, pastebins, niche blogs & forums, Yahoo answers)
- Dark web (6%): obscurecida, dificil de descubrir (Zeronet, I2P, TOR encrypted sites, Open bazaar y telegram)

**Anonimato en la red**

La dirección ip y dirección Mac de los dispositivos que tenemos conectados a nuestra
red doméstica/privada (incluidas las máquinas virtuales) no están directamente
expuestas a Internet.

Para conectarnos a Internet necesitamos un dispositivo denominado router, que, de
manera genérica, conecta nuestra red doméstica/privada con otras redes de las que se
compone Internet. Todos los dispositivos que tenemos conectados a nuestra red
doméstica/privada tienen una dirección ip privada que solo es accesible por otros
dispositivos conectados a esta misma red. Por lo tanto, para poder conectarse a
internet, tienen que hacerlo a través del router, que tiene una dirección ip pública
concreta que utilizarán todos los sistemas informáticos que tengamos conectados a
nuestra red privada.

Esto es algo sencillo de comprobar entrando en páginas que te muestran tu dirección
ip pública desde diferentes dispositivos conectados a tu red doméstica (por ejemplo
móvil y pc), y podrás observar que la dirección IP pública es la misma para ambos.

El riesgo de seguridad al que estamos expuestos todos, independientemente de
utilizar mecanismos para garantizar el anonimato o no, es a la explotación de un
posible fallo de seguridad en nuestro router de manera que permita ganar acceso a
los sistemas que se encuentren conectados a nuestra red local. Este riesgo no
puede mitigarse por completo debido a que el router tiene que estar expuesto a
Internet para poder habilitar la conexión de los dispositivos que se encuentran en
nuestra red privada.

Cuando utilizas mecanismos de anonimato como una VPN, tienen que descifrar tu
tráfico de red y, por lo tanto, pueden monitorizarlo y registrarlo. Conocen lo que
estás haciendo y también el origen de la conexión. Si utilizas un servicio gratuito de
proxy, VPN... que te encuentres por Internet, es posible que incluso te estén
monitorizando y puedan llegar a robarte información. Si realizas cualquier tipo de
actividad ilegal utilizando estos mecanismos, nada te garantiza que no vayas
a ser identificado, sobre todo si estás utilizando un servicio gratuito.

Algunas de las soluciones y herramientas más populares para garantizar el
anonimato en Internet:
1. La opción más sencilla es utilizar un proxy. Si utilizas un proxy gratuito y
público pueden estar monitorizando tu navegación.
2. Otro de los mecanismos más comunes es utilizar una VPN.
3. Aunque es menos popular, podéis conectaros a Internet a través de la Red Tor.
No siempre garantizan el anonimato en Internet y, en ciertas ocasiones, pueden
llegar exponernos a nuevos riesgos de seguridad, dependiendo de su origen y
confiabilidad.

En la actualidad existen multitud de proyectos que permiten mantener el anonimato
en la red. Una de las mas conocidas es la red TOR.

Para mantener la seguridad dentro de la red TOR, por cada equipo se aplica una capa de cifrado. De esta forma únicamente el ultimo nodo (Nodo de salida) conoce el texto en claro.

Se emplea un sistema de cifrado asimétrico empleando la clave pública (obtenidas de un directorio de nodos) de todos los nodos del recorrido empezando por el último. Previamente se ha calculado la ruta a seguir estableciendo una serie de host intermedios más o menos aleatorios.
Se conoce como Onion Routing.

A esto se debe el nombre de TOR, una alusión a las capas de las cebollas.

- ZeroNet: red de internet descentralizada. No hace uso de servidores, sino que los host pertenecen a una red p2p (peer to peer). Por defecto no es anónima, pero se puede combinar con Tor.
- FreeNet: alternativa a Tor. Como ZeroNet, es una red descentralizada que emplea la conexión punto a punto (p2p) y es anónima. Aún en desarrollo
