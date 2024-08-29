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

