# Trabajo Práctico 3 - Casos de uso

## Parte I: Definiciones generales

#### a) Describir qué es el desarrollo centrado en el usuario.

El desarrollo centrado en el usuario refiere a la filosofía de diseño que concibe al usuario como eje central de la creación de productos. Su principal objetivo es satisfacer las necesidades y resolver los problemas de los usuarios para los cuales el producto está destinado. No es posible concebir el producto desligado de su uso, el contexto o las necesidades del usuario final.

#### b) Definir qué son los casos de uso y describa cómo se utilizan.

Los casos de uso son una técnica de especificación de requerimientos que consiste en el modelado de las funcionalidades del sistema, en términos de los eventos que interactúan entre los usuarios y el sistema.
Es una herramienta para capturar los requerimientos funcionales, descompone el alcance el sistema en componentes manejables y permite estimar dicho alcance.
Se compone de un diagrama que ilustra las interacciones entre los actores y el sistema, además de escenarios que describen dichas interacciones para realizar la funcionalidad.

#### c) Definir qué es un actor y un escenario.

Los actores representan personas, sistemas o dispositivos externos que ofician de usuario e interactúan con el sistema tomando un determinado papel o rol. Generalmente son los que inician la actividad en el sistema.
Los escenarios describen la interacción entre los actores y el sistema de forma detallada, indicando el curso normal de funcionamiento y eventos alternos que puedan producirse durante este.

#### d) Definir las relaciones que pueden presentarse en el diagrama de casos de uso. Describa cuándo se utiliza cada una.

Las tipos de relaciones que pueden presentarse en el diagrama son:
- Asociaciones: relación entre actor y caso de uso, ya sea iniciada por el usuario o no.
- Extensiones: indican que un caso de uso extiende la funcionalidad de otro. Sirve para conformar un caso de uso completo a partir de otros descompuestos. Un caso de uso no puede extender a más de uno.
- Uso o inclusión: reduce redundancia entre dos o más casos de uso al combinar pasos comunes, utilizando funcionalidad común. Debe haber más de un caso de uso que use a otro.
- Herencia: relación entre actores donde un actor hereda las funcionalidades (relaciones) de uno o varios actores.

#### e) Enumerar los beneficios de modelar requerimientos del sistema con casos de uso.

El uso de esta herramienta permite:
- Facilitar y alentar participación de los usuarios
- Capturar los requerimientos funcionales
- Descomponer el alcance del sistema en piezas más manejables
- Simplifica comunicación con los usuarios (debido a que utiliza lenguaje común y fácil de entender)
- Permite estimar el alcance del proyecto y el esfuerzo a realizar.
- Define línea base para definición de planes de prueba y toda la documentación del sistema.
- Proporciona herramientas para el seguimiento de los requisitos.

## Parte II: Ejercitación

(Solo escenarios)

#### (1) Alquiler mobiliario

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Iniciar Sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Decribe el modo en que el encargado inicia sesión en el sistema con usuario y contraseña</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Encargado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
    <td>Paso 1: el encargado presiona la opción de iniciar sesión</td>
    <td>Paso 2: el sistema solicita usuario y contraseña</td>    
  <tr>
  <tr>
    <td>Paso 3: el encargado ingresa su usuario y contraseña</td>
    <td>Paso 4: el sistema verifica el usuario y contrseña ingresados</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: el sistema registra la sesión iniciada y habilita las funcionalidades del encargado</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso alternativo 4: Falla la verificación por usuario o contraseña no válidas. Se notifica situación. Se ejecuta nuevamente paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión ha sido iniciada y se han habilitado las funciones del encargado en el sistema</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cerrar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el cierre de sesión por parte del encargado autenticado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Encargado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el encargado presiona la opción de cierre de sesión</td>
    <td>Paso 2: el sistema solicita confirmación del usuario</td>    
  </tr>
  <tr>
    <td>Paso 3: el encargado confirma la operación</td>
    <td>Paso 4: el sistema cierra la sesión y deshabilita funciones de encargado</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión se encuentra cerrada, las funciones de encargado deshabilitadas y se eliminan datos de la sesión</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Alta mobiliario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la operación de carga de un mobiliario en el sistema por parte de un encargado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Encargado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El encargado debe tener la sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el encargado selecciona la opción de carga mobiliario</td>
    <td>Paso 2: el sistema solicita los datos de código, tipo de mueble, fecha de creación, fecha de último mantenimiento, estado y precio de alquiler</td>    
  </tr>
  <tr>
    <td>Paso 3: el encargado ingresa los datos del mueble, solicitados por el sistema y presiona confirmar</td>
    <td>Paso 4: el sistema verifica el código de mueble ingresado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema realiza la carga del mueble y habilita para su reserva</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso alternativo 4: el código de mueble ingresado ya existe. Se notifica el error. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El mueble ha sido dado de alta en el sistema y se encuentra disponible para su visualización y reserva</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Realizar reserva</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la realización de la reserva de un mueble por parte de un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción para Reservar muebles</td>
    <td>Paso 2: el sistema solicita los datos de fecha, lugar del evento, cantidad de días y mobiliario de la reserva</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente ingresa los datos requeridos, selecciona los muebles y presiona confirmar</td>
    <td>Paso 4: el sistema verifica la disponibilidad de los muebles</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica la cantidad de muebles indicada</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: el sistema ejecuta el CU "Pagar con tarjeta"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema realiza la reserva de los muebles y emite número de reserva único</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: los muebles seleccionados no se encuentran disponibles. El sistema notifica la situación. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: la cantidad de muebles seleccionados es inferior a 3. Se notifica al cliente. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el pago no se realiza. Se notifica al cliente. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La reserva ha sido realizada y el número de reserva único ha sido emitido</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Pagar con tarjeta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el pago con tarjeta de una reserva por parte de un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo de banco, Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Realizar reserva"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el cliente ingresa los datos de la tarjeta</td>
    <td>Paso 1: el sistema solicita los datos de la tarjeta</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo acepta la conexión y solicita datos de la tarjeta</td>
    <td>Paso 3: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 6: el servidor externo valida los datos y fondos suficientes</td>
    <td>Paso 5: el sistema envía datos de la tarjeta al servidor externo</td>
  </tr>
  <tr>
    <td>Paso 7: el servidor externo retorna el resultado</td>
    <td>Paso 8: el sistema recibe el resultado de verificación de datos de la tarjeta</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema recibe el resultado de verificación de fondos suficientes</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema registra el pago y finaliza la conexión con el servidor externo</td>
  </td>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 3 alternativo: la conexión con el servidor externo falla. Se notifica error. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 8 alternativo: la validación de datos de la tarjeta no es correcta. Se informa error en los datos de la tarjeta. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: la validación de fondos suficientes es incorrecta. Se notifica fondos insuficientes. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se efectuó y registró el pago a través de la tarjeta</td>
  </tr>
