# Trabajo Práctico 1 - Técnicas de Elicitación de Requisitos

## Obtención de los requerimientos

### Parte I. Definiciones

#### (1) Definir brevemente qué es un requerimiento.

Un requerimiento es una característica, condición o capacidad de un sistema o componente de este, el cual debe cumplir para satisfacer el objetivo del mismo.

#### (2) Definir requerimientos funcionales y no funcionales.

Los requerimientos funcionales son aquellos requisitos que describen la interacción entre el sistema y su ambiente. Indican cómo debe comportarse el sistema ante determinado estímulo. Describen aquello que el sistema **debe hacer** o como **no debe** comportarse. Brindan detalles de la funcionalidad y son independientes de la implementación de la solución.

Los requerimientos no funcionales describen **restricciones** sobre el sistema, que limita elecciones en la construcción de una solución al probelma (no se relacionan de forma directa con el comportamiento del sistema). Pueden incluir requerimientos del producto (restricciones indirectas de su comportamiento, como la fiabilidad o portabilidad), requerimientos organizacionales y requerimientos externos (legales, privacidad, seguridad). Algunos ejemplos pueden ser la estética, consistencia con interfaz de usuario, tiempo de respuesta, entre otros.

#### (3) Definir que es un **stakeholder**.

Un **stakeholder** es toda aquella persona o grupo que se verá afectado por el sistema, directa o indirectamente (las partes interesadas en el sistema). Algunos de ellos pueden ser usuarios finales, ingenieros, gerentes, expertos del dominio, entre otros.

#### (4) Definir las fuentes más importantes para la obtención de información.

Las principales fuentes para la obtención de información, en cuanto a requerimientos, son:
- Documentación: que se tenga del dominio, o de la empresa/usuario objetivo del desarrollo del software.
- Stakeholders: personas o grupos que se verán afectadas por el sistema.
- Especificaciones de sistemas similares: se pueden analizar versiones anteriores del sistema u otros semejantes para obtener información útil de ellos, para el desarrollo del nuevo sistema.

#### (5) Indicar los puntos de vista (de manera genérica) que se pueden reconocer en un proyecto de software.

Existen 3 puntos de vista genéricos:
- Punto de vista de los interactuadores: representa personas o sistemas que interactúan directamente con el sistema objetivo.
- Punto de vista indirecto: representa stakeholders que no utilizar el sistema ellos mismos.
- Punto de vista del dominio: representa características y restricciones del dominio (área de conocimiento, influencia o actividad a la que el software construido va dirigido).

Los tres influyen en los requerimientos del sistema.

#### (6) Enumerar tres problemas de comunicación que pueden existir en la elicitación de requisitos.

Algunos de los problemas de comunicación que pueden surgir en la elicitación de requerimientos son:
- Cultura y vocabulario diferentes.
- No entender como la tecnología puede ayudar (por parte del cliente o usuario).
- Intereses distintos en el sistema a desarrollar (por parte de los distintos clientes o usuarios).

### Parte II. Problemas.

#### (a) Indicar para cada problema quiénes podrían ser los stakeholders, los puntos de vista y las fuentes de información.

**(1)**
En un sistema de registro de asistencia a través de técnicas biométricas de alumnos para la cátedra de Ingeniería I, los **stakeholders** serán todos aquellos afectados por la implementación del sistema. Se pueden mencionar:
- Estudiantes inscritos a Ingeniería I: serán los usuarios que interactuarán con el sistema.
- Cátedra Ingeniería I: incluye jefes de trabajos prácticos, titulares, ayudantes y todo personal docente. Es la parte interesada en el uso del sistema y su funcionalidad.
- Personal de la oficina de alumnos: de forma indirecta se verán afectados por la implementación del sistema. Proveen información para el desarrollo del sistema.
- Desarrolladores y administradores del sistema: incluye al grupo de personas implicado en el desarrollo del sistema, y a quienes deberán mantenerlo y gestionarlo una vez esté en funcionamiento.

