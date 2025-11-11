# Definiciones básicas

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

# Principios seguridad de la información

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

# Tipos de seguridad

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

# Deep web y dark web

- Surface web (4%): Indexada y fácil de buscar (wikipedia, google, bing, yahoo)
- Deep web (90%): No indexada y algo difícil de encontrar (4chan, craiglist, reddit, pastebins, niche blogs & forums, Yahoo answers)
- Dark web (6%): obscurecida, dificil de descubrir (Zeronet, I2P, TOR encrypted sites, Open bazaar y telegram)

# Anonimato en la red

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

# Vulnerabilidades

Para el nombrado de vulnerabilidades se emplea el estándar de nomenclatura de
vulnerabilidades CVE (https://cve.mitre.org/) (Common Vulnerabilities and
Exposures), con el fin de facilitar el intercambio de información entre diferentes
bases de datos y herramientas.

El CVE-ID ofrece una nomenclatura estándar para identificar las vulnerabilidades
de forma inequívoca:
- El formato para CVE-ID es: CVE-YYYY-NNNN (YYYY indica el año y NNNN el
número de vulnerabilidad). Desde enero de 2014 este identificador puede
contener, si es necesario, más de cuatro dígitos.
-  El formato para vulnerabilidades candidatas es: CAN-YYYY-NNNN (YYYY indica
el año y NNNN el número de vulnerabilidad).

MITRE dispone de otra iniciativa llamada Common Platform Enumeration (CPE). En
resumen, permite identificar con un nombre único y estándar los sistemas, plataformas y
software de una manera muy detallada.

Se utiliza el CPE para hacer referencia a tecnologías, herramientas, sistemas o plataformas
específicas con la mayor exactitud posible. 

Nomenclatura: cpe:/ {part} : {vendor} : {product} : {version} : {update} : {edition} : {language}

Por ejemplo: cpe:2.3:a:kemptechnologies:web_application_firewall:7.2.54.1:*:*:*:*:*:*:*

**Según severidad**

Existen diferentes formas de clasificación de vulnerabilidades algunas organizaciones utilizan el CVSS (Common Vulnerability Scoring
System) que califican del 0 al 10 su riesgo.
- 0 – Ninguna
- 0.1 a 3.9 – Baja
- 4.0 a 6.9 – Media
- 7.0 a 8.9 – Alta
- 9.0 a 10.0 – Crítica

Una lista de vulnerabilidades y exposiciones más comunes (CVE – Common Vulnerabitilies and Exposures) se encuentra en el National Vulnerability Database (NVD), el cual es un repositorio del gobierno norteamericano. Otra base de datos de vulnerabilidades es cveDetails.com.

**Según tiempo**

Vulnerabilidades Zero-Day: vulnerabilidad que acaba de ser descubierta y que aún no tiene un
parche que la solucione. La principal amenaza reside en que, hasta que se lanza dicho parche
correctivo y los usuarios lo instalan en sus equipos, los atacantes tienen vía libre para explotar la
vulnerabilidad y sacar provecho del fallo de seguridad. A este tipo de ataques, se les denomina
ataques de día cero o Zero day attack.

Vulnerabilidades N-day: vulnerabilidades públicas y reconocidas por la organización que han sido (o no) debidamente parcheadas, siendo "n" el número de días desde que ha hecho público y asignado un CVE. Este tipo de vulnerabilidades debemos tomarlas en consideración por el tiempo que tardan algunas organizaciones en implementar los parches de seguridad ya publicados por el desarrollador.

Vulnerabilidades antiguas: vulnerabilidades conocidas desde hace mucho tiempo que han sido
parcheadas en nuevas versiones o no lo han sido en absoluto por diversos motivos, por ejemplo: el
abandono de Windows XP. Suelen tener exploits públicos y son usadas en un entorno de aprendizaje

# Tipos de amenazas

Poco estructuradas: personas o grupos pequeños que actúan por cuenta propia motivados
por diversas causas: curiosidad, aprendizaje, beneficios, hacktivismo, etc. Los casos más
conocidos han sido personas jóvenes que debido a su capacidad han recibido un puesto de
trabajo en la empresa atacada (tras cumplir la debida condena).

Estructuradas: grupos organizados que disponen de los medios para efectuar ataques
planificados. Suelen dedicar bastante tiempo al estudio del objetivo para encontrar
vulnerabilidades. Aquí podemos encontrar grupos como Anonymus, aunque la mayoría
permanecen en el anonimato.

Muy estructuradas: organizaciones grandes y profesionales con una gran cantidad de
recursos a su disposición. En esta categoría entran numerosas empresas de ciberseguridad
así como organizaciones gubernamentales. La más conocida es la NSA.

**¿Que es un ataque?**: Toda aquella acción que atenta contra los pilares de la seguridad:
Confidencialidad, Integridad, Disponibilidad (CIA).

# Tipos de ataques
- Pasivo o activo:
	- Activo:
		- Modifica el sistema
		- Altera la integridad o disponibilidad
		- Ejemplos: Ransomware, borrado de un base de datos.
	- Pasivo: 
		- No modifica los sistemas
		- Intercepta información
		- Afecta a la confidencialidad
		- Ejemplo: escucha de paquetes en la red o interceptación de comunicaciones