</table>

#### (2) Posgrado

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cargar carrera</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la carga de una carrera de posgrado al sistema por parte del empleado administrativo</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado administrativo</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de cargar carrera</td>
    <td>Paso 2: el sistema solicita datos de la carrera: nombre, duración, costo y cantidad máxima de cuotas para el pago</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa los datos solicitados y presiona confirmar</td>
    <td>Paso 4: el sistema verifica que no exista otra carrera con el mismo nombre</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: el sistema verifica que la duración de la carrera no sea mayor a 5 años</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: el sistema realiza el alta de la carrera y la lista entre las carreras disponibles</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: fallo por nombre de la carrera ya existente. Se notifica el error. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: fallo por duración de la carrera mayor al máximo permitido. Se notifica el error. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La carga de la carrera se ha realizado y la carrera se encuentra listada como posgrado disponible</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar Usuario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el registro de un usuario como alumno en el sistema</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Alumno no registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el alumno no registrado selecciona la opción de registro de cuenta</td>
    <td>Paso 2: el sistema solicita datos personales</td>    
  </tr>
  <tr>
    <td>Paso 3: el alumno no registrado completa los datos personales solicitados</td>
    <td>Paso 4: el sistema solicita nombre de usuario y contraseña</td>
  </tr>
  <tr>
  <td>Paso 5: el alumno no registrado completa los datos requeridos</td>
  <td>Paso 6: el sistema verifica que no exista otro usuario con mismo nombre</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema verifica que la contraseña sea de más de 6 dígitos</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema registra el alta del usuario</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el nombre de usuario ya existe. Se notifica. Se retoma paso 4.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 7 alternativo: la contraseña no cumple la cantidad de caracteres mínima. Se notifica. Se retoma paso 4.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se realiza el alta de una nueva cuenta de alumno</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Iniciar Sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Decribe el modo en que el alumno registrado inicia sesión en el sistema con usuario y contraseña</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
    <td>Paso 1: el alumno registrado presiona la opción de iniciar sesión</td>
    <td>Paso 2: el sistema solicita usuario y contraseña</td>    
  <tr>
  <tr>
    <td>Paso 3: el alumno registrado ingresa su usuario y contraseña</td>
    <td>Paso 4: el sistema verifica el usuario y contrseña ingresados</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: el sistema registra la sesión iniciada y habilita las funcionalidades del alumno registrado</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso alternativo 4: Falla la verificación por usuario o contraseña no válidas. Se notifica situación. Se ejecuta nuevamente paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión ha sido iniciada y se han habilitado las opciones del alumno registrado en el sistema</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cerrar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el cierre de sesión por parte del alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El alumno registrado debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el alumno registrado presiona la opción de cierre de sesión</td>
    <td>Paso 2: el sistema solicita confirmación del usuario</td>    
  </tr>
  <tr>
    <td>Paso 3: el alumno registrado confirma la operación</td>
    <td>Paso 4: el sistema cierra la sesión y deshabilita las opciones para alumnos registrados</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión se encuentra cerrada, las opciones para alumnos registrados deshabilitadas y se eliminan datos de la sesión</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Inscribir a carrera</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de inscripción a una carrera por parte de un alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El alumno debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el alumno registrado selecciona la opción de inscribirse a carrera</td>
    <td>Paso 2: el sistema muestra las carreras disponibles</td>
  </tr>
  <tr>
    <td>Paso 3: el alumno registrado selecciona una carrera de las listadas</td>
    <td>Paso 4: el sistema solicita dato de cantidad de cuotas a pagar</td>
  </tr>
  <tr>
  <td>Paso 5: el alumno registrado ingresa el dato requerido</td>
  <td>Paso 6: se ejecuta CU de "Pagar con tarjeta"</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 7: el sistema realiza la inscripción y emite comprobantes de inscripción y pago</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: no se realiza el pago. Se notifica. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha realizado la inscripción a la carrera por parte del alumno registrado. Se han emitido comprobantes de inscripción y pago.</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Pagar con tarjeta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el pago con tarjeta de la carrera de posgrado por parte de un alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo de banco, Alumno registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Inscribir a carrera"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el alumno registrado ingresa los datos de la tarjeta</td>
    <td>Paso 1: el sistema solicita los datos de la tarjeta</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo acepta la conexión y solicita datos de la tarjeta</td>
    <td>Paso 3: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 6: el servidor externo valida los datos y fondos suficientes</td>
    <td>Paso 5: el sistema envía datos de la tarjeta al servidor externo</td>
  </tr>
  <tr>
    <td>Paso 7: el servidor externo retorna el resultado</td>
    <td>Paso 8: el sistema recibe el resultado de verificación de datos de la tarjeta</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema recibe el resultado de verificación de fondos suficientes</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema registra el pago y finaliza la conexión con el servidor externo</td>
  </td>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 3 alternativo: la conexión con el servidor externo falla. Se notifica error. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 8 alternativo: la validación de datos de la tarjeta no es correcta. Se informa error en los datos de la tarjeta. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: la validación de fondos suficientes es incorrecta. Se notifica fondos insuficientes. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se efectuó y registró el pago a través de la tarjeta</td>
  </tr>
</table>