El punto de vista de los **interactuadores** referirá a los estudiantes que cursen Ingeniería I, al jefe de trabajos prácticos y al profesor a cargo de la materia (podría ser más de uno). Estos actores son los que interactuarán de forma directa con el sistema.
El punto de vista **indirecto** está compuesto principalmente por el personal de la oficina de alumnos. Estos, si bien no interactuarán directamente con el sistema, brindan información para su desarrollo y podrían verse afectados por la nueva forma en la que los presentes se toman en la materia (pues estos estarán ligados a los resultados académicos de los alumnos).
El punto de vista del **dominio** está relacionado con el uso de las técnicas biométricas y la reglamentación de la institución sobre la privacidad de los datos de los alumnos. Debe incluirse tanto el apartado técnico sobre las cuestiones que implican el escaneo de datos biométricos, como el marco legal referente a la privacidad y seguridad de los datos que se recaban.

En cuanto a las **fuentes de información**, se presupone que no existe un sistema similar para el registro de asistencia. De esta forma, las principales fuentes de requerimientos provienen de la documentación sobre el dominio (técnicas de escaneo biométricas, y privacidad de los datos), así como stakeholders tales como el personal de la oficina de alumnos, docentes a cargo y jefes de trabajos prácticos (actores involucrados directamente en la tarea que tendrá el sistema) e incluso puede considerarse personal administrativo vinculado al manejo de los datos que el sistema deberá recabar como objetivo.

**(2)**
Los **stakeholders** del sistema planteado podrían ser los siguientes: primero se debe tener en cuenta los pacientes, aunque estos no utilicen el sistema como tal, son el objetivo del producto de software planteado. 
Luego se debe considerar al personal administrativo que registra los datos personales del paciente. Estos interactuarán con el sistema y, dada la naturaleza de su cargo, proveeran información vital para el desarrollo del mismo.
Asimismo, se debe considerar al enfermero, que continuará la labor de recabación de datos del paciente. El doctor, por su parte, contribuirá aportando registros sobre el tratamiento recomendado, así como dejar constancia si el paciente debe quedar internado. Esto último también implica una gestión de la historia clínica del paciente que sea internado.
El director de la clínica es otra de las partes interesadas, pues busca que el sistema le provea acceso a las historias clínicas de los pacientes.
Estos son los stakeholders más evidentes del sistema a desarrollar. Además, se debe considerar miembros del grupo de desarrollo del proyecto (todos sus roles), así como personal administrativo de la clínica que se encargue de gestionar la información de los pacientes, almacenarla y demás cuestiones relacionadas.

En cuanto a los puntos de vista, el de los **interactuadores** podría incluir al personal administrativo (que toma los datos), enfermero, doctor y el director de la clínica. Estos actores interactuarán directamente con el sistema. También se podría incluir otro sistema, si es que hay, que tome los datos recabados y los utilice de alguna forma.
Considero que el punto de vista **indirecto** sería principalmente por parte de los pacientes. Estos no utilizan el sistema y no pueden acceder a él, pero son parte vital del mismo, es por ellos que se desarrolla, pues la administración de sus datos es el objetivo del sistema.
El punto de vista del **dominio** puede referir a cuestiones como la protección y confidencialidad de los datos de los pacientes, el soporte del flujo de trabajo planteado (personal administrativo recaba datos personales, luego enfermero con controles, etc.), un sistema de permisos (pues los doctores pueden ver la historia clínica de sus pacientes, pero el director puede acceder a todas), eficiencia en cuanto al acceso (tiempo de respuesta) y capacidad para realizar actualizaciones en tiempo real, entre otros.

Finalmente, las **fuentes de información** puede provenir de las tres principales fuentes de requerimientos:
- Documentación: incluye tanto cuestiones legales en cuanto a la protección de la privacidad de los datos, como gestión de la información por parte de la clínica. Será de utilidad documentación acerca del funcionamiento de la clínica y el flujo de atención de los pacientes.
- Stakeholders: será de vital importancia consultar con las partes interesadas para analizar los requisitos del sistema. Tanto personal administrativo (cuya tarea es el primer paso en la recabación de los datos), enfermeros (tomarán nota sobre los controles a los pacientes), doctores (modificarán y tendrán acceso diario a las historias clínicas de sus pacientes) y el director de la clínica (usuario con acceso privilegiado, que podrá consultar la totalidad de información del sistema). Además se puede considerar personal encargado de la gestión y almacenamiento de la información, en la base de datos que la clínica posea.
- Especificaciones de sistemas similares: tanto si es un sistema inteligente que será actualizado o si es manual, se debe analizar el funcionamiento de este y su tarea en la obtención y administración de los datos, pues puede servir de referencia para el sistema en desarrollo.

