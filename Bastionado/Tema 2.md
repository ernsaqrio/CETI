**1.- Análisis de riesgos**

Para poder conocer a qué amenazas se encuentran sujetos los activos de una organización, el primer paso es llevar a cabo una evaluación de cuál es la situación inicial, en términos de ciberseguridad, de la organización. 

Esta fase conlleva una serie de actividades que describiremos a continuación.

*Conocer la situación actual del sistema u organización*

Sin duda es indispensable conocer la situación actual en términos de ciberseguridad de la organización o sistema sobre el que vamos a hacer el análisis. 

Nunca podremos estar seguros de si realmente estamos elevando el nivel de seguridad si no conocemos la situación de partida.

Para llevar a cabo este primer análisis, tendremos en cuenta los aspectos esenciales sobre los que hemos de realizarlo como por ejemplo:
- Nivel de madurez de la empresa
- Elementos técnicos
- Aspectos organizativos
- Cumplimiento o normativa vigente
- Criticidad de la información

Es necesario implicar a toda la organización, pues debemos realizar una serie de actividades como entrevistas, cuestionarios, etc. para recopilar la información necesaria de cara a llevar a cabo el análisis. 

En este punto podríamos encontrar dificultades o problemas como que no se nos facilitara toda la
información, de manera intencionada o no, no contar con el apoyo de áreas críticas, como el área de TI, etc. 

Además será necesario contar con el apoyo de la dirección o la parte estratégica de la organización para esta cuestión ya que, por ejemplo, si no creen en las bondades de la ciberseguridad, difícilmente podremos incrementar el nivel de seguridad ya que no se facilitará presupuesto y se demorarán los plazos establecidos priorizando otras cuestiones.

*Limitar el alcance*

Para poder implementar ciberseguridad desde un punto de vista efectivo y eficiente, se ha de limitar el alcance del proyecto y este además ha de ser realista. 

Por un lado para conocer el tamaño de las tareas que tendremos que llevar a cabo, y por otro para concretar sobre qué áreas o procesos se llevará a cabo. 

Por ejemplo, en una empresa dedicada a la investigación, una de las áreas más importantes a proteger será la relativa a I+D+i.

Tendremos que realizar una identificación de activos que serán los objetivos donde se aplicarán los controles de seguridad que implementemos, tanto a nivel técnico como organizativo sin olvidar los de carácter normativo. 

Lo habitual es que una vez determinados los más críticos, las tareas de protección comiencen por estos. 

Un buen punto de partida para determinar qué controles se han de implementar, podría estar basado en el listado de la norma[ ISO/IEC 27001. ]()

Estos controles han de estar dirigidos por los que se denominan escalas o modelos de madurez que pueden tener distintos valores en función de cómo se encuentre implementado en la organización.

Tomando como ejemplo los basados en [CMM]() y considerando el control relativo a las copias
de seguridad, este podría ser:
- Inexistente: carecen de política de copias de seguridad.
- Inicial: disponen de un sistema, pero nadie las controla ni se planifican.
- Repetible: se lleva a cabo la política pero sin ningún tipo de normalización, habitualmente bajo demanda.
- Definido: existe un procedimiento claro, pero no está aprobado por la dirección.
- Administrado: existe un procedimiento formal que ha sido aprobado.
- Optimizado: existe un procedimiento formal que ha sido aprobado y se verifica su eficacia periódicamente mediante indicadores.

**1.1- Fases del análisis**

Llevaremos a cabo el análisis propiamente dicho en todas sus fases para obtener el listado de posibles amenazas que podrían afectar al sistema analizado. 

Las mas destacadas son las siguientes:

*Fase inicial: reconocimiento*
1. Identificación de activos: para identificar las amenazas a las que podrían estar sujetos.
2. Identificación del riesgo intrínseco: resultante de la fase previa y que, nos dará el nivel de riesgo del activo sin la aplicación de los controles que mejorarán la seguridad.
3. Probabilidad de ocurrencia: estableceremos la posibilidad de que se materialice la amenaza sobre el activo y que pueda generar un impacto y las consecuencias derivadas. En este punto podremos calcular el nivel de riesgo siguiendo la fórmula: [[Formula de probabilidad de ocurrencia y ejemplo]] Este ejemplo, evidentemente indica que se requiere establecer un control para esta cuestión.
4. Riesgos no aceptables: tras el paso previo, hemos de identificar aquellos riesgos que no son aceptables. Estos serían aquellos que pueden afectar muy negativamente al negocio hasta el punto de dejar la organización sin servicio. El tipo de control a implementar, será siempre proporcional al activo que se quiere proteger.
5. Riesgo residual: determinará el nivel de riesgo tras su reducción considerando este con un valor “aceptable”.

*Mitigación de riesgos*

Tras la fase previa, en esta será donde se establecerán los mecanismos y controles que permitirán definir un nivel de riesgo aceptable y asumible. ¿Con qué mecanismos contamos para llevar a cabo esta tarea? Podemos implementar los siguientes:
1. Implementar controles para su mitigación: suele ser la más habitual cuando se trata de problemas que pueden interferir en el correcto funcionamiento de los procesos de una organización.
2. Eliminando el riesgo: cuando se trata de un proceso que no es necesario pero que podría poner en peligro otros activos de la organización.
3. Tercerizar o transferir el riesgo: a través por ejemplo de un ciberseguro o una póliza de [ciber-riesgos.]()

*Establecimiento de indicadores y verificación del proceso*

Tras definir los controles, se han de establecer [cuadros de mando]() que nos permitan medir el correcto funcionamiento de los controles. 

Si no tenemos en cuenta esta cuestión, es decir si no medimos, nunca sabremos si realmente el control está funcionando. 

Por ejemplo, en una política de copias de seguridad, si no comprobamos la frecuencia con que se hacen y si no verificamos su posible restauración, no podremos estar seguros de si realmente la misma está funcionando de manera correcta. 

De esta manera verificaremos que la medida que se ha implementado es efectiva contra el riesgo que queremos reducir.

Por último, es importante indicar, que el análisis de riesgos es un proceso continuo y que se
debe llevar a cabo de manera periódica pues las tecnologías, servicios e infraestructuras de
las organizaciones cambian frecuentemente en el mundo TI. 