#### (3) Contratos

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Confeccionar minuta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de confección de una minuta por parte del empleado de mesa de entradas</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado de mesa de entradas</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado de mesa de entradas selecciona la opción de confeccionar minuta</td>
    <td>Paso 2: el sistema solicita los datos de la minuta: nombre y CUIT de la persona a contratar, tipo de contrato, fecha de comienzo, duración y monto</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado de mesa de entradas ingresa los datos requeridos</td>
    <td>Paso 4: el sistema verifica que el monto de la minuta sea menor a $25.000</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: el sistema verifica que la duración de la minuta no sea mayor a 6 meses</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: el sistema genera la minuta como pendiente de aprobación, con un número asociado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: fallo por monto de la minuta superior al permitido. Se notifica. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: fallo por duración de la minuta superior a la permitida. Se notifica. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se confeccionó la minuta con un número asociado y se indicó como pendiente de aprobación</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Aprobar minuta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la aprobación de una minuta confeccionada, por parte del empleado de rendiciones</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado de rendiciones</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Confeccionar minuta"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado de rendiciones selecciona la opción para aprobar minutas pendientes</td>
    <td>Paso 2: el sistema solicita el número de minuta</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado de rendiciones ingresa el dato requerido</td>
    <td>Paso 4: el sistema verifica que la persona a contratar no supere los 3 contratos vigentes</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: se ejecuta el CU "Verificación CUIT" </td>
  </tr>
  <tr>
  <td>Paso 7: el empleado de rendiciones confirma la aprobación</td>
  <td>Paso 6: el sistema muestra los datos de la minuta</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 8: el sistema aprueba la minuta</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: fallo por cantidad de contratos vigentes superior a la permitida. Se notifica. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: verificación de CUIT indica CUIT inválido. Se notifica CUIT inhabilitado. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: conexión con servicio de verificación de AFIP fallida. Se notifica error. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La minuta de número especificado fue aprobada</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Verificación CUIT</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la verificación de CUIT de la persona especificada en la minuta, por parte de AFIP</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo de AFIP</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Aprobar minuta"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el servidor externo establece la conexión y solicita token</td>
    <td>Paso 1: el sistema solicita conexión con servidor externo</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo valida el token y retorna estado de la conexión</td>
    <td>Paso 3: el sistema envía el token</td>
  </tr>
  <tr>
  <td>Paso 6: el servidor externo solicita CUIT</td>
  <td>Paso 5: el sistema recibe resultado de la conexión con el servidor externo</td>
  </tr>
  <tr>
  <td>Paso 8: el servidor externo verifica CUIT</td>
  <td>Paso 7: el sistema envía CUIT al servidor externo</td>
  </tr>
  <tr>
  <td>Paso 9: el servidor externo retorna el resultado de la verificación de CUIT</td>
  <td>Paso 10: el sistema recibe resultado de verificación de CUIT</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 11: el sistema registra el estado del CUIT y cierra la conexión con el servidor externo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 1 alternativo: fallo en establecer conexión inicial con el servidor externo. Se notifica. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: fallo en conexión con servidor externo por token inválido. Se notifica. Fin de CU. </td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se verificó el estado del CUIT de la persona especificada en la minuta.</td>
  </tr>
</table>

#### (4) Máquina de reciclado

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Reciclar</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de reciclado por parte de una persona</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Persona (Cliente)</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: la persona coloca lo que desea reciclar en el recipiente y presiona reciclar</td>
    <td>Paso 2: el sistema detecta el tipo de material</td>    
  </tr>
  <tr>
    <td></td>
    <td>Paso 3: el sistema registra el peso del elemento </td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 4: el sistema imprime recibo con monto total que se debe pagar</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 2 alternativo: fallo producido debido a que el sistema no detecta el tipo de material. Se notifica y retorna el producto. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El producto ha sido registrado y se ha emitido el recibo con monto total a pagar por lo reciclado</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Listar materiales reciclados</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso por el cual se solicita listado con tipos de materiales por parte de un operador</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Operador</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el operador selecciona la opción de solicitar listado con tipos de materiales reciclados</td>
    <td>Paso 2: el sistema solicita indicar un período</td>    
  </tr>
  <tr>
    <td>Paso 3: el operador indica el dato solicitado</td>
    <td>Paso 4: el sistema verifica los elementos listados en la fecha indicada</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema muestra los tipos de materiales reciclados en la fecha indicada junto al total abonado por dicho material</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: no hay productos reciclados en la fecha indicada. Se notifica. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se listaron los tipos de materiales y el total abonado en la fecha especificada</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Actualizar montos a pagar</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso por el cual se actualizan los montos a pagar por kilo de cada tipo de material por parte de un operador</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Operador</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el operador selecciona la opción de actualizar montos</td>
    <td>Paso 2: el sistema solicita el tipo de material a actualizar</td>    
  </tr>
  <tr>
    <td>Paso 3: el operador ingresa el dato solicitado</td>
    <td>Paso 4: el sistema solicita el nuevo monto</td>
  </tr>
  <tr>
    <td>Paso 5: el operador ingresa el dato solicitado y presiona aceptar</td>
    <td>Paso 6: el sistema actualiza el monto</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: el operador cancela la actualización. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El monto a pagar por el tipo de material especificado fue actualizado</td>
  </tr>
</table>