#### (b) Habiendo resuelto los problemas presentados, ¿por qué considera que los requerimientos de los distintos stakeholders podrían entrar en conflicto?

Es natural que los requerimientos de los distintos stakeholders involucrados puedan entrar en conflicto. Esto se debe a que cada uno concibe el sistema para su propio uso, o su propia idea de negocio. Dado que cada uno tiene distintos roles, los requisitos muchas veces pueden ser contrarios unos a otros.
Por ejemplo, en el segundo problema, el personal administrativo buscará que el sistema presente facilidad en el registro de los datos personales, mientras que los doctores querrán que el sistema sea centralizado y accesible, así como eficiencia operativo en cuanto al acceso y actualización en tiempo real. Por otro lado, el director de la clínica no modificará los datos, por lo que su enfoque estará vinculado a la estructuración y visualización de la información de una forma detallada y cómoda.
Si bien estos requerimientos pueden ser afines en muchos casos, es común que puedan presentarse conflictos cuando se intenen congeniar.

___

## Entrevistas

### Parte I. Definiciones.

#### (1) Describir qué tipo de información puede obtenerse en una entrevista.

La entrevista es una técnica de exploración en la que el analista recolecta información a través de la interacción cara a cara. Esto le permite conocer sentimientos y opiniones del entrevistado. Es una conversación con un propósito específico.
Permite obtener información verbal en base a las respuestas del entrevistado, e información no verbal observando las acciones y expresiones del mismo.

#### (2) Enumerar y describir brevemente las etapas de la preparación de una entrevista.

La preparación previa de una entrevista puede implicar:
- Leer antecedentes: implica, entre otras cosas, aprender vocabulario relacionado al dominio.
- Establecer objetivos de la entrevista: usando los antecedentes, se diseña una visión general de la entrevista.
- Seleccionar entrevistados: los entrevisstados deben conocer el objetivo y preguntas de la entrevista.
- Planificación de la entrevista: se establece fecha, hora, lugar y duración de acuerdo con el entrevistado.
- Estructura de las preguntas: se define el flujo de preguntas y su formulación.

#### (3) Enumerar y describir brevemente qué tipos de preguntas puede contener una entrevista. Detalle ventajas y desventajas de cada una.

Los tipos de pregunta de una entrevista pueden ser:
- Abiertas:

    Ventajas:
    - revelan nueva línea de preguntas
    - permiten espontaneidad

    Desventajas:
    - puede dar detalles irrelevantes
    - parece que el entrevistador no tiene los objetivos claros
- Cerradas:

    Ventajas:
    - ahorran tiempo
    - se mantiene fácilmente el control de la entrevista
    - se consiguen datos relevantes
    Desventajas:

    - puede aburrir al encuestado
    - no se obtienen detalles
- De sondeo: buscan obtener más detalle sobre un tema puntual, lo que brinda información más precisa, pero puede ser demasiado específica y otorgar información en algunos casos irrelevante.

#### (4) Enumerar y describir brevemente qué tipo de estructuras y organización existen para el armado de una entrevista.

Existen 3 principales formas de organización de una entrevista:
- Piramidal (inductivo): se basa en comenzar la entrevista con preguntas cerradas y finalizarla con preguntas abiertas.
- Embudo (deductivo): implica comenzar la entrevista con preguntas abiertas y terminar con preguntas cerradas.
- Diamante: una combinación entre organizaciones anteriores, se basa en comenzar la entrevista de forma piramidal (preguntas cerradas a abiertas) y terminar en forma de embudo (preguntas abiertas a cerradas).

#### (5) Analizar un formato de la planilla adecuado al momento de armar una entrevista.