- Vectores de ataque:
	- Phishing: El phishing es una técnica que consiste en el envío de un correo o mensaje por parte de un ciberdelincuente a un usuario realizando una suplantación de identidad (red social, banco, institución pública, etc.) con el objetivo de robarle información privada, realizarle un cargo económico o infectar el dispositivo. Para ello, adjuntan archivos infectados o enlaces a páginas fraudulentas en el mensaje.
	- Malware: tiene como objetivo la infección del sistema o sistemas objetivos. Es un tipo de programa malicioso que se camufla en el ordenador y puede dañar los sistemas afectados. Pueden ser virus, troyanos, gusanos, programas ransomware y otros.
	- Ataques de fuerza bruta: intentos de adivinar algún tipo de información (típicamente una contraseña) mediante la permutación de caracteres hasta hallar la correcta. Suele combinarse con el uso de diccionarios.
	- Web: utiliza como medio la web realizando distintos ataques como una inyección SQL o XSS (Cross Site Scripting).
- Atacante:
	- Estados (Ciber espionaje)
	- Cibercriminales
	- Grupos hacktivistas
	- Ciber terroristas
	- Otros actores:
		- Organizaciones privadas
		- Empleados internos
		- Investigadores
		- Script kiddies

# Hacking ético

El hacking ético, también conocido como «pentesting» o prueba de penetración, es una técnica utilizada por los expertos en seguridad informática para detectar y corregir vulnerabilidades en los sistemas de información.

El objetivo principal de los hackers éticos es asegurar que los sistemas y redes de una organización sean seguros y protegidos contra posibles ataques malintencionados.

**comparativa de hacker ético y hacker**

Mientras que el término hacker tiene unas connotaciones de persona que hace uso del hacking para obtener algún tipo de beneficio personal realizando actividades ilegales, cuando hablamos de hacker ético nos referimos a:
- Profesional de la ciberseguridad que se encarga de identificar y reportar vulnerabilidades en sistemas.
- Experto que se especializan en las pruebas de penetración de sistemas informáticos y de software con el fin de evaluar, fortalecer y mejorar la seguridad.


**tipos de hackers**
- White hat: los sombreros blancos utilizan sus capacidades y recursos para descubrir vulnerabilidades y mantener a salvo a la organización. Reciben el permiso de la organización para esta búsqueda. **Actividad legal**
- Black hat: delincuentes que buscan identificar y explotar vulnerabilidades en sistemas motivados por el simple beneficio económico, reputación, venganza o diversión. **Actividades ilegales.**
- Grey hat: este tipo de hacker es una combinación de los dos anteriores. Realizan el mismo análisis de vulnerabilidades de la forma que lo haría un sombrero blanco, pero a diferencia de este no cuenta con el permiso expreso de la organización. Mientras que un sombrero blanco encuentran, reportan vulnerabilidades exclusivamente a la organización y un sombrero negro las explota para su propio beneficio, un sombrero gris encuentra y podría intentar reportárselo a la organización. **Actividades ilegales por no contar con el permiso expreso**

# Bug bounties

El Bug Bounty se puede definir como una modalidad de seguridad ofensiva en el que una organización ofrece recompensa a aquellos hackers que encuentren diferentes vulnerabilidades en su infraestructura.

Esquema:
- Una organización publica un programa en la que invita a los hackers a encontrar vulnerabilidades a cambio de recompensa. Cada programa tiene sus políticas y condiciones, en las que se indicará lo que se puede hacer y lo que no.
- Los hackers tendrán que emplear su conocimiento y habilidades para descubrir vulnerabilidades. Hay diferentes metodologías, cada hacker emplea la que mejor se le adapte.
- Cuando el hacker encuentra una vulnerabilidad, se lo debe comunicar a la empresa a través de un reporte en el que explicará en que consiste la vulnerabilidad, su impacto y pasos para reproducirla
- Los triagers (Personas encargadas en verificar y categorizar las vulnerabilidades) reproducirán la vulnerabilidad reportada y verificarán si cumple con las condiciones descritas en el programa, en ese caso, el hacker recibirá una recompensa. Hay que tener en cuenta que solo será el primer hacker en reportar la vulnerabilidad el que se lleve la recompensa.

Entre las plataformas más populares donde las empresas y los hackers pueden
encontrar programas de recompensa están:
- https://www.yeswehack.com/
- https://www.hackerone.com/
- https://www.bugcrowd.com/
- http://antihack.me/

# Tipos de análisis de seguridad

**Auditorias de gestión**

Este tipo de auditorias se encarga principalmente de auditar un determinado activo con el fin de verificar normativas a cumplir en la organización.

Algunos ejemplos serian:
- Cumplimiento de políticas de seguridad
- Cumplimiento de la norma ISO 27001: Certificación de los Sistemas de Gestión de Seguridad de la Información (SGSI). Garantiza confidencialidad, integridad y disponibilidad. Ejemplo checklist.
 - Cumplimiento de las medidas de seguridad física
 