#### (5) Impresión de fotos

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar Usuario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el registro de un cliente como usuario del sistema</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente no registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente no registrado selecciona la opción de registro de cuenta</td>
    <td>Paso 2: el sistema solicita datos personales, nombre, apellido, email y domicilio</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente no registrado completa los datos solicitados</td>
    <td>Paso 4: el sistema solicita nombre de usuario y contraseña</td>
  </tr>
  <tr>
  <td>Paso 5: el cliente no registrado completa los datos requeridos</td>
  <td>Paso 6: el sistema verifica que no exista otro usuario con mismo nombre</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra el alta del usuario</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el nombre de usuario ya existe. Se notifica. Se retoma paso 4.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se realiza el alta de una nueva cuenta de cliente</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Iniciar Sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Decribe el modo en que el cliente registrado inicia sesión en el sistema con usuario y contraseña</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
    <td>Paso 1: el cliente registrado presiona la opción de iniciar sesión</td>
    <td>Paso 2: el sistema solicita usuario y contraseña</td>    
  <tr>
  <tr>
    <td>Paso 3: el cliente registrado ingresa su usuario y contraseña</td>
    <td>Paso 4: el sistema verifica el usuario y contrseña ingresados</td>
  </tr>
  <tr>
  <td></td>
  <td>Paso 5: el sistema registra la sesión iniciada y habilita las funcionalidades del cliente registrado</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso alternativo 4: Falla la verificación por usuario o contraseña no válidas. Se notifica situación. Se ejecuta nuevamente paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión ha sido iniciada y se han habilitado las opciones del cliente registrado en el sistema</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cerrar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el cierre de sesión por parte del cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente registrado debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente registrado presiona la opción de cierre de sesión</td>
    <td>Paso 2: el sistema solicita confirmación del usuario</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente registrado confirma la operación</td>
    <td>Paso 4: el sistema cierra la sesión y deshabilita las opciones para clientes registrados</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión se encuentra cerrada, las opciones para clientes registrados deshabilitadas y se eliminan datos de la sesión</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Subir fotos</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de cargar fotos en el sistema por parte del cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente registrado selecciona la opción de subir fotos</td>
    <td>Paso 2: el sistema solicita la carga de fotos</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente registrado carga las fotos</td>
    <td>Paso 4: el sistema verifica la cantidad de fotos cargadas</td>
  </tr>
  <tr>
    <td>Paso 5: el cliente registrado selecciona pagar</td>
    <td>Paso 6: se ejecuta el CU "Pagar con tarjeta"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema genera el código único para el retiro de las fotos, lo indica al usuario y vuelve a la menú principal</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: la cantidad de fotos es superior a 50. Se notifica. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el pago no se realiza. Se notifica. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Las fotos fueron cargadas y abonadas. Se generó código único para retiro de las fotos.</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Pagar con tarjeta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el pago con tarjeta de las fotos por parte de un cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo de banco, Cliente registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Subir fotos"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el cliente registrado ingresa los datos de la tarjeta</td>
    <td>Paso 1: el sistema solicita los datos de la tarjeta</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo acepta la conexión y solicita datos de la tarjeta</td>
    <td>Paso 3: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 6: el servidor externo valida los datos y fondos suficientes</td>
    <td>Paso 5: el sistema envía datos de la tarjeta al servidor externo</td>
  </tr>
  <tr>
    <td>Paso 7: el servidor externo retorna el resultado</td>
    <td>Paso 8: el sistema recibe el resultado de verificación de datos de la tarjeta</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema recibe el resultado de verificación de fondos suficientes</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema registra el pago y finaliza la conexión con el servidor externo</td>
  </td>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 3 alternativo: la conexión con el servidor externo falla. Se notifica error. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 8 alternativo: la validación de datos de la tarjeta no es correcta. Se informa error en los datos de la tarjeta. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: la validación de fondos suficientes es incorrecta. Se notifica fondos insuficientes. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se efectuó y registró el pago a través de la tarjeta</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Entregar fotos</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de entregar las fotos abonadas al cliente por parte del empleado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de retiro de fotos</td>
    <td>Paso 2: el sistema solicita código único</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa el dato requerido</td>
    <td>Paso 4: el sistema verifica el código único</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra el código y la fecha de retiro de las fotos</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el código no es válido. Se notifica. Se retoma paso 2.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El código único de las fotos y su fecha de retiro fueron registradas en el sistema</td>
  </tr>
</table>


#### (6) Ventas de Entradas para Teatro

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Comprar entrada vía web</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la compra de una entrada por la web por parte de un usuario cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de comprar entrada</td>
    <td>Paso 2: el sistema muestra la grilla de funciones disponibles</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente selecciona una de las obras de la lista</td>
    <td>Paso 4: el sistema solicita DNI y cantidad de lugares</td>
  </tr>
  <tr>
    <td>Paso 5: el cliente ingresa los datos requeridos y selecciona la opción pagar</td>
    <td>Paso 6: se ejecuta CU "Pagar con Tarjeta"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema emite código de compra de la/s entrada/s</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el pago no se realiza. Se notifica. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se registró compra y se emitió código de compra</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Reservar entrada</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de reserva de entrada realizado por un empleado (vendedor de boletería) para un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de reserva de entradas</td>
    <td>Paso 2: el sistema muestra una grilla de funciones disponibles</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado selecciona una de las obras de la lista</td>
    <td>Paso 4: el sistema solicita fecha de la obra, hora de la obra, nombre y DNI del cliente, y cantidad de entradas</td>
  </tr>
  <tr>
    <td>Paso 5: el empleado ingresa los datos requeridos</td>
    <td></td>
  </tr>
  <tr>
    <td>Paso 6: el sistema verifica la cantidad de entradas reservadas</td>
    <td></td>
  </tr>
  <tr>
    <td>Paso 7: el sistema registra la reserva de entradas</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: reserva fallida por cantidad de entradas solicitadas superior a 2. Se informa. Se retoma paso 4.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El sistema ha registrado la reserva de entradas del cliente junto a la hora en que se realizó</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Comprar entrada personalmente</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe la compra de una entrada en persona por parte de un empleado para un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de comprar entrada</td>
    <td>Paso 2: el sistema muestra grilla de funciones disponibles</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado selecciona una de las obras listadas</td>
    <td>Paso 4: el sistema solicita DNI del cliente y cantidad de lugares solicitados</td>
  </tr>
  <tr>
    <td>Paso 5: el empleado ingresa los datos requeridos y selecciona pagar</td>
    <td>Paso 6: se ejecuta CU "Pagar con Tarjeta"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra la compra de las entradas y las imprime</td>
  </tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado compra de entradas y se han impreso</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Retirar entradas reservadas</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de retiro de entradas reservadas realizado por un empleado para un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona opción de retiro de entradas reservadas</td>
    <td>Paso 2: el sistema solicita nombre y DNI del cliente</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa los datos solicitados</td>
    <td>Paso 4: el sistema verifica que el cliente indicado posea entradas</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica que las entradas no estén caducadas</td>
  </tr>
  <tr>
    <td>Paso 6: el empleado selecciona las entradas reservadas y selecciona pagar</td>
    <td>Paso 7: se ejecuta CU "Pagar con Tarjeta"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema registra el retiro de las entradas y las imprime</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: no hay entradas reservadas. Se informa. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: retiro fallido por entradas reservadas caducadas. Se informa. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El sistema ha registrado el retiro de las entradas reservadas y se han impreso</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Retirar entradas compradas</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de retiro de entradas ya compradas realizado por un empleado para un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de retiro de entradas compradas</td>
    <td>Paso 2: el sistema solicita código de compra</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa el dato requerido</td>
    <td>Paso 4: el sistema verifica el código de compra</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema imprime las entradas</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: código de compra no válido. Se notifica. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado retiro de entradas compradas y se han impreso</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Administrar programación de salas</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe proceso de administración de la distribución semanal de las obras en las salas por parte del administrador</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Administrador</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el administrador selecciona la opción de cargar distribución semanal</td>
    <td>Paso 2: el sistema solicita datos de las obras y sus horarios</td>    
  </tr>
  <tr>
    <td>Paso 3: el administrador ingresa los datos requeridos</td>
    <td>Paso 4: el sistema registra la distribución de las obras</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">---</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha cargado la distribución semanal de las obras con sus salas y horarios para su visualización en la grilla de funciones disponibles</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Pagar con Tarjeta</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de realizaciónl pago de una entrada con tarjeta de crédito</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario del sistema, Servidor externo del Banco</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se deben haber ejecutado los CU "Comprar entrada vía web", "Comprar entrada personalmente" o "Retirar entradas reservadas"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el usuario ingresa los datos requeridos</td>
    <td>Paso 1: el sistema solicita número de tarjeta, vencimiento y código de seguridad</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo acepta la conexión y solicita número de tarjeta, vencimiento y código de seguridad</td>
    <td>Paso 3: el sistema solicita conexión con servidor externo del banco</td>
  </tr>
  <tr>
    <td>Paso 6: el servidor externo valida datos de la tarjeta y fondos suficientes</td>
    <td>Paso 5: el sistema envía datos solicitados</td>
  </tr>
  <tr>
    <td>Paso 7: el servidor externo retorna el resultado</td>
    <td>Paso 8: el sistema recibe resultado de validación de datos de la tarjeta</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema recibe resultados de validación de fondos suficientes</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema registra el pago la conexión con el servidor externo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 3 alternativo: falla la conexión con el servidor externo. Se notifica. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 8 alternativo: validación de datos incorrecta. Se informa. Fin de CU.</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: fondos insuficientes. Se informa. Fin de CU.</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado el pago realizado a través de la tarjeta</td>
  </tr>