Para armar una entrevista es necesario planificar la misma, por lo que el diseño de una planilla puede resultar útil. Se debe especificar la organización de la entrevista (piramidal, embudo, diamante). Se deben asentar datos de la entrevista como el entrevistado, fecha, hora, lugar y tema. Además, se deben detallar las preguntas junto con el tiempo asignado a cada una y la respuesta del entrevistado, así como los objetivos de la entrevista. 
Cada pregunta tiene su objetivo. Puede comenzarse con preguntas que evalúen el funcionamiento del sistema actual, de los criterios del proceso en cuestión y detalles sobre este. Puede continuarse con preguntas para obtener información sobre la tarea y magnitud del sistema. 

#### (6) Analizar un formato de la planilla adecuado al momento de terminar una entrevista.

Así como la planilla para la planificación de la entrevista resulta útil para su creación, esta también detalla la finalización de la misma.
En la planilla, la sección del término de la misma puede indicar una pregunta abierta tal como "¿Le queda algo más para añadir?", que resulta útil para obtener detalles finales o explorar cuestiones que el entrevistado no haya podido conversar previamente. Luego, debe asentarse en la planilla lo referente a la finalización de la entrevista, tal como agredecer al entrevistado y asegurar la retroalimentación de los resultados de las respuestas. Además, se indica el tiempo asignado para preguntas y objetivos, preguntas de seguimiento y redirección, y finalmente el tiempo total de la entrevista.
En la última sección, se detallan comentarios generales y notas que el entrevistador redacta.

### Parte II. Situaciones.

#### Situación 1:

**(a)**
*Sus subordinados me dijeron que la empresa no anda bien. ¿Es cierto?*

Reformulación: ¿Cuál considera que es la situación de la empresa actualmente?

Considero que la versión anterior no es apropiada debido a que toma opiniones de otros empleados y las comunica al gerente (lo que podría ir en contra de la confidencialidad que haya habido con ellos). Además, es un pregunta cerrada que busca un si o no como respuesta, brindando poca información. Por último, puede resultar ofensiva y da por hecho una situación que no podría no ser cierta.

**(b)**
*Soy nuevo en esto. ¿Qué he dejado afuera?*

Reformulación: ¿Le gustaría añadir algo más?

La versión inicial no muestra la confianza que debería tener un entrevistador. Además, resulta demasiado informal.

**(c)**
*¿Estará usted de acuerdo con los demás gerentes de ventas, respecto a que computarizar las ventas mensuales y luego realizar un análisis de la tendencia tendría grandes mejoras?*

Reformulación: ¿Que beneficios cree que le podría dar al negocio la computarización de las ventas mensuales?

La versión original resulta demasiado larga, incluye opiniones de terceros e intenta tratar un tema el cual el entrevistador no domina. Es importante recordar que el conocimiento del dominio lo tiene el cliente, por lo que no se debería plantear ideas referentes al mismo sin que el cliente lo formule por si mismo.

**(d)**
*¿No habrá una mejor manera de hacer proyecciones de sus ventas, que ese procedimiento anticuado que usted utiliza?*

Reformulación: ¿De qué forma considera que se podría mejorar la proyección de las ventas?

La primera pregunta puede resultar ofensiva y nuevamente el entrevistador intenta tratar un tema del dominio. El desarrollador puede recomendar cuestiones vinculadas al sistema en si, pero no debería inmiscuirse en el modelo de negocio del cliente, pues es este el que lo conoce mejor.

#### Situación 2:

**(a, b)**
La primera opción sería buscar reprogramar la entrevista, en caso de que el entrevistado tenga urgencia en atender sus otros asuntos.
Si esto no es posible, se podría intentar explicarle la importancia que la entrevista supone para el desarrollo del sistema que es de su interés, además de indicar que la misma no tomará demasiado tiempo. Luego de esto, se podrían tomar dos enfoques:
- Realizar las preguntas tal cual están en la programación de la entrevista, o intentar hacerlas más abiertas de forma tal que el entrevistado se sienta más en confianza y pueda explayarse para relajarse.
- Reformular mínimamente en la medida de lo posible las preguntas para hacerlas más cerradas, intentando acortar el tiempo. Esto podría comprometer la información obtenida.

