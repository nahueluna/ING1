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