</table>

#### (7) Préstamos Personales

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Solicitar préstamo</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el pedido de un préstamo personal por parte de un cliente a través de la web del banco</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente está autenticado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de pedir préstamo personal en la web</td>
    <td>Paso 2: el sistema solicita motivo del préstamo, la cuenta a la que se le descontará automáticamente la cuota y el monto del préstamo</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente ingresa los datos requeridos</td>
    <td>Paso 4: el sistema verifica la cantidad de préstamos activos del cliente</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica el monto del préstamo indicado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: se ejecuta CU "Verificar deuda"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema comprueba el resultado de la verificación de deuda</td>
  </tr>
  <td></td>
    <td>Paso 8: el sistema registra el préstamo. Genera identificador del préstamo, código de verificación y comprobante con los datos del préstamo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el cliente posee 3 préstamos activos. Se informa que el préstamo no puede ser otorgado por exceder cantidad de préstamos activos permitida. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: el monto del préstamo es superior a $30.000. Se informa que el monto indicado excede el límite permitido. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: No se ha realizado la verificación. Se notifica error durante la verificación. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 7 alternativo: la verificación indica que el cliente es deudor. Se informa que el préstamo no puede ser otorgado ya que el cliente es deudor. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>El préstamo ha sido registrado. Se generaron identificador, comprobante y código de verificación del préstamo</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Verificar deuda</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe el proceso de conexión con el Veraz y la comprobación de deudas de un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo (Veraz)</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Solicitar préstamo"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el servidor externo establece conexión inicial y solicita código de seguridad</td>
    <td>Paso 1: el sistema solicita conexión con el servidor externo</td>    
  </tr>
  <tr>
    <td>Paso 4: el servidor externo recibe código de seguridad y acepta la conexión</td>
    <td>Paso 3: el sistema envía código de seguridad para validar identidad</td>
  </tr>
  <tr>
    <td>Paso 5: el servidor externo solicita nombre, apellido y CUIT/CUIL de la persona a verificar</td>
    <td>Paso 6: el sistema envía nombre, apellido y CUIT/CUIL de la persona</td>
  </tr>
  <tr>
    <td>Paso 7: el servidor externo valida los datos de la persona</td>
    <td>Paso 9: el sistema recibe resultado de validación de deudas de la persona</td>
  </tr>
  <tr>
    <td>Paso 8: el servidor externo retorna resultado de validación</td>
    <td>Paso 10: el sistema registra resultado de validación y cierra conexión con servidor externo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 1 alternativo: falla la conexión con el servidor externo. Se notifica error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 3 alternativo: conexión con servidor externo no establecida por código incorrecto. Se notifica error en la conexión por código de segutidad incorrecto. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: no fue posible verificar los datos enviados. Se informa error datos envíados no han podido ser verificados. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha recibido resultado de verificación de deudas de la persona cuyos datos fueron enviados</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Adelantar cuotas</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el pago simultáneo de varias cuotas de un préstamo por parte de un cliente para adelantarlas</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente debe estar autenticado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de adelantar cuotas</td>
    <td>Paso 2: el sistema muestra listado de préstamos vigentes del cliente</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente selecciona el préstamo que desea pagar</td>
    <td>Paso 4: el sistema verifica meses transcurridos desde el otorgamiento del préstamo</td>
  </tr>
  <tr>
    <td>Paso 6: el cliente ingresa el dato solicitado</td>
    <td>Paso 5: el sistema solicita cantidad de cuotas a pagar</td>
  </tr>
  <tr>
    <td>Paso 8: el cliente selecciona la cuenta desde la cual abonar</td>
    <td>Paso 7: el sistema muestra listado de cuentas del cliente</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema verifica saldo de la cuenta del cliente</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema descuenta monto requerido de la cuenta del cliente y registra pago de las cuotas indicadas</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: se detiene proceso de adelantar cuotas por requisito no cumplido. Se informa que se pueden adelantar cuotas a partir del sexto mes de otorgado el préstamo. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 9 alternativo: fondos insuficientes. Se informa fondos insuficientes en la cuenta. Se retoma paso 7</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado pago de las cuotas seleccionadas y el monto se ha descontado de la cuenta especificada por el cliente</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cancelar préstamo</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe proceso de pago total de préstamo por parte de un cliente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de cancelar préstamo</td>
    <td>Paso 2: el sistema solicita DNI para verificar identidad</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente ingresa dato requerido</td>
    <td>Paso 4: el sistema verifica DNI ingresado</td>
  </tr>
  <tr>
    <td>Paso 6: el cliente selecciona el préstamo a cancelar</td>
    <td>Paso 5: el sistema lista los préstamos vigentes del cliente</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema verifica cantidad de meses desde el otorgamiento del préstamo</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema verifica fondos de la cuenta asociada</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema registra la cancelación del préstamo y emite comprobante con los datos de la operación</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el DNI ingresado no corresponde a un cliente del banco. Se informa. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 7 alternativo: se interrumpe cancelación del préstamo. Se informa que los préstamos pueden cancelarse a partir de los 9 meses de otorgado. Se retoma paso 5</td>
  </tr>
  <tr>
    <td colspan="2">Paso 8 alternativo: fondos insuficientes. Se informa que el pago no se ha podido realizar por fondos insuficientes. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado cancelación del préstamo y se emitió comprobante de la operación</td>
  </tr>