#### Situación 3:

**(a)**
El informe deja la sensación de que el entrevistador ha perdido el control de la entrevista. El entrevistado ha comenzado a hablar y se ha explayado durante demasiado tiempo en una cuestión puntual, dejando de lado las preguntas cuyo objetivo era obtener la información relevante de los requerimientos.

**(b)**
Si bien la historia del negocio y el historial de cambios puede resultar útil como documentación para el análisis de los requerimientos, considero que se ha extendido demasiado, brindando detalles que son irrelevantes para el desarrollo del sistema.

**(c)**
Considero 3 principales sugerencias:
- Elaborar una planificación de la entrevista y seguirla tanto como sea posible. Las preguntas formuladas en esta son relevantes para la elicitación de los requisitos.
- Mantener el control de la entrevista. Es importante que el entrevistado marque el ritmo de la conversación, dejando hablar al entrevistado pero en su justa medida.
- Habiendo sido testigo del tipo de persona que es el entrevista (una que acostumbra a explayarse), podría ser conveniente elaborar preguntas que vayan más a lo puntual, y de carácter más cerrado.

### Parte III. Problemas.

#### Problema 1:

La entrevista tiene organización de tipo embudo, comenzando con preguntas abiertas y finalizando con preguntas cerradas.
Tema: sistema que permita compartir vehículo para un viaje.

Comienzo:
Me presento, agradezco el tiempo que el entrevistado me brinda y explico la razón de la entrevista (aunque el entrevistado ya posee información básica sobre esto): entender más a detalle el objetivo y alcance del software a desarrollar.

¿De que forma se organizan actualmente los viajes conjuntos, si es que hay?
**Objetivo:** tener noción acerca de como se lleva a cabo el proceso actualmente, para entender que soluciones podría traer el nuevo sistema.

¿De qué forma se daría la reunión entre conductor y pasajero, en cuestiones de tiempos y ubicación?
**Objetivo:** intentar comprender la idea del entrevistado, conduciéndolo a un tópico más acotado: la ubicación y tiempo en el que se establece la comunicación entre dos usuarios finales.

¿Qué opciones debería poder considerar el conductor a la hora de buscar un acompañante?
**Objetivo:** buscar filtros, opciones y restricciones que debe tener el sistema.

¿Qué información debe poder tener el pasajero acerca de la oferta de conductores?
**Objetivo:** saber a que tipo de información debería poder acceder el usuario final.

¿Considera que debería haber un sistema de puntuación de servicio y recomendaciones?
**Objetivo:** saber el tipo de retroalimentación que habría en cuanto al servicio ofrecido por el sistema.

Final:
Agradezo su tiempo y colaboración. Le aseguro que recibirá un informe de los resultados de la entrevista.

#### Problema 2:

La entrevista tiene organización de tipo embudo, comenzando con preguntas abiertas y finalizando con preguntas cerradas.
Tema: sistema de venta de libros de cocina en línea.

Comienzo:
Me presento, agradezco el tiempo brindado a los entrevistados y comento el propósito de la entrevista: obtener una comprensión más precisa del sistema utilizado y los detalles del nuevo software a implementar.

¿Podría describirme como funcionaba su sistema de ventas en línea?
**Objetivo:** obtener información sobre sistema anterior.

¿Cuál es el perfil de sus clientes y que tipo de usuario esperan que utilice el nuevo sistema?
**Objetivo:** saber que clase de usuario utilizará el sistema y diseñarlo en base a esto.

¿A qué información acerca de los productos considera que debería tener acceso el usuario?
**Objetivo:** establecer ideas y restricciones para los elementos del sistema.

¿Cuál es el volumen de ventas mensuales?
**Objetivo:** permite conocer la cantidad de solicitudes que recibirá el sistema.

¿Qué información le interesa saber sobre sus clientes?
**Objetivo:** obtener detalles sobre los datos requeridos para las cuentas de usuarios finales.