Tienen un carácter mas teórico y donde la auditoria suele estar basada en una batería de pruebas
teóricas que deben ser cumplidas.

**Auditorias técnicas**

Este tipo de auditorias tienen un carácter más practico donde se pasa de simplemente identificar que algo existe o no para pasar a verificarlo.
Los principales tipos de auditorias técnicas son los siguientes:
- Auditoria de vulnerabilidades (Búsqueda de vulnerabilidades).
- Test de Intrusión (Proceso de intrusión, simulación de ataque digital).
- Red Team (Simulación de ataque real y dirigido).

**Ámbitos**

En base al activo y origen de las pruebas podemos tener los siguientes ámbitos tanto de auditoria como de intrusión:
▪ Externo: Acciones realizadas sobre la infraestructura desde Internet.
▪ Interno: Acciones realizadas desde la red interna.
▪ Aplicaciones Web: Acciones sobre determinados activos web.
▪ Sistemas: Acciones sobre determinados sistemas.
▪ Wireless: Acciones sobre tecnologías inalámbricas como Wi-Fi.
▪ Otros.

# Alcance del hacking ético

- Antes de realizar ninguna acción, discutir con el cliente las tareas que llevará a cabo el analista durante el Hacking Ético, así como los roles y responsabilidades de ambos.
- Asegurar mediante contrato firmado que las acciones que se llevan a cabo son en representación del cliente.
- Análisis de las políticas de la organización que definen el uso que los usuarios hacen de los sistemas y de la infraestructura.
- Procedimiento en el caso de que se localice una intrusión por un tercero.

# Mejores prácticas para el hacking ético
- Obtener autorización: Antes de realizar cualquier prueba de penetración o análisis de vulnerabilidades, es esencial obtener la autorización del propietario del sistema o red que se está evaluando.
- Documentar todo: Es importante documentar todas las actividades realizadas durante la evaluación de seguridad, incluyendo cualquier vulnerabilidad encontrada y las medidas tomadas para corregirlas.
- Mantener la confidencialidad: Todo lo descubierto durante la prueba de penetración debe mantenerse en secreto y no debe ser compartido con terceros sin autorización.
- No causar daño: El objetivo del hacking ético es mejorar la seguridad del sistema, no dañarlo. Por lo tanto, es importante asegurarse de que las pruebas de penetración no causen daño a los sistemas evaluados.
- Conocer y cumplir las leyes y regulaciones: Es importante conocer las leyes y regulaciones locales, nacionales e internacionales relacionadas con la seguridad informática y asegurarse de cumplirlas durante cualquier actividad de hacking ético.

# Metodologías de seguridad

Existen una gran cantidad de metodologías actualmente reconocidas y ampliamente
utilizadas por profesionales a nivel internacional. De entre ellas cabe destacar:
- OSSTMM: Metodología genérica y muy amplia.
- PTES (Penetration Testing Execution Standard): Metodología especializada en test de intrusión
En cuanto a certificaciones mas acotadas:
- OWASP: Auditoria de aplicaciones Web
- OWISAM: Auditoria de redes Wi-Fi
- OASAM: Auditoria de aplicaciones móvil (Android)

**OWASP**

Es una metodología desarrollada por el proyecto OWASP, que tiene por objetivo
exponer todos los detalles necesarios para realizar ejercicios de auditoria e
intrusión en aplicaciones web.

Uno de los beneficios mas destacados de esta metodología es el alto nivel de
detalle en que se explican cada una de las pruebas a realizar. Esto permite a
auditores junior o gente menos experta poder seguir la metodología de manera
correcta.

Para ello, han elaborado la OWASP Testing Guide.

**PTES**

Es una metodología abierta desarrollada por reputados profesionales en el ámbito
de la seguridad. Dicha metodología tiene un claro enfoque en el desarrollo de
ejercicios de intrusión o “test de intrusión”.

Esta metodología cubre todas las fases necesarias que deben ser seguidas para
materializar una intrusión.

**OSSTMM**

Es una metodología abierta (v3) desarrollada por ISECOM, y es uno de los estándares
profesionales mas completos y comúnmente utilizados en auditoria de seguridad.
Dicha metodología consta de diferentes secciones que son:
- Sección A - Seguridad de la Información
- Sección B - Seguridad de los Procesos
- Sección C - Seguridad en las tecnologías de Internet
- Sección D - Seguridad en las Comunicaciones
- Sección E - Seguridad Inalámbrica
- Sección F - Seguridad Física

# Reportes

Para resolver esta duda y que tengáis ejemplos reales de cara a poder organizar
de la mejor forma posible vuestros informes, me gustaría dejaros por aquí varios
recursos que considero valiosos.

Antes de nada, debéis tener en cuenta que los informes de Hacking ético y
auditoría de seguridad dependen mucho de la organización que los realiza y del
tipo de auditoría que se ha llevado a cabo. 

No todas las auditoría son completas y siguen todas las fases que se enseñan en este curso, en algunas ocasiones se centran en fases o entornos específicos dentro de la infraestructura tecnológica de una organización. Todo esto se debe concretar en la fase de definición del alcance
que se mencionaba en la sección anterior.