</table>

#### (8) Pago de impuestos y servicios

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cobrar pagos</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe el cobro de los pagos de impuestos y servicios por parte de un empleado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de cobro de pago</td>
    <td>Paso 2: el sistema solicita código de pago</td>    
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa el dato requerido</td>
    <td>Paso 4: se ejecuta CU "Conectarse a central de cobros"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica los vencimientos de la factura</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: si la factura no está vencida</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 6.1: se muestra el monto original a cobrar</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: si el 1er vencimiento de la factura está vencido</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 7.1: se muestra el monto original más recargo</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema registra la factura como pagada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4: la conexión con la central no se ha realizado. Se informa el error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5: 2do vencimiento de la factura vencido. Se informa que la factura no puede cobrarse porque ya está vencida. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado el cobro del pago de la factura</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar pagos</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe proceso de registro de de pagos en la central de cobros</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Gerente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el gerente selecciona la opción de registrar pagos</td>
    <td>Paso 2: el sistema solicita clave maestra</td>    
  </tr>
  <tr>
    <td>Paso 3: el gerente ingresa el dato requerido</td>
    <td>Paso 4: el sistema verifica clave maestra</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema recupera transacciones cobradas en el día</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: se ejecuta CU "Conectarse con central de cobros"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra los pagos como enviados</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: clave maestra incorrecta. Se informa. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: los pagos se encuentra registrados como enviados. Se informa que es posible enviar la información de los pagos a la central de cobros una única vez en el día. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: la conexión no se ha realizado. Se informa error. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se han registrado las transacciones como enviadas a la central de cobro</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Conectarse a central de cobros</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de conexión al servidor externo de la central de cobros</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo (central de cobros)</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se deben haber ejecutado el CU "Cobrar pagos" o "Registrar pagos"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el servidor externo establece conexión inicial y solicita token</td>
    <td>Paso 1: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 4: el servidor externo recibe el token y lo valida</td>
    <td>Paso 3: el sistema envía el token</td>
  </tr>
  <tr>
    <td>Paso 5: el servidor externo retorna estado de la conexión</td>
    <td>Paso 6: el sistema recibe estado de la conexión</td>
  </tr>
  <tr>
    <td>Paso 8: la central recibe requerimiento y retorna resultado del requerimiento pedido</td>
    <td>Paso 7: el sistema envía el requerimiento solicitado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 9: el sistema recibe resultado del requerimiento</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 10: el sistema registra resultado del requerimiento</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 1 alternativo: error en la conexión con el servidor externo. Se informa el error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: conexión con el servidor externo no establecida por token incorrecto. Se informa el error. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado resultado retornado por la central de cobros acerca del requerimiento solicitado</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Ver estadísticas cobros</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe proceso de visualización de las estadísticas de los cobros realizados, por parte del gerente</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Gerente</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el gerente selecciona la opción de ver estadísticas de cobros</td>
    <td>Paso 2: el sistema solicita clave maestra</td>
  </tr>
  <tr>
    <td>Paso 3: el gerente ingresa el dato solicitado</td>
    <td>Paso 4: el sistema valida clave maestra</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema solicita rango de fechas</td>
  </tr>
  <tr>
    <td>Paso 6: el gerente ingresa el dato solicitado</td>
    <td>Paso 7: el sistema muestra los montos y cantidad de cobros realizados, agrupados por empresa</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: clave maestra incorrecta. Se informa que la clave maestra ingresada es incorrecta. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se han listado los montos y cantidad de cobros realizados</td>
  </tr>
</table>

#### (9) Un Aventón

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar usuario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de creación y registro de una nueva cuenta de usuario</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario no registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario no registrado selecciona la opción de registrarse</td>
    <td>Paso 2: el sistema solicita nombre de usuario, correo electrónico y contraseña</td>
  </tr>
  <tr>
    <td>Paso 3: el usuario no registrado ingresa los datos solicitados</td>
    <td>Paso 4: el sistema verifica que no exista otra cuenta con el mismo correo electrónico</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra del alta del nuevo usuario</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: ya existe otro usuario con el mismo correo electrónico. Se informa. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se creó una nueva cuenta de usuario</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Iniciar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe el proceso de inicio de sesión por parte de un usuario con usuario y contraseña</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Parte 1: el usuario registrado selecciona la opción de iniciar sesión</td>
    <td>Parte 2: el sistema solicita nombre de usuario y contraseña</td>
  </tr>
  <tr>
    <td>Paso 3: el usuario registrado ingresa los datos requeridos</td>
    <td>Paso 4: el sistema valida las credenciales ingresadas</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema inicia la sesión y habilita las funcionalidades del usuario registrado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4: el nombre de usuario o la contraseña no son válidas. Se notifica discrepancia. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión del usuario ha sido iniciada y se han habilitado las funcionalidades de usuario registrado</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cerrar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Se describe el proceso de cierre de sesión por parte de un usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario registrado selecciona la opción de cerrar sesión</td>
    <td>Paso 2: el sistema solicita la confirmación del cierre de sesión</td>    
  </tr>
  <tr>
    <td>Paso 3: el usuario registrado confirma la operación</td>
    <td>Paso 4: el sistema efectúa el cierre de sesión y deshabilita las funcionalidades de usuario registrado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>La sesión ha sido cerrada, las funciones de usuario registrado deshabilitadas y se eliminaron los datos de la sesión</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Dar de alta viaje</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Especifica el proceso de carga de un nuevo viaje por parte de un usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario registrado selecciona la opción de nuevo viaje</td>
    <td>Paso 2: el sistema verifica si el usuario adeuda calificaciones</td>    
  </tr>
  <tr>
    <td>Paso 4: el usuario registrado ingresa los datos solicitados</td>
    <td>Paso 3: el sistema solicita fecha, hora y automóvil que se utilizará en el viaje</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica que el nuevo viaje no se superponga con un viaje ya publicado por el usuario</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: se registra el nuevo viaje y se lista en las opciones de viajes disponibles</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 2 alternativo: el usuario adeuda calificaciones. Se informa que no se pueden publicar viajes si el usuario adeuda calificaciones de otros viajes. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5: la fecha y hora del nuevo viaje se superpone con otro viaje publicado por el usuario. Se notifica lo sucedido. Se retoma paso 3</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado el alta de un nuevo viaje y se ha listado como viaje disponible a postularse</td>
  </tr>