¿Qué tipos de servicio de entrega consideran?
**Objetivo:** conocer posibilidades y restricciones del sistema acerca del despacho de productos.

¿A qué información le interesaría acceder acerca de las ventas?
**Objetivo:** conocer detalles a incluir sobre los productos que conforman el sistema

¿Le gustaría tener interacción con los clientes? Si es así, ¿de qué tipo?
**Objetivo:** conocer características de retroalimentación del sistema

¿Piensa que sería útil tener opciones para filtrar productos según sus características?
**Objetivo:** saber si son necesarias opciones de filtrado y ordenación. De ser así, cuales y de que forma.

¿Le gustaría añadir algo más?

Final:
Agradezco la colaboración y prometo enviar datos sobre los resultados.

## Cuestionarios

### Parte I. Definiciones.

#### (1) Describir qué tipo de información se busca mediante la aplicación de cuestionarios.

El cuestionario es un documento que permite al analista recabar información y opiniones de los encuestados. Recolecta hechos de gran número de personas, detecta sentimientos generalizados y problemas entre usuarios, y permite cuantificar las respuestas.

#### (2) Describir bajo qué circunstancia considera apropiado utilizar cuestionarios.

Los cuestionarios resultan útiles cuando los encuestados son muchos o están lejos unos de otros. Además, permite obtener información de muchas personas, lo que implica recibir opiniones y/o problemas generalizados, que permitan detectar cuestiones que afectan a una gran mayoría. Aunque es menos íntimo y no posibilita analizar el lenguaje no verbal, si que sondea las opiniones de grupos grandes de personas.

#### (3) Describir los dos tipos de cuestionarios.

Los dos tipos de cuestionarios se basan en sus preguntas. Estos tipos son:
- Cuestionarios de preguntas abiertas: permite obtener todas las posibles opciones de respuesta. Brindan mayor información y son de fácil preparación. Sin embargo, su análisis es lento y difícil.
- Cuestionarios de preguntas cerradas: posee opciones fijas. Tienen poca naturaleza exploratoria y profundida. Su preparación es más compleja. Sin embargo, su análisis es fácil y rápido.

### Parte II. Situaciones.

#### Situación 1:

Reformulación del cuestionario:

Se les pide a todos los encuestados que completen a detalle y con total sinceridad las siguientes consignas, con el fin de mejorar las condiciones del sistema actual: 
1. Enumere tres principales problemas que considera que tiene el centro de cómputo actual.
2. ¿De qué forma han afectado estos inconvenientes al trabajo conjunto en el centro de cómputo?
3. ¿Con qué frecuencia ocurren los problemas mencionados?
4. ¿Cuál considera que es el motivo por el cuál estos problemas no han sido tratados?

#### Situación 2:

**(b)**
El diseño del cuestionario, con un pequeño espacio blanco para las respuestas, limita significativamente la longitud de las respuestas. Dada la naturaleza abierta de las preguntas, considero que se debería incluir un espacio de respuestas de mayor tamaño. Además, el formato hace que tanto preguntas como respuestas queden superpuestas debido a la decisión de incluir una al lado de la otra.

**(a, c)**
En base a las modificaciones, el cuestionario se reformularía de la siguiente manera:

¡Saludos a todos los empleados!
Con motivo de actualizar nuestro sistema de computadoras, nos gustaría conocer su opinión acerca de las siguientes cuestiones:
1. ¿Durante cuanto tiempo ha trabajado en el sector de las computadoras?
`espacio de respuesta`
2. ¿Cuál es la frecuencia con la que el sistema suele fallar?
`espacio de respuesta`
3. ¿Cuánto tiempo toma solucionar estas fallas?
`espacio de respuesta`
4. En base al tiempo trabajado con el sistema, ¿qué actualizaciones considera que debería tener este para mejorar o facilitar su uso?
`espacio de respuesta`
5. ¿Cuáles de los dispositivos en el sector de cómputo utiliza con más frecuencia (pantalla, impresora, etc.)?
`espacio de respuesta`
6. ¿Qué cantidad de personas y con qué frecuencia se accede a la base de datos de su sucursal?
`espacio de respuesta`