</table>


___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Postular a viaje</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso por el cual un usuario registrado se ofrece como candidato a participar en un viaje publicado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario registrado selecciona la opción de postularse a viaje</td>
    <td>Paso 2: el sistema muestra los viajes disponibles</td>    
  </tr>
  <tr>
    <td>Paso 3: el usuario selecciona un viaje y presiona postularse</td>
    <td>Paso 4: el sistema registra la postulación y envía candidatura al usuario que publicó el viaje</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 2 alternativo: no hay viajes disponibles para mostrar al usuario. Se informa que no hay viajes disponibles. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado postulación y enviado al usuario que publicó el viaje</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Aceptar o rechazar candidato</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso por el cual un usuario registrado elige aceptar o rechazar a un usuario que se ha postulado a participar en su viaje</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario registrado selecciona la opción de ver candidatos sobre el viaje elegido</td>
    <td>Paso 2: el sistema muestra candidatos al viaje elegido</td>    
  </tr>
  <tr>
    <td>Paso 3: el usuario registrado selecciona un usuario y presiona para aceptar o rechazar</td>
    <td>Paso 4: si el candidato fue aceptado</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 4.1: el sistema registra al usuario candidato en el viaje, lo elimina de la lista de candidatos y le notifica</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: si el candidato fue rechazado</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 5.1: el sistema elimina el candidato de la lista de candidatos y le notifica</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 2 alternativo: no hay candidatos al viaje elegido. Se notifica situación. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha determinado la aceptación o rechazo del usuario candidato acerca de su participación en el viaje publicado</td>
  </tr>
</table>


___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Calificar usuario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Especifica proceso de calificación de un usuario dueño de viaje a sus usuarios copilotos y viceversa</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El usuario debe tener una sesión iniciada y haber participado de un viaje ya finalizado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario registrado selecciona la opción de calificar usuario en el viaje elegido</td>
    <td>Paso 2: el sistema muestra los usuarios participantes del viaje</td>    
  </tr>
  <tr>
    <td>Paso 3: el usuario registrado selecciona un usuario participante del viaje</td>
    <td>Paso 4: el sistema solicita calificación</td>
  </tr>
  <tr>
    <td>Paso 5: el usuario registrado envía calificación</td>
    <td>Paso 6: si la calificación es positiva</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 6.1: se suma un punto de reputación al usuario calificado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: si la calificación es negativa</td>
  </tr>
  <tr>
    <td></td>
    <td>- Paso 7.1: se resta un punto de reputación al usuario calificado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema registra que el usuario ha calificado en el viaje elegido</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado calificación del usuario y se ha modificado reputación de los usuario calificados</td>
  </tr>
</table>

#### (10) Gimnasio

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar usuario</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Especifica el proceso de alta de un nuevo usuario en el sistema</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Usuario no registrado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el usuario no registrado selecciona la opción de registrar cuenta</td>
    <td>Paso 2: el sistema solicita dni, nombre, apellido y mail</td>
  </tr>
  <tr>
    <td>Paso 3: el usuario ingresa los datos requeridos</td>
    <td>Paso 4: el sistema verifica que no exista otra cuenta con el mismo mail</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra al usuario, genera una contraseña y la envía al correo indicado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el mail ya está en uso por una cuenta existente. Se informa la situación. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha dado de alta una nueva cuenta de usuario</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Iniciar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de inicio de una sesión por parte de un cliente del gimnasio, ya registrado en el sistema</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de iniciar sesión</td>
    <td>Paso 2: el sistema solicita mail y contraseña</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente ingresa los datos solicitados</td>
    <td>Paso 4: el sistema verifica las credenciales indicadas</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra el inicio de sesión y habilita las funcionalidades del cliente del gimnasio</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el mail o contraseña no es correcto. Se informa situación. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha iniciado una sesión y se han habilitado las funcionalidades de cliente del gimnasio</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cerrar sesión</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el cierre de una sesión activa por parte de un cliente del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de cerrar sesión</td>
    <td>Paso 2: el sistema solicita confirmación del cliente</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente confirma la operación</td>
    <td>Paso 4: el sistema cierra la sesión y deshabilita las funcionalidades de cliente del gimnasio</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha cerrado la sesión del cliente, se han deshabilitados las funcionalidades pertinentes y se han eliminado los datos de la sesión</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Solicitar turno</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de reserva de un turno para una actividad del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Cliente del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>El cliente debe tener una sesión iniciada</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el cliente selecciona la opción de solicitar turno</td>
    <td>Paso 2: el sistema solicita fecha, hora y actividad a realizar</td>    
  </tr>
  <tr>
    <td>Paso 3: el cliente ingresa los datos solicitados</td>
    <td>Paso 4: el sistema verifica cupo de la actividad en el día y horario especificados</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra el turno e informa al usuario</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: no hay cupo para la actividad indicada en el día y horario especificado. Se notifica cupo no disponible. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado un turno para la actividad indicada en el día y horario especificados</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Registrar llegada</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de registro de asistencia de un cliente al turno reservado</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Secretaria del gimnasio</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: la secretaria selecciona la opción de registrar asistencia</td>
    <td>Paso 2: el sistema solicita DNI del cliente</td>
  </tr>
  <tr>
    <td>Paso 3: la secretaria ingresa el dato solicitado</td>
    <td>Paso 4: el sistema verifica actividad reservada por el cliente</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: se ejecuta CU "Sumar puntos"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: el sistema registra asistencia del cliente al turno reservado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el cliente no tiene un turno para la actividad en el corriente día y horario. Se informa situación. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5: la suma de puntos no se realiza. Se notifica error. Se retoma paso 2</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado la llegada del cliente al turno previamente reservado</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Sumar puntos</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de conexión y suma de puntos de cliente a través de un sistema externo</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecutado el CU "Registrar llegada"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el servidor externo acepta la conexión y solicita dni del cliente y actividad a realizar</td>
    <td>Paso 1: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 4: el servidor externo recibe los datos y los valida</td>
    <td>Paso 3: el sistema envía los datos requeridos</td>
  </tr>
  <tr>
    <td>Paso 5: el servidor externo retorna resultado de operación de suma de puntos</td>
    <td>Paso 6: el sistema recibe resultado de operación de suma de puntos</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra resultado de la operación y cierra la conexión con el servidor externo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 1 alternativo: falla la conexión con el servidor externo. Se informa el error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: ocurrió error durante la suma de puntos. Se informa el error. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se registró la suma de puntos del cliente</td>
  </tr>
</table>

#### (11) Carga de empleados

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Cargar empleado</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de carga de un nuevo empleado contratado en el sistema por parte de la secretaria de recursos humanos</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Secretaria de recursos humanos</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td></td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: la secretaria selecciona la opción de cargar empleado</td>
    <td>Paso 2: el sistema solicita DNI, apellido, nombre, edad y domicilio del empleado</td>    
  </tr>
  <tr>
    <td>Paso 3: la secretaria ingresa los datos solicidatos</td>
    <td>Paso 4: el sistema verifica que el empleado no forme parte de la base de sumariados</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema registra la carga del empleado</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el empleado forma parte de la base de sumariados. Se informa la situación y se cancela la carga. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se han registrado los datos personales y se ha dado de alta al empleado en el sistema</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Asociar obra social</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Especifica el proceso de vinculación de un empleado con una obra social, gestionado por una secretaria de recursos humanos</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Secretaria de recursos humanos</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: la secretaria selecciona la opción de asociar obra social</td>
    <td>Paso 2: el sistema solicita DNI del empleado</td>    
  </tr>
  <tr>
    <td>Paso 3: la secretaria ingresa el dato requerido</td>
    <td>Paso 4: el sistema valida DNI del empleado</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: se ejecuta CU "Consultar morosidad"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: el sistema verifica resultado de la consulta de morosidad</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra la asociación con la obra social e imprime un carnet</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el DNI no corresponde a un empleado registrado. Se notifica situación. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: no se ha podido consultar la morosidad. Se informa error en la consulta de morosidad. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: el empleado es moroso. Se informa situación y se imprime código de inicio de trámite. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado la asociación del empleado con la obra social</td>
  </tr>
</table>

___

<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Avisar regularización deuda</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso por el cual el empleado registra la regularización de la deuda con su obra social</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Empleado</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>---</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 1: el empleado selecciona la opción de avisar regularización de deuda</td>
    <td>Paso 2: el sistema solicita DNI y código de inicio de trámite</td>
  </tr>
  <tr>
    <td>Paso 3: el empleado ingresa los datos solicitados</td>
    <td>Paso 4: el sistema verifica DNI</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 5: el sistema verifica código de inicio de trámite</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 6: se ejecuta CU "Consultar morosidad"</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema verifica resultado de la consulta de morosidad</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 8: el sistema registra registra asociación con obra social e imprime un carnet</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 4 alternativo: el DNI no corresponde a un empleado registrado en el sistema. Se informa situación. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 5 alternativo: el código de inicio de trámite no corresponde a un código válido. Se informa que el código de inicio de trámite no es válido. Se retoma paso 2</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: no se ha realizado la consulta de morosidad. Se informa error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 7 alternativo: el empleado es moroso. Se informa error en la regularización de deuda. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha avisado regularización de deuda y se ha registrado obra social del empleado</td>
  </tr>
</table>

___
<table>
  <tr>
    <td><strong>Nombre del caso de uso:</strong></td>
    <td>Consultar morosidad</td>
  </tr>
  <tr>
    <td><strong>Descripción:</strong></td>
    <td>Describe el proceso de conexión y consulta de morosidad con servidor externo de obra social</td>
  </tr>
  <tr>
    <td><strong>Actores:</strong></td>
    <td>Servidor externo de obra social</td>
  </tr>
  <tr>
    <td><strong>Precondiciones:</strong></td>
    <td>Se debe haber ejecuta el CU "Asociar obra social" o "Avisar regularización deuda"</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Normal:</strong></td>
  </tr>
  <tr>
    <td><strong>Acción del Actor</strong></td>
    <td><strong>Acciones del Sistema</strong></td>
  </tr>
  <tr>
    <td>Paso 2: el servidor externo acepta conexión y solicita DNI del empleado</td>
    <td>Paso 1: el sistema solicita conexión con el servidor externo</td>
  </tr>
  <tr>
    <td>Paso 4: el servidor externo valida DNI y situación de morosidad del empleado</td>
    <td>Paso 3: el sistema envía dato solicitado</td>
  </tr>
  <tr>
    <td>Paso 5: el servidor externo envía resultado de consulta de morosidad</td>
    <td>Paso 6: el sistema recibe resultado de consulta de morosidad</td>
  </tr>
  <tr>
    <td></td>
    <td>Paso 7: el sistema registra resultado de consulta de morosidad y cierra la conexión con el servidor externo</td>
  </tr>
  <tr>
    <td colspan="2"><strong>Curso Alterno:</strong></td>
  </tr>
  <tr>
    <td colspan="2">Paso 1 alternativo: falla la conexión con el servidor externo. Se informa error. Fin de CU</td>
  </tr>
  <tr>
    <td colspan="2">Paso 6 alternativo: resultado inválido por error producido durante la consulta de morosidad. Se informa error. Fin de CU</td>
  </tr>
  <tr>
    <td><strong>Postcondición:</strong></td>
    <td>Se ha registrado el resultado de la consulta de morosidad del empleado</td>
  </tr>
</table>