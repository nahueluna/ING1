# Trabajo Práctico 2

## Problema 1: Alquiler de mobiliario

**Roles de usuarios**
- Propietario
- Arrendatario (persona que alquila)

**Historias de usuario**
- Dar de alta mobiliario
- Realizar reserva
- Pagar con tarjeta

___

**ID**: Dar de alta mobiliario

**Título**: Como propietario quiero cargar mobiliario para que sea alquilado

**Reglas de negocio**:
- No pueden existir códigos repetidos
- El precio debe cargarse en dólares
- El usuario debe autenticarse

**Criterios de aceptación**:

*Escenario 1:* Alta exitosa

    Dado que el usuario "Pedro" con código de inmueble "1234" esté autenticado y posee los datos requeridos
    Cuando el propietario carga los datos del inmueble "1234" y presiona "subir"
    Entonces el inmueble es dado de alta con éxito

*Escenario 2:* Alta fallida por código repetido

    Dado que el código de inmueble "1234" se encuentra subido.
    Cuando el usuario carga los datos del inmueble "1234" y presiona "subir".
    Entonces el sistema notifica que el inmueble ya está cargado.

*Escenario 3:* Alta fallida por usuario no autenticado

    Dado el usuario "Pedro" quien no está autenticado.
    Cuando "Pedro" carga los datos del inmueble y presiona "subir".
    Entonces el sistema notifica que el usuario no está autenticado.

___

**ID**: Realizar reserva

**Título**: Como usuario quiero realizar reserva de inmueble para alquilarlo

**Reglas de negocio**:
- Debe incluir 3 muebles
- Hay disponibilidad
- Debe abonar 20% del total

**Criterios de aceptación**:

*Escenario 1:* Reserva exitosa

    Dado que la reserva del inmueble "1234" incluye un mínimo de 3 muebles, está disponible y las condiciones de pago son las adecuadas.
    Cuando el usuario escoge el inmueble "1234" y presiona "reservar".
    Entonces la reserva es realizada con éxito y el sistema emite el número de reserva.

*Escenario 2:* Reserva fallida por no incluir mínimo de muebles

    Dado que la reserva del inmueble "1234" figura disponible, e incluye 2 muebles.
    Cuando el usuario escoge el inmueble "1234" y presiona "reservar".
    Entonces el sistema notifica que cantidad mínima de muebles no está incluida.

*Escenario 3:* Reserva fallida por falta de disponibilidad

    Dado que la reserva del inmueble "1234" incluye un mínimo de 3 muebles y figura no disponible.
    Cuando el usuario escoge el inmueble "1234" y presiona "reservar".
    Entonces el sistema notifica que el inmueble no está disponible.

*Escenario 4:* Reserva fallida por abono inferior al 20% del total

    Dado que la reserva del inmueble "1234" incluye un mínimo de 3 muebles, está disponible y realiza un abono inferior al 20%.
    Cuando el usuario escoge el inmueble "1234" y presiona "resevar".
    Entonces el sistema notifica que el abono de 20% del total requerido no es satisfecho.

*Escenario 5:* Reserva fallida por error en el pago

    Dado la reserva del inmueble "1234" cumple los pertinentes requisitos y las condiciones no son las adecuadas para un pago exitoso.
    Cuando el usuario escoge el inmueble "1234" y presiona "reservar".
    Entonces el sistema redirige al usuario hacia la ventana de pago, espera respuesta y notifica que ha ocurrido un error con el pago.

___

**ID**: Pagar con tarjeta

**Título**: Como usuario quiero pagar con tarjeta para poder reservar un inmueble

**Reglas de negocio**:
- Solo se acepta tarjeta de crédito

**Criterios de aceptación**:

*Escenario 1:* Pago con tarjeta realizado exitosamente.

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y la tarjeta tiene saldo suficiente.
    Cuando el usuario ingresa el número de tarjeta "3456" y presiona "pagar".
    Entonces el sistema registra el pago y retorna un resultado exitoso.

*Escenario 2:* Pago fallido por tarjeta de crédito inexistente

    Dado que la conexión con el servidor del banco es exitosa y el número "3456" no corresponde a un número de tarjeta de crédito.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por número de tarjeta de crédito no válido.

*Escenario 3:* Pago fallido por saldo insuficiente 

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y no posee saldo suficiente para la reserva.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por saldo insuficiente.

*Escenario 4:* Pago fallido por error del servidor del banco.

    Dado que la conexión con el servidor del banco es fallida.
    Cuando el usuario ingresa un número de tarjeta de crédito y presiona "pagar".
    Entonces el sistema retorna un error por conexión fallida.


## Problema 2: Posgrado

**Roles de usuarios**
- Empleado administrativo (carga las carreras)
- Alumno

**Historias de usuario**
- Cargar carrera
- Registrar cuenta de alumno
- Inscribirse a carrera
- Pagar con tarjeta

___

**ID**: Cargar carrera

**Título**: Como empleado administrativo quiero cargar las carreras para que estén disponibles para inscripciones

**Reglas de negocio**:
- El nombre de carrera no puede repetirse
- La duración máxima de la carrera es de 5 años

**Criterios de aceptación**:

*Escenario 1:* Carga de carrera exitosa.

    Dada la carrera "Doctorado en Ciencias Informáticas", cuyo nombre no está registrado y posee una duración igual o menor a 5 años.
    Cuando el empleado administrativo ingresa los datos de la carrera "Doctorado en Ciencias Informáticas" y presiona cargar.
    Entonces la carga se realiza satisfactoriamente.

*Escenario 2:* Carga fallida por nombre de carrera existente.

    Dada la carrera "Doctorado en Ciencias Informáticas", cuyo nombre ya se encuentra registrado.
    Cuando el empleado administrativo ingresa los datos de la carrera "Doctorado en Ciencias Informáticas" y presiona cargar.
    Entonces el sistema impide la carga e informa que el nombre ya se encuentra registrado.

*Escenario 3:* Carga fallida por duración de carrera no válida.

    Dada la carrera "Doctorado en Ciencias Informáticas", cuyo nombre no está registrado y su duración es superior a 5 años.
    Cuando el empleado administrativo ingresa los datos de la carrera "Doctorado en Ciencias Informáticas" y presiona cargar.
    Entonces el sistema impide la carga e informa que la duración de la carrera excede el máximo permitido.

___

**ID:** Registrar cuenta de alumno

**Título**: Como alumno quiero registrarme en el sistema para poder inscribirme a una carrera.

**Reglas de negocio**:
- El nombre de usuario no puede repetirse
- La contraseña debe tener más de 6 dígitos

**Criterios de aceptación**:

*Escenario 1:* Registro exitoso.

    Dado el nombre de usuario "nahuel" que no existe en el sistema y la contraseña "1234567" mayor a 6 dígitos.
    Cuando el alumno ingresa el nombre de usuario "nahuel", la contraseña "1234567" y presiona registrarse.
    Entonces el sistema indica que el alumno se registró con éxito.

*Escenario 2:* Registro fallido por nombre de usuario existente.

    Dado el nombre de usuario "nahuel" que ya existe en el sistema.
    Cuando el alumno ingresa el nombre de usuario "nahuel", una contraseña y presiona registrarse.
    Entonces el sistema impide el registro e informa que el nombre de usuario ya se encuentra registrado.

*Escenario 3:* Registro fallido por contraseña que incumple requistos.

    Dado un nombre de usuario que no se encuentra registrado y la contraseña "123456" que no cumple condición de más de 6 dígitos.
    Cuando el alumno ingresa su nombre de usuario, la contraseña "123456" y presiona registrarse.
    Entonces el sistema impide el registro e informa que la contraseña debe poseer un largo mayor a 6 dígitos.

___

**ID**: Inscribirse a carrera

**Título:** Como alumno quiero inscribirme a una carrera para obtener mayor conocimiento.

**Reglas de negocio**:
- El usuario debe estar autenticado
- La cantidad de cuotas no puede exceder el máximo especificado

**Criterios de aceptación**:

*Escenario 1:* Inscripción exitosa

    Dado el alumno "Nahuel" que se encuentra autenticado, su pago se realizará en un número de cuotas menor o igual al máximo y las condiciones de pago son las adecuadas.
    Cuando el alumno "Nahuel" selecciona la carrera y cantidad de cuotas, y presiona inscribirse.
    Entonces el sistema redirecciona a la ventana de pago, espera respuesta y emite comprobantes de inscripción y pago, informando que el proceso finalizó con éxito.

*Escenario 2:* Inscripción fallida por usuario no autenticado.

    Dado el alumno "Nahuel" que no ha iniciado sesión.
    Cuando el alumno "Nahuel" selecciona la carrera y demás requisitos, y presiona inscribirse.
    Entonces el sistema impide la inscripción y notifica que el usuario no se ha autenticado.

*Escenario 3:* Inscripción fallida por cantidad de cuotas incorrecta.

    Dado el alumno "Nahuel" que se encuentra autenticado y su pago se realizará en un número de cuotas superior a la permitida.
    Cuando el alumno "Nahuel" selecciona la carrera y cantidad de cuotas, y presiona inscribirse.
    Entonces el sistema impide la inscripción e informa que la cantidad de cuotas seleccionada supera el máximo permitido.

*Escenario 4:* Inscripción fallida por error en el pago.

    Dado el alumno "Nahuel" que se encuentra autenticado, su pago se realizará en un número de cuotas menor o igual al máximo y las condiciones de pago no son las adecuadas para un pago exitoso.
    Cuando el alumno "Nahuel" selecciona la carrera y cantidad de cuotas, y presiona inscribirse.
    Entonces el sistema redirecciona a la ventana de pago, espera respuesta e informa que hubo un problema con el pago.

___

**ID**: Pagar con tarjeta

**Título**: Como usuario quiero pagar con tarjeta para poder reservar un inmueble

**Reglas de negocio**:
- Solo se acepta tarjeta de crédito

**Criterios de aceptación**:

*Escenario 1:* Pago con tarjeta realizado exitosamente.

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y la tarjeta tiene saldo suficiente.
    Cuando el usuario ingresa el número de tarjeta "3456" y presiona "pagar".
    Entonces el sistema registra el pago y retorna un resultado exitoso.

*Escenario 2:* Pago fallido por tarjeta de crédito inexistente

    Dado que la conexión con el servidor del banco es exitosa y el número "3456" no corresponde a un número de tarjeta de crédito.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por número de tarjeta de crédito no válido.

*Escenario 3:* Pago fallido por saldo insuficiente 

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y no posee saldo suficiente para la reserva.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por saldo insuficiente.

*Escenario 4:* Pago fallido por error del servidor del banco.

    Dado que la conexión con el servidor del banco es fallida.
    Cuando el usuario ingresa un número de tarjeta de crédito y presiona "pagar".
    Entonces el sistema retorna un error por conexión fallida.

## Problema 3: Contratos

**Roles de usuarios**
- Empleado de mesa de entradas
- Empleado de rendiciones

**Historias de usuario**
- Realizar minuta
- Aprobar minuta
- ~~Verificar CUIT con AFIP~~ (el que interactúa es el sistema)
- Imprimir listado de minutas aprobadas


___

**ID**: Realizar minuta

**Título**: Como empleado de mesa de entradas quiero realizar minuta para que sea evaluada por el empleado de rendiciones

**Reglas de negocio**:
- Los montos no pueden superar los $25.000
- La duración debe ser de un máximo de 6 meses

**Criterios de aprobación**:

*Escenario 1:* Minuta realizada exitosamente.

    Dada la minuta de monto "$20.000" y una duración de "3 meses", a cargo de un empleado de mesa de entradas.
    Cuando el empleado ingresa el monto de "$20.000", la duración de "3 meses" y demás datos requeridos, y presiona generar minuta.
    Entonces el sistema realiza la minuta exitosamente, le asocia un número automáticamente y la deja pendiente de aprobación.

*Escenario 2:* Confección de minuta fallida por monto excesivo.

    Dada la minuta de monto "$28.000" y una duración de "3 meses", a cargo de un empleado de mesa de entradas.
    Cuando el empleado ingresa el monto de "$28.000", la duración de "3 meses" y demás datos requeridos, y presiona generar minuta.
    Entonces el sistema impide la realización de la minuta e informa que el monto indicado supera el máximo permitido por la vigente reglamentación.

*Escenario 3:* Confección de minuta fallida por duración excesiva.

    Dada la minuta de monto "$20.000" y una duración de "8 meses", a cargo de un empleado de mesa de entradas.
    Cuando el empleado ingresa el monto de "$20.000", la duración de "8 meses" y demás datos requeridos, y presiona generar minuta.
    Entonces el sistema impide la realización de la minuta e informa que la duración indicada supera el máximo permitido por la vigente reglamentación.

___

**ID**: Aprobar minuta

**Título**: Como empleado de rendiciones quiero aprobar minuta para que la realización de la misma sea efectiva.

**Reglas de negocio**:
- La persona objetivo de la minuta no debe tener 3 contratos vigentes
- El CUIT de la persona objetivo debe estar habilitado por AFIP

**Criterios de aprobación**:

*Escenario 1:* Aprobación de minuta exitosa.

    Dada la minuta "1" cuya confección fue correcta, su persona objetivo posee 2 contratos vigentes y su CUIT "30-68537634-9" está habilitado por AFIP.
    Cuando el empleado de rendiciones ingresa el número de minuta "1" y presiona aprobar.
    Entonces el sistema informa que la minuta se ha aprobado con éxito.

*Escenario 2:* Aprobación de minuta fallida por cantidad máxima de contratos vigentes excedida.

    Dada la minuta "1" cuya confección fue correcta, su persona objetivo posee 3 minutas aprobadas y su CUIT "30-68537634-9" está habilitado por AFIP.
    Cuando el empleado de rendiciones ingresa el número de minuta "1" y presiona aprobar.
    Entonces el sistema impide la aprobación e informa que la persona objetivo de la minuta ya posee 3 contratos vigentes.

*Escenario 3:* Aprobación de minuta fallida por CUIT inhabilitado.

    Dada la minuta "1" cuya confección fue correcta, su persona objetivo posee 2 contratos vigentes y su CUIT "30-68537634-9" se encuentra inhabilitado por AFIP.
    Cuando el empleado de rendiciones ingresa el número de minuta "1" y presiona aprobar.
    Entonces el sistema impide la aprobación e informa que el CUIT se encuentra inhabilitado por AFIP.

*Escenario 4:* Aprobación de minuta fallida por error en servicio AFIP

    Dada la minuta "1" cuya confección fue correcta, su persona objetivo posee 2 contratos vigentes y las condiciones no son las adecuadas para la verificación del CUIT en el servicio de AFIP.
    Cuando el empleado de rendiciones ingresa el número de minuta "1" y presiona aprobar.
    Entonces el sistema impide la aprobación e informa que el ha ocurrido un error al conectarse al servicio de verificación de AFIP.

*Escenario 5:* Aprobación de minuta fallida por CUIT inexistente.

    Dada la minuta "1" cuya confección fue correcta, su persona objetivo posee 2 contratos vigentes y el CUIT "30-68537634-9" no existe.
    Cuando el empleado de rendiciones ingresa el número de minuta "1" y presiona aprobar.
    Entonces el sistema impide la aprobación e informa que el CUIT especificado en la minuta no existe.

___

**ID**: Imprimir listado de minutas aprobadas

**Título**: Como empleado de rendiciones quiero imprimir los listados con las minutas aprobadas para elevarlo al jefe de departamento.

**Reglas de negocio**: (el cliente no indicó ninguna)

**Criterios de aprobación**:

*Escenario 1:* Impresión exitosa

    Dada la lista con las minutas aprobadas "1", "2", y "3", y las condiciones de impresión son las adecuadas.
    Cuando el empleado de rendiciones selecciona la lista de minutas aprobadas "1", "2" y "3", y presiona imprimir.
    Entonces la lista se imprime y el sistema informa que la operación se ha realizado con éxito.

*Escenario 2:* Impresión fallida por error con impresora.

    Dada la lista con las minutas aprobadas "1", "2" y "3", y las condiciones de conexión con la impresora no son las adecuadas.
    Cuando el empleado de rendiciones selecciona la lista de minutas aprobadas "1", "2" y "3", y presiona imprimir.
    Entonces la impresión no se realiza, el sistema informa que ha ocurrido un error al conectarse a la impresora y ofrece opciones para intentar nuevamente.

## Problema 4: Venta de bebidas

**Roles de usuarios**:
- Persona
- Usuario logueado

**Historias de usuario**:
- Registrar persona
- Comprar bebida

___

**ID**: Registrar persona

**Título**: Como persona quiero registrarme en el sistema para comprar bebidas en línea.

**Reglas de negocio**:
- El mail será utilizado como nombre de usuario (debe ser único)
- Solo se permite registrarse a personas mayores a 18 años

**Criterios de aceptación**:

*Escenario 1:* Registro exitoso.

    Dada la persona "Nahuel" con la dirección de email "nahuel@example.com" no registrada, de 20 años.
    Cuando "Nahuel" ingresa el mail "nahuel@example.com", su edad de 20 años y demás datos requeridos, y presiona registrarse.
    Entonces el sistema lo registra exitosamente y genera una contraseña que es envíada a su dirección de email.

*Escenario 2:* Registro fallido por mail existente.

    Dada la persona "Nahuel" con la dirección de email "nahuel@example.com" ya registrada, de 20 años de edad.
    Cuando "Nahuel" ingresa el mail "nahuel@example.com", su edad de 20 años y demás datos requeridos, y presiona registrarse.
    Entonces el sistema impide el registro e informa que la dirección de email utilizada ya se encuentra registrada.

*Escenario 3:* Registro fallido por edad insuficiente.

    Dada la persona "Nahuel" con la dirección de email "nahuel@example.com" no registrada, de 17 años.
    Cuando "Nahuel" ingresa el mail "nahuel@example.com", su edad de 17 años y demás datos requeridos, y presiona registrarse.
    Entonces el sistema impide el registro y muestra en pantalla el texto de la ley que impide la venta de bebidas alcohólicas a menores.

___

**ID**: Comprar bebida 

**Título**: Como usuario logueado quiero comprar bebidas en línea para recibir mis productos.

`nota:` como el sujeto es usuario logueado, no es necesario poner como regla de negocio que se debe iniciar sesión. Además, solo a los usuarios logueados les aparece el catálogo, por lo que no puede haber falla de compra por usuario no registrado.

**Reglas de negocio**:
- Si el usuario es premium recibe 20% de descuento
- Si el monto de la compra es superior a $4500 se recibe 10% de descuento
- Si se dan las condiciones, ambos descuentos deben combinarse

**Criterios de aceptación**:

*Escenario 1:* Compra exitosa con ambos descuentos.

    Dado el mail "nahuel@example.com" que corresponde a una cuenta premium y su monto de compra es de $5000.
    Cuando el usuario con mail "nahuel@example.com" selecciona sus bebidas con monto total de $5000 y presiona comprar.
    Entonces el sistema aplica descuento de 20% por premium, 10% por compra superior a monto indicado, informa el precio en pantalla, espera respuesta y redirige a ventana de pago con éxito.

*Escenario 2:* Compra exitosa con descuento premium.

    Dado el mail "nahuel@example.com" que corresponde a una cuenta premium y su monto de compra es de $3000.
    Cuando el usuario con mail "nahuel@example.com" selecciona sus bebidas con monto total de $3000 y presiona comprar.
    Entonces el sistema aplica descuento de 20% por premium, informa el precio en pantalla, espera respuesta y redirige a ventana de pago con éxito.

*Escenario 3:* Compra exitosa con descuento por compra mayor a monto indicado.

    Dado el mail "nahuel@example.com" que no corresponde a una cuenta premium y su monto de compra es de $5000.
    Cuando el usuario con mail "nahuel@example.com" selecciona sus bebidas con monto total de $5000 y presiona comprar.
    Entonces el sistema aplica descuento de 10% por compra superior a monto indicado, informa el precio en pantalla, espera respuesta y redirige a ventana de pago con éxito.

*Escenario 4:* Compra fallida por falta de stock

    Dado el mail "nahuel@example.com" que selecciona una bebida sin stock.
    Cuando el usuario con mail "nahuel@example.com" selecciona la bebida y presiona comprar.
    Entonces el sistema impide la compra e indica que la bebida seleccionada no posee stock.

## Problema 5: Casa de fotografía

**Roles de usuarios**:
- Persona
- Usuario autenticado
- Empleado

**Historias de usuario**
- Registrar cuenta
- Realizar pedido foto
- Pagar con tarjeta
- Registrar retiro

___

**ID**: Registrar cuenta

**Título**: Como persona quiero registrar cuenta para acceder a servicio de impresión de fotos.

**Reglas de negocio**: (el cliente no indicó ninguna)

**Criterios de aprobación**:

*Escenario 1:* Registro exitoso

    Dado el email "nahuel@example.com" y el nombre de usuario "nahuel" los cuales no se encuentran registrados.
    Cuando se ingresa el email "nahuel@example.com", el nombre de usuario "nahuel" y demás datos requeridos, y se presiona registrar.
    Entonces el sistema indica que la cuenta se ha creado con éxito.

*Escenario 2:* Registro fallido por email existente

    Dado el email "nahuel@example.com" que ya existe en el sistema.
    Cuando se ingresa el email "nahuel@example.com" y demás datos requeridos y se presiona registrar.
    Entonces el sistema impide el registro e indica que el email ya se encuentra registrado.

*Escenario 3:* Registro fallido por nombre de usuario existente

    Dado el nombre de usuario "nahuel" que ya existe en el sistema.
    Cuando se ingresa el nombre de usuario "nahuel" y demás datos requeridos y se presiona registrar.
    Entonces el sistema impide el registro e indica que el nombre de usuario ya se encuentra registrado.

___

**ID**: Realizar pedido foto

**Título**: Como usuario autenticado quiero realizar pedido de fotos para poder imprimirlas y retirarlas.

**Reglas de negocio**:
- Se pueden subir máximo 50 fotos para ser impresas
- Las fotos se ingresan de a una

**Criterios de aceptación**:

*Escenario 1:* Fotos pedidas exitosamente

    Dada la carga de 30 fotos, las cuales son subidas de a una y las condiciones de pago son las adecuadas.
    Cuando las 30 fotos son subidas y se presiona continuar para acceder al pago.
    Entonces se redirige a la ventana de pago, se espera respuesta y se genera código único para retiro de fotos.

*Escenario 2:* Pedido de fotos fallido por exceder máximo permitido.

    Dada la carga de 60 fotos, las cuales son subidas de a una y las condiciones de pago son las adecuadas.
    Cuando se suben 50 fotos y se intenta subir la siguiente.
    Entonces el sistema impide la carga de nuevas fotos e indica que se ha alcanzado el máximo de fotos permitido.

*Escenario 3:* Pedido de fotos fallida por subida simultánea de fotos.

    Dada la carga de 30 fotos, las cuales son subidas de a dos y las condiciones de pago son las adecuadas.
    Cuando se seleccionan las primeras dos fotos para subir de forma simultánea.
    Entonces el sistema impide la carga de la segunda foto e indica que se permite subir una foto por vez.

*Escenario 4*: Pedido de fotos fallida por error en el pago

    Dado el pedido que consta de 30 fotos cargadas, las cuales son subidas de a una y las condiciones de pago no son las adecuadas.
    Cuando las 30 fotos son subidas y se presiona continuar.
    Entonces se redirige a ventana de pago, se espera respuesta e informa que hubo un error en el pago, impidiendo el pedido de las fotos.

___

**ID**: Pagar con tarjeta

**Título**: Como usuario autenticado quiero pagar con tarjeta para abonar mi pedido.

**Reglas de negocio**:
- El pago se realiza con tarjeta de crédito

**Criterios de aceptación**:

*Escenario 1:* Pago con tarjeta realizado exitosamente.

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y la tarjeta tiene saldo suficiente.
    Cuando el usuario ingresa el número de tarjeta "3456" y presiona "pagar".
    Entonces el sistema registra el pago y retorna un resultado exitoso.

*Escenario 2:* Pago fallido por tarjeta de crédito inexistente

    Dado que la conexión con el servidor del banco es exitosa y el número "3456" no corresponde a un número de tarjeta de crédito.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por número de tarjeta de crédito no válido.

*Escenario 3:* Pago fallido por saldo insuficiente 

    Dado que la conexión con el servidor del banco es exitosa, el número "3456" corresponde a una tarjeta de crédito y no posee saldo suficiente para el pedido.
    Cuando el usuario ingresa el número "3456" y presiona "pagar".
    Entonces el sistema retorna un error por saldo insuficiente.

*Escenario 4:* Pago fallido por error del servidor del banco.

    Dado que la conexión con el servidor del banco es fallida.
    Cuando el usuario ingresa un número de tarjeta de crédito y presiona "pagar".
    Entonces el sistema retorna un error por conexión fallida.

___

**ID**: Registrar retiro

**Título**: Como empleado quiero registrar retiro de fotos para asentar que el cliente ya ha recibido su pedido.

**Reglas de negocio**: (no se han especificado)

**Criterios de aprobación**:

*Escenario 1:* Registro de retiro exitoso.

    Dado el código único existente "1234".
    Cuando se ingresa el código único "1234" y demás datos pertenecientes a un pedido.
    Entonces el sistema informa que el retiro del pedido se ha registrado exitosamente.

*Escenario 2:* Registro de retiro fallido por código único no existente.

    Dado el código único no existente "1234".
    Cuando se ingresa el código único "1234" y demás datos pertenecientes a un pedido.
    Entonces el sistema impide el registro e informa que el código único especificado no existe.

## Problema 6: Biblioteca

**Roles de usuario**
- Alumno
- Socio
- Bibliotecaria

**Historias de usuario**
- Registrar libro
- Asociar alumno
- Realizar préstamo
- Suspender socio
- Registrar devolución préstamo

___

**ID**: Registrar libro

**Título**: Como bibliotecaria quiero registrar un libro para realizar inventario.

**Reglas de negocio**:
- Se pueden almacenar varios ejemplares del mismo libro

**Criterios de aprobación**:

*Escenario 1:* Registro exitoso de libro nuevo

    Dado el libro "El Señor de los Anillos", el cual no posee ejemplares registrados.
    Cuando se cargan los datos del libro "El Señor de los Anillos" y se presiona registrar.
    Entonces el libro se registra exitosamente en el sistema con una cantidad de 1.

*Escenario 2:* Registro exitoso de libro existente

    Dado el libro "El Señor de los Anillos", el cual posee 3 ejemplares registrados.
    Cuando se cargan los datos del libro "El Señor de los Anillos" y se presiona registrar.
    Entonces se incrementa en uno la cantidad de ejemplares del libro en el sistema.
    
___

**ID**: Asociar alumno

**Título**: Como alumno quiero asociarme en el sistema para pedir libros.

**Reglas de negocio**: (no se ha especificado. No se tienen en cuenta cuestiones como la falta de DNI o certificado pues es ajeno al sistema).

**Criterios de aceptación**:

*Escenario 1:* Asociación exitosa.

    Dado el DNI "45872921" perteneciente a un alumno regular que no se encuentra registrado en el sistema.
    Cuando el DNI "45872921" es ingresado junto con el certificado y se presiona asociar.
    Entonces el DNI es registrado exitosamente y se genera un número de socio.

*Escenario 2:* Asociación fallida por DNI existente.

    Dado el DNI "45872921" perteneciente a un alumno regular que ya existe en el sistema.
    Cuando el DNI "45872921" es ingresado junto con el certificado y se presiona asociar.
    Entonces el sistema impide el registro e informa que el DNI indicado pertenece a un alumno ya asociado.

*Escenario 3:* Asociación fallida por certificado de alumno regular no válido

    Dado el DNI "45872921" no registrado en el sistema y su certificado de alumno regular el cual no está vigente.
    Cuando el DNI "45872921" es ingresado junto con el certificado y se presiona asociar.
    Entonces el sistema impide el registro e informa que el certificado de alumno regular provisto no es válido.

___

**ID**: Realizar préstamo

**Título**: Como asociado quiero realizar préstamo para acceder al material de lectura.

**Reglas de negocio**:
- El socio no debe estar suspendido
- El socio no debe tener más de 3 préstamos vigentes

**Criterios de aprobación**:

*Escenario 1:* Préstamo exitoso.

    Dado el socio número "33" quien está habilitado, posee 1 préstamo vigente y el libro "El Hobbit" el cual posee 5 ejemplares.
    Cuando el socio número "33" selecciona el libro "El Hobbit" y presiona pedir préstamo.
    Entonces se indica una fecha de devolución, se decrementa en uno la cantidad de ejemplares disponibles, se incrementa en uno la cantidad de préstamos vigentes del socio y se informa que el préstamo se ha realizado exitosamente.

*Escenario 2:* Préstamo fallido por socio suspendido.

    Dado el socio número "33" quien está suspendido, posee 1 préstamo vigente y el libro "El Hobbit" el cual posee 5 ejemplares.
    Cuando el socio número "33" selecciona el libro "El Hobbit" y presiona pedir préstamo.
    Entonces se impide la realización del préstamo y se informa que el socio se encuentra suspendido para pedir libros.

*Escenario 3:* Préstamo fallido por falta de ejemplares.

    Dado el socio número "33" quien está habilitado, posee 1 préstamo vigente y el libro "El Hobbit" el cual posee 0 ejemplares.
    Cuando el socio número "33" selecciona el libro "El Hobbit" y presiona pedir préstamo.
    Entonces se impide la realización del préstamo y se informa que el libro no posee ejemplares para prestar.

*Escenario 4:* Préstamo fallido por cantidad máxima de préstamos vigentes excedida.

    Dado el socio número "33" quien está habilitado, posee 4 préstamos vigentes y el libro "El Hobbit" el cual posee 5 ejemplares.
    Cuando el socio número "33" selecciona el libro "El Hobbit" y presiona pedir préstamo.
    Entonces se impide la realización del préstamo y se informa que el socio ya posee más de 3 préstamos vigentes.

*Escenario 5:* Préstamo fallido por número de socio no existente.

    Dado el socio número "33" quien no existe en el sistema, y el libro "El Hobbit".
    Cuando el socio número "33" selecciona el libro "El Hobbit" y presiona pedir préstamo.
    Entonces se impide la realización del préstamo y se informa que el número de socio no existe en el sistema.
___

**ID**: Suspender socio

**Título**: Como bibliotecaria quiero suspender un socio para evitar que pueda realizar préstamos.

**Reglas de negocio**:
- Es suspendido si posee préstamos vencidos

**Criterios de aceptación**:

*Escenario 1:* Suspensión exitosa.

    Dado el socio número "33" quien posee un préstamo vencido.
    Cuando se ingresa el número de socio "33" y se presiona suspender.
    Entonces el sistema informa que el socio no podrá realizar préstamos por los siguientes 15 días

*Escenario 2:* Suspensión fallida por falta de préstamos vencidos.

    Dado el socio número "33" quien no posee préstamos vencidos.
    Cuando se ingresa el número de socio "33" y se presiona suspender.
    Entonces el sistema impide la suspensión e informa que el socio no tiene ningún préstamo vencido.

___

**ID**: Registrar devolución préstamo

**Título**: Como bibliotecaria quiero registrar la devolución de un préstamo para tener inventario de ejemplares actualizado.

**Reglas de negocio**:
- Libros deteriorados no son prestados nuevamente (decrementa ejemplares)
- Se deja constancia de los préstamos vencidos

**Criterios de aprobación**:

*Escenario 1:* Registro exitoso con libro en buenas condiciones.

    Dado el préstamo del libro "El Hobbit", el cuál no está vencido y su libro se encuentra en buenas condiciones.
    Cuando se registra la devolución del libro "El Hobbit" junto con los datos requeridos.
    Entonces el sistema actualiza historial de préstamos e incrementa ejemplares disponibles del libro.

*Escenario 2:* Registro exitoso con libro deteriorado.

    Dado el préstamo del libro "El Hobbit", el cual no está vencido y su libro se encuentra deteriorado.
    Cuando se registra la devolución del libro "El Hobbit" junto con los datos requeridos.
    Entonces el sistema actualiza historial de préstamos y decrementa cantidad total de ejemplares del libro.

*Escenario 3*: Registro exitoso de préstamo vencido

    Dado el préstamo del libro "El Hobbit" realizado por el socio "33", el cual está vencido.
    Cuando se registra la devolución del libro "El Hobbit" por parte del socio "33" junto con los datos requeridos.
    Entonces el sistema actualiza historial de préstamos y deja constancia de que el socio devolvió un préstamo en calidad de vencido.


## Problema 8: Teatro

**Roles de usuario**:
- Empleado (vendedor de la boletería)
- Usuario (cliente)
- Administrador

**Historias de usuario**:
- Reservar entradas
- Mostrar grilla de funciones disponibles
- Comprar entrada via web
- Comprar entrada personalmente
- Pagar con tarjeta
- Retirar entradas reservadas
- Imprimir entradas compradas
- Cargar distribución de obras

___

**ID**: Reservar entradas

**Título**: Como empleado quiero gestionar reserva de entradas para que el cliente asegure su lugar en la obra.

**Reglas de negocio**:
- Se pueden reservar hasta 2 entradas a la vez

**Criterios de aceptación**:

*Escenario 1:* Reserva exitosa

    Dado el cliente de DNI "45284082" que no posee entradas reservadas y la función de la obra posee disponibilidad.
    Cuando se ingresa la fecha 11/9, la hora 19:00, la obra "El Principito", junto con el nombre "Juan Pérez" y el DNI "45284082" y se presiona reservar.
    Entonces el sistema reserva la entrada vínculada al DNI "45284082" de forma exitosa.

*Escenario 2:* Reserva fallida por cantidad de entradas

    Dado el cliente de DNI "45284082" que posee 2 entradas reservadas y la función de la obra posee disponibilidad.
    Cuando se ingresa la fecha 11/9, la hora 19:00, la obra "El Principito", junto con el nombre "Juan Pérez" y el DNI "45284082" y se presiona reservar.
    Entonces el sistema impide la reserva de la entrada e informa que el cliente posee 2 entradas reservadas.

___

**ID**: Mostrar grilla de funciones disponibles

**Título**: Como cliente y empleado quiero acceder a la grilla de funciones disponibles para seleccionar una obra de teatro.

**Reglas de negocio**:

**Criterios de aceptación**:

*Escenario 1:* Muestra de funciones disponibles exitosa

    Dado que existen funciones disponibles.
    Cuando se selecciona mostrar funciones disponibles.
    Entonces el sistema exhibe la grilla de funciones disponibles.

*Escenario 2:* Muestra de funciones disponibles fallida por falta de disponibilidad

    Dado que no existen funciones disponibles.
    Cuando se selecciona mostrar funciones disponibles.
    Entonces el sistema informa que no hay funciones de obras disponibles.

___

**ID**: Comprar entradas vía web

**Título**: Como usuario quiero comprar entradas vía web para conseguir entradas de forma remota.

**Reglas de negocio**:


**Criterios de aceptación**:

*Escenario 1:* Compra vía web exitosa

    Dado el usuario de DNI "45284082", tanto las condiciones para la visualización de la grilla de funciones como las de pago son las adecuadas y hay disponibilidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082", la cantidad de 2 lugares solicitados y se presiona pagar.
    Entonces el sistema redirige a ventana de pago, espera respuesta y se emite el código de compra.

*Escenario 2:* Compra vía web fallida por error en el pago

    Dado el usuario de DNI "45284082", las condiciones para la visualización de la grilla de funciones son las adecuadas,las condiciones de pago no son las adecuadas y hay disponiblidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082", la cantidad de 2 lugares solicitados y se presiona pagar.
    Entonces el sistema redirige a ventana de pago, espera respuesta, informa que el pago no se ha podido realizar y permite intentar nuevamente.

*Escenario 3:* Compra vía web fallida por disponibilidad insuficiente

    Dado el usuario de DNI "45284082", tanto las condiciones para la visualización de la grilla de funciones como las de pago son las adecuadas y no hay disponibilidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082" y se indica la cantidad de 2 lugares solicitados.
    Entonces el sistema informa que no hay disponibilidad de lugares suficiente para comprar la cantidad indicada.

___

**ID**: Comprar entrada personalmente

**Título**: Como empleado quiero gestionar compra de entrada físicamente para que el cliente acceda a ella de forma local.

**Reglas de negocio**:

**Criterios de aceptación**:

*Escenario 1*: Compra personal exitosa

    Dado el cliente de DNI "45284082", tanto las condiciones para la visualización de la grilla de funciones como las de pago son las adecuadas y hay disponibilidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082", la cantidad de 2 lugares solicitados y se presiona pagar.
    Entonces el sistema redirige a ventana de pago, espera respuesta e imprime las entradas.

*Escenario 2:* Compra personal fallida por error en el pago

    Dado el usuario de DNI "45284082", las condiciones para la visualización de la grilla de funciones son las adecuadas,las condiciones de pago no son las adecuadas y hay disponiblidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082", la cantidad de 2 lugares solicitados y se presiona pagar.
    Entonces el sistema redirige a ventana de pago, espera respuesta, informa que el pago no se ha podido realizar y permite intentar nuevamente.

*Escenario 3:* Compra personal fallida por disponibilidad insuficiente

    Dado el usuario de DNI "45284082", tanto las condiciones para la visualización de la grilla de funciones como las de pago son las adecuadas y no hay disponibilidad suficiente.
    Cuando se selecciona la obra "El Principito" del "11/9" a las "19:00hs", se ingresa el DNI "45284082" y se indica la cantidad de 2 lugares solicitados.
    Entonces el sistema informa que no hay disponibilidad de lugares suficiente para comprar la cantidad indicada.

___

**ID**: Pagar con tarjeta

**Título**: Como cliente quiero pagar con tarjeta para abonar mis entradas.

**Reglas de negocio:**
- El número debe corresponder a una tarjeta de crédito

**Criterios de aceptación**:

*Escenario 1:* Pago con tarjeta realizado exitosamente.

    Dado que la conexión con el servidor del banco es exitosa, el número "5362765397525673" corresponde a una tarjeta de crédito y la tarjeta tiene saldo suficiente.
    Cuando se ingresa el número de tarjeta "5362765397525673", vencimiento "06/25", código de seguridad "777" y se presiona "pagar".
    Entonces el sistema registra el pago e informa compra exitosa.

*Escenario 2:* Pago fallido por tarjeta de crédito inexistente

    Dado que la conexión con el servidor del banco es exitosa y el número "5362765397525673" no corresponde a un número de tarjeta de crédito.
    Cuando se ingresa el número de tarjeta "5362765397525673", vencimiento "06/25", código de seguridad "777" y se presiona "pagar".
    Entonces el sistema informa error por número de tarjeta de crédito no válido.

*Escenario 3:* Pago fallido por saldo insuficiente 

    Dado que la conexión con el servidor del banco es exitosa, el número "5362765397525673" corresponde a una tarjeta de crédito y no posee saldo suficiente para la compra.
    Cuando se ingresa el número de tarjeta "5362765397525673", fecha de vencimiento "06/25", código de seguridad "777" y se presiona "pagar".
    Entonces el sistema informa error por saldo insuficiente.

*Escenario 4:* Pago fallido por error del servidor del banco.

    Dado que la conexión con el servidor del banco es fallida.
    Cuando se ingresa un número de tarjeta, fecha de vencimiento y código de seguridad y presiona "pagar".
    Entonces el sistema informa error por conexión con el banco fallida.

___

**ID**: Retirar entradas reservadas

**Título**: Como empleado quiero gestionar retiro de entradas reservadas para que los clientes abonen y obtengan sus entradas.

**Reglas de negocio**:
- La persona debe tener entradas reservadas no caducadas

**Criterios de aceptación**:

*Escenario 1*: Retiro exitoso

    Dado el cliente de DNI "45284082" el cual posee una entrada reservada no caducada y las condiciones de pago son las adecuadas.
    Cuando se ingresa el nombre "Juan Pérez", el DNI "45284082" y se presiona validar.
    Entonces el sistema indica que el cliente posee una entrada reservada no caducada y procede con el pago.

*Escenario 2*: Retiro fallido por entradas caducadas

    Dado el cliente de DNI "45284082" el cual posee una entrada reservada caducada, y las condiciones de pago son las adecuadas.
    Cuando se ingresa el nombre "Juan Pérez", el DNI "45284082" y se presiona validar.
    Entonces el sistema indica que el cliente la entrada del cliente está caducada e impide continuar con el pago.

*Escenario 3*: Retiro fallido por falta de entradas

    Dado el cliente de DNI "45284082" el cual no posee entradas reservadas.
    Cuando se ingresa el nombre "Juan Pérez", el DNI "45284082" y se presiona validar.
    Entonces el sistema indica que el cliente no ha reservado ninguna entrada.

___

**ID**: Imprimir entradas compradas

**Título**: Como empleado quiero imprimir entradas compradas para que el cliente obtenga sus entradas ya abonadas.

**Reglas de negocio**:


**Criterios de aceptación**:

*Escenario 1*: Impresión exitosa

    Dado el código de compra "66" correspondiente a una entrada existente, y la conexión con dispositivo de impresión es adecuada.
    Cuando se ingresa el código de compra "66" y se presiona continuar.
    Entonces el sistema verifica el código de compra, informa los datos de la entrada y procede con su impresión.

*Escenario 2:* Impresión fallida por código de compra inexistente

    Dado el código de compra "66" que no pertenece a una entrada existente, y la conexión con dispositivo de impresión es adecuada.
    Cuando se ingresa el código de compra "66" y se presiona continuar.
    Entonces el sistema verifica el código de compra e informa que este no es válido.

*Escenario 3:* Impresión fallida por error de conexión con impresora

    Dado el código de compra "66" correspondiente a una entrada existente, y la conexión con dispositivo de impresión no es la adecuada.
    Cuando se ingresa el código de compra "66" y se presiona verificar.
    Entonces el sistema verifica el código de compra, informa los datos de la entrada e indica error al conectarse a la impresora.

___

**ID**: Cargar distribución de obras

**Título**: Como administrador quiero ingresar la distribución semanal de las obras para que la información esté disponible en el sitio.

**Reglas de negocio**:

**Criterios de aceptación**:

*Escenario 1*: Carga exitosa

    Dado que la obra "El Principito" está programada para proyectarse en la semana y existe disponibilidad en la sala.
    Cuando se ingresa la obra "El Principito" en la sala 4 con fecha para "11/9" a las "19:00hs" y se presiona cargar.
    Entonces el sistema informa que se ha cargado correctamente.

*Escenario 2:* Carga fallida por falta de disponibilidad

    Dado que la obra "El Principito" está programada para proyectarse en la semana y no existe disponibilidad en la sala.
    Cuando se ingresa la obra "El Principito" en la sala 4 con fecha para "11/9" a las "19:00hs" y se presiona cargar.
    Entonces el sistema informa que la sala no se encuentra disponible en la distribución horaria especificada.

## Problema 9: Pago Electrónico

**Roles de usuario:**
- Empleado
- Gerente

**Historias de usuario:**
- Recuperar datos de factura
- Determinar monto a cobrar
- Registrar pago en central
- Ver estadísticas de cobros

___

**ID:** Recuperar datos de factura

**Título:** Como empleado, gerente quiero recuperar los datos de la factura para obtener la información importante para el cobro

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* Recuperación de datos exitosa
>**Dado** el código de pago "123" correspondiente a una factura de pago válida y las condiciones de conexión con la central de cobro están dadas.
> **Cuando** se ingresa el código de pago "123" y se presiona obtener datos.
> **Entonces** el sistema se conecta con la central de cobro enviando el token y retorna los datos de la factura.

*Escenario 2:* Recuperación de datos fallida por código inexistente
>**Dado** el código de pago "123" que no corresponde a una factura existente y las condiciones de conexión con la central de cobro están dadas.
>**Cuando** se ingresa el código de pago "123" y se presiona obtener datos.
>**Entonces** el sistema se conecta con la central de cobro enviando el token y notifica que la factura solicitada no existe.

*Escenario 3:* Recuperación de datos fallida por error de conexión con central
>**Dado** el código de pago "123" correspondiente a una factura de pago válida y las condiciones de conexión con la central de cobro no son las adecudas.
>**Cuando** se ingresa el código de pago "123" y se presiona obtener datos.
>**Entonces** el sistema notifica que no se ha podido establecer conexión con la central.

___

**ID:** Determinar monto a cobrar

**Título:** Como empleado, gerente quiero verificar el vencimiento de la factura para conocer el monto que se debe abonar

**Reglas de negocio:**
- Cuando 1er vencimiento está vencido, se aplica recargo al monto original
- Cuando 2do vencimiento está vencido, no se puede cobrar la factura

**Criterios de aceptación:**

*Escenario 1:* Cobro de monto original
>**Dada** la 1era fecha de vencimiento 2/10 la cual no corresponde a una fecha vencida.
>**Cuando** se recibe los datos de factura de empresa ABSA, nro de cliente 1234, 1era fecha de vencimiento 2/10, 2da fecha de vencimiento 15/10, recargo 10% y monto $5000 y se presiona verificar factura.
>**Entonces** el sistema informa que se debe cobrar el monto original.

*Escenario 2:* Cobro de monto con recargo
>**Dada** la 1era fecha de vencimiento 2/10 la cual corresponde a una fecha vencida.
>**Cuando** se recibe los datos de factura de empresa ABSA, nro de cliente 1234, 1era fecha de vencimiento 2/10, 2da fecha de vencimiento 15/10, recargo 10% y monto $5000 y se presiona verificar factura.
>**Entonces** el sistema informa que se debe cobrar el monto original más un recargo del 10%.

*Escenario 3:* Cobro de monto fallido por factura vencida
>**Dada** la 2da fecha de vencimiento 15/10 la cual corresponde a una fecha vencida.
>**Cuando** se recibe los datos de factura de empresa ABSA, nro de cliente 1234, 1era fecha de vencimiento 2/10, 2da fecha de vencimiento 15/10, recargo 10% y monto $5000 y se presiona verificar factura.
> **Entonces** el sistema informa que la factura no se puede cobrar.

___

**ID:** Registrar pagos en central de cobros

**Título:** Como gerente quiero registrar pagos de clientes en central de cobros para asentar las transacciones del día.

**Reglas de negocio:**
- No se deben enviar dos veces las transacciones

**Criterios de aceptación:**

*Escenario 1*: Registro de pagos exitoso
>**Dada** la clave maestra "246" correspondiente a una clave válida, se realizaron transacciones en el día, no se ha realizado un registro anterior en el día y las condiciones de conexión con central de cobros son las adecuadas.
>**Cuando** se ingresa la clave "246" y se presiona registrar pagos.
>**Entonces** el sistema recupera las transacciones, se conecta a la central de cobros enviándole el token, espera confirmación de central de cobros y registra las transacciones como enviadas.

*Escenario 2*: Registro de pagos fallido por clave inexistente
>**Dada** la clave maestra "246" que no corresponde a una clave válida y las condiciones de conexión con central de cobros son las adecuadas.
>**Cuando** se ingresa la clave "246" y se presiona registrar pagos. 
>**Entonces** el sistema indica que la clave ingresada no es válida.

*Escenario 3*: Registro de pagos fallido por error de conexión con central de pagos
>**Dada** la clave maestra "246" que corresponde a una clave válida, se realizaron transacciones en el día, no se ha realizado un registro anterior en el día y las condiciones de conexión con central de cobros no son las adecuadas.
>**Cuando** se ingresa la clave "246" y se presiona registrar pagos.
>**Entonces** el sistema informa que se ha producido un error durante la conexión con la central-

*Escenario 4*: Registro de pagos fallido por falta de transacciones
>**Dada** la clave maestra "246" que corresponde a una clave válida, no se ha realizado un registro anterior en el día y no se realizaron transacciones en el día.
>**Cuando** se ingresa la clave "246" y se presiona registrar pagos.
>**Entonces** el sistema informa que no se han registrado pagos en el día.

*Escenario 5*: Registro de pagos fallido por segundo intento
>**Dada** la clave maestra "246" que corresponde a una clave válida, se han realizado transacciones en el día, se ha realizado un registro de pagos anterior en el día y las condiciones de conexión con central de pago son las adecuadas.
>**Cuando** se ingresa la clave "246" y se presiona registrar pagos.
>**Entonces** el sistema informa que ya han sido enviadas las transacciones del día.

___

**ID:** Ver estadísticas de cobros

**Título:** Como gerente quiero ver las estadísticas de impuestos y servicios cobrados para tener información de los montos y cantidad de cobros realizados

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* Visualización de cobros exitosa
>**Dada** la clave "246" correspondiente a una clave maestra existente y el rango de fecha 1/9 a 30/9 posee cobros.
>**Cuando** se ingresa la clave "246", el rango de fechas desde 1/9 al 30/9 y se presiona ver cobros.
>**Entonces** el sistema muestra las estadísticas de cobros en el rango de fecha, agrupado por empresa.

*Escenario 2*: Visualización de cobros fallida por clave inexistente
>**Dada** la clave "246" que no corresponde a una clave maestra válida y el rango de fecha 1/9 a 30/9 posee cobros.
>**Cuando** se ingresa la clave "246", el rango de fechas desde 1/9 al 30/9 y se presiona ver cobros.
>**Entonces** el sistema informa que la clave maestra no es válida.

*Escenario 3*: Visualización de cobros fallida por rango de fecha sin cobros
>**Dada** la clave "246" que corresponde a una clave maestra válida y el rango de fecha 1/9 a 30/9 posee cobros.
>**Cuando** se ingresa la clave "246", el rango de fechas desde 1/9 al 30/9 y se presiona ver cobros.
>**Entonces** el sistema informa que no se han realizado cobros en el período indicado.

## Problema 10: Un Aventón

**Roles de usuario:**
- Persona no registrada
- Usuario registrado
- Piloto
- Copiloto

**Historias de usuario:**
- Registrar usuario
- Iniciar sesión
- Cerrar sesión
- Dar de alta viaje
- Postular para viaje
- Aceptar o rechazar candidato a copiloto
- Calificar usuario

___

**ID:** Registrar usuario

**Título:** Como persona quiero registrarme en la aplicación para compartir vehículo en un viaje.

**Reglas de negocio**
- No pueden haber dos correos electrónicos iguales en el sistema

**Criterios de aceptación:**

*Escenario 1*: Registro exitoso
>**Dado** el email "user@example.com" correspondiente a una dirección de correo no existente en el sistema.
>**Cuando** se ingresa el email "user@example.com", el username "usuario1" y la contraseña "1234" y se presiona registrarse.
>**Entonces** el sistema crea la cuenta y la registra.

*Escenario 2:* Registro fallido por email existente
>**Dado** el email "user@example.com" el cual ya se encuentra registrado en el sistema.
>**Cuando** se ingresa el email "user@example.com", el username "usuario1" y la contraseña "1234" y se presiona registrarse.
>**Entonces** el sistema informa que la dirección de correo electrónico ya está asociada a una cuenta existente.

___

**ID**: Iniciar Sesión

**Título:** Como usuario registrado quiero iniciar sesión para acceder a las funcionalidades de la aplicación

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1*: Inicio de sesión exitoso
>**Dado** el username "usuario1" correspondiente a un usuario ya registrado y la contraseña "1234" es correcta.
>**Cuando** se ingresa el username "usuario1", la contraseña "1234" y se presiona iniciar sesión.
>**Entonces** el sistema da mensaje de bienvenida y muestra opciones del menú principal.

*Escenario 2*: Inicio de sesión fallido por username inexistente
>**Dado** el username "usuario1" no corresponde a un usuario registrado
>**Cuando** se ingresa el username "usuario1", la contraseña "1234" y se presiona iniciar sesión. 
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas.

*Escenario 3*: Inicio de sesión fallido por contraseña incorrecta
>**Dado** el username "usuario1" que corresponde a un usuario registrado y la contraseña "1234" no es correcta
>**Cuando** se ingresa el username "usuario1", la contraseña "1234" y se presiona iniciar sesión. 
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas.

___

**ID:** Cerrar sesión

**Título:** Como usuario registrado quiero cerrar sesión para salir del sistema

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* Cierre de sesión exitoso
>**Dado** el usuario de username "usuario1" que ha iniciado sesión.
>**Cuando** se presiona cerrar sesión.
>**Entonces** el sistema cierra la sesión del usuario y redirige a la pantalla de inicio de sesión.

___

**ID:** Dar de alta viaje

**Título:** Como piloto quiero dar de alta un viaje para buscar copilotos que me acompañen

**Reglas de negocio:**
- Los viajes no pueden superponerse
- Un usuario que adeuda calificaciones no puede dar de alta un viaje

**Criterios de aceptación:**

*Escenario 1:* Alta de viaje exitosa
>**Dado** el usuario piloto "usuario1" que se encuentra autenticado, no adeuda calificaciones, y la fecha y hora 2/10 15:00hs no se superpone con otro viaje suyo.   
>**Cuando** el usuario "usuario1" ingresa la fecha 2/10, la hora 15:00hs, el vehículo Chery Tiggo, y presiona subir viaje.
>**Entonces** el sistema da de alta el viaje y lo incluye como opción para postularse.

*Escenario 2:* Alta de viaje fallida por viaje superpuesto
>**Dado** el usuario piloto "usuario1" que se encuentra autenticado, no adeuda calificaciones y la fecha y hora 2/10 15:00hs se superpone con un viaje suyo dado de alta anteriormente.
>**Cuando** el usuario "usuario1" ingresa la fecha 2/10, la hora 15:00hs, el vehículo Chery Tiggo, y presiona subir viaje.
>**Entonces** el sistema verifica la fecha y hora e informa que ya posee un viaje en la franja horaria indicada.

*Escenario 3:* Alta de viaje fallida por adeudar calificación
>**Dado** el usuario piloto "usuario1" que se encuentra autenticado y adeuda calificaciones.
>**Cuando** el usuario "usuario1" selecciona la opción de cargar viaje.
>**Entonces** el sistema le informa que debe calificar lo que adeuda antes de dar de alta otro viaje.

___

**ID:** Postular para viaje

**Título:** Como copiloto quiero postularme a un viaje para unirme a un piloto en su recorrido

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* Postulación exitosa
>**Dado** el usuario copiloto "usuario1" quien se encuentra autenticado y el viaje posee capacidad suficiente.
>**Cuando** el usuario "usuario1" selecciona el viaje a postularse.
>**Entonces** el sistema envía una solicitud al dueño del viaje de parte del copiloto para participar del viaje.

*Escenario 2:* Postulación fallida por falta de disponibilidad
>**Dado** el usuario copiloto "usuario1" quien se encuentra autenticado y el viaje no posee capacidad disponible suficiente. 
>**Cuando** el usuario "usuario1" selecciona el viaje a postularse.
>**Entonces** el sistema informa que el viaje seleccionado no posee lugares disponibles.

___

**ID:** Aceptar o rechazar candidato a copiloto

**Título:** Como piloto quiero aceptar o rechazar un copiloto para determinar los acompañantes de mi viaje

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* aceptación de copiloto exitosa
>**Dado** el usuario piloto "usuario1" que posee un viaje dado de alta y postulantes para este.
>**Cuando** el usuario "usuario1" selecciona al postulante y presiona aceptar.
>**Entonces** el sistema informa que el postulante ha sido aceptado y envía notificación al copiloto.

*Escenario 2:* rechazo de copiloto exitosa
>**Dado** el usuario piloto "usuario1" que posee un viaje dado de alta y postulantes para este.
>**Cuando** el usuario "usuario1" selecciona al postulante y presiona rechazar.
>**Entonces** el sistema informa que el postulante ha sido rechazado y lo elimina de los candidatos al viaje.

___

**ID:** Calificar usuario

**Título:** Como participante de viaje quiero calificar a los demás usuarios participantes para opinar sobre su compañía durante el viaje

**Reglas de negocio:**
- Calificaciones positivas suman un punto de reputación
- Calificaciones negativas restan un punto de reputación

**Criterios de aceptación:**

*Escenario 1:* calificación positiva exitosa
>**Dado** el usuario de username "usuario1" que ha participado en el viaje ya finalizado junto al usuario de username "usuario2"
>**Cuando** el usuario "usuario1" selecciona al usuario "usuario2", indica una calificación positiva y selecciona enviar.
>**Entonces** el sistema suma un punto de reputación del usuario calificado y registra que el usuario calificador ha expedido su reseña.

*Escenario 2:* calificación negativa exitosa
>**Dado** el usuario de username "usuario1" que ha participado en el viaje ya finalizado junto al usuario de username "usuario2"
>**Cuando** el usuario "usuario1" selecciona al usuario "usuario2", indica una calificación negativa y selecciona enviar.
>**Entonces** el sistema resta un punto de reputación del usuario calificado y registra que el usuario calificador ha expedido su reseña.

## Problema 11: Concursos

**Roles de usuarios:**
- Docente no registrado
- Docente registrado
- Jefe del área de concursos

**Historias de usuario:**
- Registrar usuario
- Iniciar sesión
- Cerrar sesión
- Inscribirse a concurso
- Imprimir listado de inscriptos a materia

___

**ID:** Registrar usuario

**Título:** Como docente no registrado quiero registrarme en el sistema para poder inscribirme a un concurso.

**Reglas de negocio**
- Mail no puede repetirse y será usado como nombre de usuario
- DNI debe ser menor a 55 millones y mayor a 12 millones

**Criterios de aceptación:**

*Escenario 1*: Registro exitoso
>**Dado** el email "user@example.com" correspondiente a una dirección de correo no existente en el sistema y el DNI "40.947.425" el cual es menor a 55 millones y mayor a 12 millones.
>**Cuando** el docente no registrado ingresa el DNI "40.947.425", el email "user@example.com", el nombre "Pedro", el apellido "Pascal" y presiona registrarse.
>**Entonces** el sistema da de alta la cuenta y envía al correo indicado la contraseña de la cuenta generada automáticamente.

*Escenario 2:* Registro fallido por email existente
>**Dado** el email "user@example.com" el cual ya se encuentra registrado en el sistema.
>**Cuando** el docente no registrado ingresa el DNI "40.947.425", el email "user@example.com", el nombre "Pedro", el apellido "Pascal" y presiona registrarse.
>**Entonces** el sistema informa que la dirección de correo electrónico ya está asociada a una cuenta existente.

*Escenario 3:* Registro fallido por DNI no permitido
>**Dado** el email "user@example.com" el cual no se encuentra registrado en el sistema y el DNI "10.242.257" el cual es menor a 12 millones.
>**Cuando** el docente no registrado ingresa el DNI "10.242.257", el email "user@example.com", el nombre "Pedro", el apellido "Pascal" y presiona registrarse.
>**Entonces** el sistema informa que el DNI ingresado no cumple con los criterios establecidos para el registro de cuentas y retorna a la pantalla de inicio.

___

**ID**: Iniciar Sesión

**Título:** Como docente registrado y jefe del área de concursos quiero iniciar sesión para acceder a las funcionalidades del sistema de concursos

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1*: Inicio de sesión exitoso para docente
>**Dado** el mail "user@example.com" correspondiente a un docente ya registrado y la contraseña "1234" es correcta.
>**Cuando** el docente registrado ingresa el mail "user@example.com", la contraseña "1234" y presiona iniciar sesión.
>**Entonces** el sistema da mensaje de bienvenida y muestra la opción de inscribirse a concurso y cerrar sesión.

*Escenario 2*: Inicio de sesión exitoso para jefe de área de concursos
>**Dado** el mail "jefe@example.com" correspondiente a un al jefe del área de concursos y la contraseña "1234" es correcta.
>**Cuando** el jefe del área de concursos ingresa el mail "jefe@example.com", la contraseña "1234" y presiona iniciar sesión.
>**Entonces** el sistema da mensaje de bienvenida y muestra la opción de imprimir listado de inscriptos y cerrar sesión.

*Escenario 3*: Inicio de sesión fallido por mail inexistente
>**Dado** el mail "user@example.com" que no corresponde a un usuario del sistema.
>**Cuando** el usuario ingresa el mail "user@example.com", la contraseña "1234" y presiona iniciar sesión. 
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas.

*Escenario 4*: Inicio de sesión fallido por contraseña incorrecta
>**Dado** el mail "user@example.com" que corresponde a un usuario del sistema y la contraseña "1234" no es correcta
>**Cuando** el usuario ingresa el mail "user@example.com", la contraseña "1234" y presiona iniciar sesión. 
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas.

___

**ID:** Cerrar sesión

**Título:** Como usuario autenticado quiero cerrar sesión para salir del sistema

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* Cierre de sesión exitoso
>**Dado** el mail "user@example.com" correspondiente a un usuario del sistema que ha iniciado sesión.
>**Cuando** se presiona cerrar sesión.
>**Entonces** el sistema cierra la sesión del usuario y redirige a la pantalla de inicio de sesión.

___

**ID:** Inscribirse a concurso

**Título:** Como docente registrado quiero inscribirme a un concurso para competir por un puesto en una materia determinada

**Reglas de negocio:**
- El docente no puede inscribirse a más de 3 concursos

**Criterios de aceptación:**

*Escenario 1:* Inscripción exitosa
>**Dado** el docente autenticado de mail "user@example.com" que no se ha inscrito a ningún concurso.
>**Cuando** el docente autenticado de mail "user@example.com" selecciona la materia "Ingeniería de Software I" y presiona inscribirse.
>**Entonces** el sistema realiza la inscripción e imprime un comprobante.

*Escenario 2:* Inscripción fallida por cantidad de inscripciones superior a las permitidas
>**Dado** el docente autenticado de mail "user@example.com" que se encuentra inscripto a 3 concursos.
>**Cuando** el docente autenticado de mail "user@example.com" selecciona la materia "Ingeniería de Software I" y presiona inscribirse.
>**Entonces** el sistema notifica que el usuario ya se encuentra inscripto a 3 concursos

___

**ID**: Imprimir listado de inscriptos a materia

**Título:** Como jefe del área de concursos quiero imprimir el listado de inscriptos a una materia determinada para enviar dicho lista al secretario administrativo

**Reglas de negocio:**

**Criterios de aceptación**

*Escenario 1:* Impresión exitosa
>**Dado** el jefe del área de concursos de mail "jefe@example.com" que se encuentra autenticado en el sistema, las condiciones de conexión con la impresora son las adecuadas y hay docentes inscriptos en el concurso de la materia "Ingeniería de Software I".
>**Cuando** el jefe del área de concursos de mail "jefe@example.com" selecciona la materia "Ingeniería de Software 1" y presiona imprimir listado.
>**Entonces** el sistema se conecta con la impresora y envía los datos necesarios para realizar la impresión.

*Escenario 2:* Impresión fallida por error de conexión con impresora
>**Dado** el jefe del área de concursos de mail "jefe@example.com" que se encuentra autenticado en el sistema, las condiciones de conexión con la impresora no son las adecuadas y hay docentes inscriptos en el concurso de la materia "Ingeniería de Software I".
>**Cuando** el jefe del área de concursos de mail "jefe@example.com" selecciona la materia "Ingeniería de Software 1" y presiona imprimir listado.
>**Entonces** el sistema informa que la conexión con la impresora ha fallado.

*Escenario 3:* Impresión de listado impedida por falta de inscriptos
>**Dado** el jefe del área de concursos de mail "jefe@example.com" que se encuentra autenticado en el sistema, las condiciones de conexión con la impresora son las adecuadas y no hay docentes inscriptos en el concurso de la materia "Ingeniería de Software I".
>**Cuando** el jefe del área de concursos de mail "jefe@example.com" selecciona la materia "Ingeniería de Software 1" y presiona imprimir listado.
>**Entonces** el sistema notifica que no se han inscrito docentes en la materia seleccionada.

## Problema 12: Créditos bancarios

**Roles de usuario:**
- Cliente
- Gerente del banco

**Historias de usuario:**
- Pedir crédito
- Consultar estado de trámite
- Pedir listado de créditos aprobados

___

**ID:** Pedir crédito

**Título:** Como cliente quiero pedir un crédito en el banco para poder obtener el monto de dinero solicitado

**Reglas de negocio:**
- El pedido del crédito podrá ser evaluado solo para clientes del banco
- El monto solicitado no debe superar los $400.000

**Criterios de aceptación:**

*Escenario 1:* pedido de crédito exitoso
>**Dado** el DNI 45829124 correspondiente a un cliente del banco y el monto solicitado de $300.000
>
>**Cuando** el cliente ingresa el DNI 45829124, nombre Juan, apellido Verón, mail user@example.com, tipo de crédito personal y monto $300.000, y presiona solicitar crédito
>
>**Entonces** el sistema almacena el trámite para que sea analizado e imprime número de comprobante para el cliente

*Escenario 2:* pedido de crédito fallido por cliente no afiliado al banco
>**Dado** el DNI 45829124 que no corresponde a un cliente del banco
>
>**Cuando** el cliente ingresa el DNI 45829124, nombre Juan, apellido Verón, mail user@example.com, tipo de crédito personal y monto $300.000, y presiona solicitar crédito
>
>**Entonces** el sistema detecta que el DNI no corresponde a un cliente del banco y envía un correo electrónico a la dirección de email indicada con un instructivo para hacerse cliente del banco

*Escenario 3:* pedido de crédito fallido por límite de monto excedido
>**Dado** el DNI 45829124 correspondiente a un cliente del banco y el monto solicitado de $500.000
>
>**Cuando** el cliente ingresa el DNI 45829124, nombre Juan, apellido Verón, mail user@example.com, tipo de crédito personal y monto $500.000, y presiona solicitar crédito
>
>**Entonces** el sistema muestra el mensaje "El monto solicitado excede el límite permitido"

___

**ID:** Consultar estado de trámite

**Título:** Como cliente quiero consultar el estado de un trámite para saber cuando se me otorgará el cŕedito solicitado

**Reglas de negocio:**
- Si se ingresa tres veces un código inexistente el sistema bloquea la ip del cliente por 24hs

**Criterios de aceptación:**

*Escenario 1:* consulta exitosa
>**Dado** el número de comprobante 123 correspondiente a un trámite válido y el usuario no ha tenido 3 intentos fallidos
>
>**Cuando** el cliente ingresa el número de comprobante 123 y presiona consultar estado
>
>**Entonces** el sistema retorna un informe con el estado del trámite

*Escenario 2:* consulta fallida por código inválido sin bloqueo de usuario
>**Dado** el número de comprobante 123 que no corresponde a un trámite válido y el usuario no ha tenido 3 intentos fallidos
>
>**Cuando** el cliente ingresa el número de comprobante 123 y presiona consultar estado
>
>**Entonces** el sistema muestra el mensaje "Trámite inexistente"

*Escenario 3:* consulta fallida por código inválido con bloqueo de usuario
>**Dado** el número de comprobante 123 que no corresponde a un trámite válido y es la tercera vez que el usuario intenta consultar el trámite
>
>**Cuando** el cliente ingresa el número de comprobante 123 y presiona consultar estado
>
>**Entonces** el sistema bloquea la ip del cliente por 24hs y muestra el mensaje "Usted ha excedido el número e consultas inválidas"

___

**ID:** Pedir listado de créditos aprobados

**Título:** como gerente del banco quiero pedir un listado de créditos aprobados entre fechas para tener información sobre los créditos a clientes en un período especificado

**Reglas de negocio:**

**Criterios de aceptación:**
*Escenario 1:* pedido de listado exitoso
>**Dado** las fechas 1/9 y 30/9 las cuales corresponden a fechas válidas con créditos aprobados
>
>**Cuando** el gerente del banco ingresa las fechas 1/9 y 30/9, y presiona pedir listado
>
>**Entonces** el sistema muestra un listado con los créditos aprobados en entre las fechas indicadas

*Escenario 2:* pedido de listado fallido por fechas inválidas
>**Dado** las fechas 1/9 y 31/9 las cuales no son fechas válidas
>
>**Cuando** el gerente del banco ingresa las fechas 1/9 y 31/9, y presiona pedir listado
>
>**Entonces** el sistema muestra un mensaje indicando "las fechas ingresadas no son válidas"

*Escenario 3:* pedido de listado vacío por falta de créditos
>**Dado** las fechas 1/9 y 30/9 correspondientes a fechas válidas sin créditos aprobados
>
>**Cuando** el gerente del banco ingresa las fechas 1/9 y 30/9, y presiona pedir listado
>
>**Entonces** el sistema muestra el mensaje "No hay créditos aprobados en las fechas ingresadas"

___

## Problema 13: Venta de libros

**Roles de usuario:**
- Usuario visitante
- Usuario autenticado
- Servidor externo (banco)

**Historias de usuario:**
- Acceder catálogo de libros
- Dar de alta parcialmente
- Registrar usuario totalmente
- Iniciar sesión
- Cerrar sesión
- Comprar libro
- Pagar con tarjeta

___

**ID:** Acceder catálogo de libros

**Título:** Como usuario visitante o registrado quiero acceder al catálogo de libros para visualizar los productos que se ofrecen

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* muestra de catálogo con libros disponibles
>**Dado** el catálogo que posee libros disponibles
>
>**Cuando** el usuario visitante o registrado presiona la opción de catálogo de libros
>
>**Entonces** el sistema muestra los libros disponibles

*Escenario 2:* muestra de catálogo sin libros disponibles
>**Dado** el catálogo que no posee libros disponibles
>
>**Cuando** el usuario visitante o registrado presiona la opción de catálogo de libros
>
>**Entonces** el sistema informa que no hay libros disponibles

___

**ID:** Dar de alta parcialmente

**Título:** Como usuario visitante quiero darme de alta parcialmente para realizar el primer paso de registro de mi cuenta

**Reglas de negocio:**
- el correo electrónico será utilizado como username
- la clave debe ser de 6 caracteres

**Criterios de aceptación:**

*Escenario 1:* alta parcial exitosa
>**Dado** el email user@example.com que no existe en el sistema y la clave 123456 que posee 6 caracteres
>
>**Cuando** el usuario visitante ingresa el nombre Enzo, apellido Pérez, DNI 45827192, email user@example.com, clave 123456 y presiona registrarse
>
>**Entonces** el sistema genera un código de 16 dígitos y lo envía al correo electrónico indicado

*Escenario 2:* alta parcial fallida por email existente
>**Dado** el email user@example.com que ya existe en el sistema
>
>**Cuando** el usuario visitante ingresa el nombre Enzo, apellido Pérez, DNI 45827192, email user@example.com, clave 123456 y presiona registrarse
>
>**Entonces** el sistema informa que el email ya se encuentra registrado

*Escenario 3:* alta parcial fallida por clave de longitud no permitida
>**Dado** el email user@xample.com que no existe en el sistema y la clave 123 que posee 3 caracteres
>
>**Cuando** el usuario visitante ingresa el nombre Enzo, apellido Pérez, DNI 45827192, email user@example.com y la clave 123
>
>**Entonces** el sistema notifica que la clave debe poseer 6 caracteres

___

**ID:** Registrar usuario totalmente

**Título:** Como usuario visitante quiero completar el registro de mi cuenta para poder comprar un libro

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* registro exitoso
>**Dado** el código 0112358132134558 que corresponde a un código de confirmación de cuenta generado y el email user@example.com que está dado de alta parcialmente en el sistema
>
>**Cuando** el usuario visitante ingresa el email user@example.com, el código de confirmación 0112358132134558 y presiona confirmar
>
>**Entonces** el sistema registra al usuario

*Escenario 2:* registro fallido por código incorrecto
>**Dado** el código 0112358132134558 que no corresponde a un código de confirmación de cuenta generado
>
>**Cuando** el usuario visitante ingresa el email user@example.com, el código de confirmación 0112358132134558 y presiona confirmar
>
>**Entonces** el sistema informa que el código de confirmación no es válido

*Escenario 3:* registro fallido por email incorrecto
>**Dado** el código 0112358132134558 que corresponde a un código de confirmación de cuenta generado y el email user@example que no existe en el sistema
>
>**Cuando** el usuario visitante ingresa el email user@example.com, el código de confirmación 0112358132134558 y presiona confirmar
>
>**Entonces** el sistema informa que el email indicado no está registrado

__

**ID:** Iniciar sesión

**Título:** como usuario registrado quiero iniciar sesión para acceder a las funcionalidades del sistema

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1*: inicio de sesión exitoso
>**Dado** el email user@example.com el cual existe en el sistema y la clave 123456 que es correcta
>
>**Cuando** el usuario registrado ingresa el email user@example.com, la clave 123456 y presiona iniciar sesión
>
>**Entonces** el sistema redirige al usuario a la pantalla principal del sitio y habilita las funcionalides de usuario con sesión iniciada

*Escenario 2*: inicio de sesión fallido por email incorrecto
>**Dado** el email user@example.com el cual no existe en el sistema
>
>**Cuando** el usuario registrado ingresa el email user@example.com, la clave 123456 y presiona iniciar sesión
>
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas

*Escenario 3*: inicio de sesión fallido por clave incorrecto
>**Dado** el email user@example.com el cual existe en el sistema y la clave 123456 que no es correcta
>
>**Cuando** el usuario registrado ingresa el email user@example.com, la clave 123456 y presiona iniciar sesión
>
>**Entonces** el sistema informa que las credenciales ingresadas no son válidas

___

**ID:** Cerrar sesión

**Título:** Como usuario registrado quiero cerrar sesión para salir del sistema

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* cierre de sesión exitoso 
>**Dado** el usuario de email user@example.com que ha iniciado sesión
>
>**Cuando** el usuario registrado presiona cerrar sesión
>
>**Entonces** el sistema cierra la sesión del usuario y redirige a la pantalla de inicio de sesión

___

**ID:** Comprar libro

**Título:** Como usuario registrado quiero comprar un libro para agregarlo a mi biblioteca personal

**Reglas de negocio:**

**Criterios de aceptación:**

*Escenario 1:* compra exitosa
>**Dado** el ISBN 1234 que corresponde a un libro disponible y las condiciones de pago son las adecuadas
>
>**Cuando** el usuario registrado ingresa el ISBN 1234 y presiona comprar
>
>**Entonces** el sistema redirige al usuario al pago con tarjeta, espera respuesta y genera un enlace de descarga al correo del usuario

*Escenario 2:* compra fallida por ISBN de libro no disponible
>**Dado** el ISBN 1234 que corresponde a un libro que no se encuentra disponible
>
>**Cuando** el usuario registrado ingresa el ISBN 1234 y presiona comprar
>
>**Entonces** el sistema informa que el libro elegido no se encuentra disponible

*Escenario 3:* compra fallida por ISBN inexistente
>**Dado** el ISBN 1234 que no corresponde a un libro existente
>
>**Cuando** el usuario registrado ingresa el ISBN 1234
>
>**Entonces** el sistema informa que el ISBN especificado no se corresponde con un libro existente en el sitio

*Escenario 4:* compra fallida por error en el pago
>**Dado** el ISBN 1234 que corresponde a un libro disponible y las condiciones de pago no son las adecuadas
>
>**Cuando** el usuario registrado ingresa el ISBN 1234 y presiona pagar
>
>**Entonces** el sistema redirige al usuario al pago con tarjeta, espera respuesta e informa que se ha producido un error en el pago por lo que no se ha podido realizar la compra

___

**ID:** Pagar con tarjeta

**Título:** Como usuario registrado quiero pagar con tarjeta para finalizar la compra de mi libro

**Reglas de negocio:**
- El nombre y apellido registrado en el sistema deben coincidir con el de la tarjeta

**Criterios de aceptación:**

*Escenario 1:* pago realizado exitosamente
>**Dado** el número 4567 que corresponde a una tarjeta existente con fondos suficientes, el nombre y apellido Pedro Pascal que se condicen con los registrados en la cuenta y la conexión con el servidor externo es exitosa
>
>**Cuando** el usuario registrado ingresa el nombre Pedro, apellido Pascal, nro de tarjeta 4567 y presiona pagar
>
>**Entonces** el sistema registra el pago y retorna resultado de éxito

*Escenario 2:* pago no realizado por número de tarjeta inexistente
>**Dado** el número 4567 que no corresponde a una tarjeta existente y la conexión con el servidor externo es exitosa
>
>**Cuando** el usuario registrado ingresa el número 4567, el nombre Pedro, el apellido Pascal y presiona pagar
>
>**Entonces** el sistema retorna error por número de tarjeta inexistente

*Escenario 3:* pago no realizado por fondos insuficientes
>**Dado** el número 4567 que corresponde a una tarjeta existente con fondos insuficientes y la conexión con el servidor externo es exitosa
>
>**Cuando** el usuario registrado ingresa el número 4567, el nombre Pedro, el apellido Pascal y presiona pagar
>
>**Entonces** el sistema retorna error por fondos de tarjeta insuficientes

*Escenario 4:* pago no realizado por error de conexión con servidor externo
>**Dado** que no se ha podido establecer la conexión con el servidor externo
>
>**Cuando** el usuario registrado ingresa el número de tarjeta 4567, el nombre Pedro, el apellido Pascal y presiona pagar
>
>**Entonces** el sistema retorna error por conexión fallida

*Escenario 5:* pago no realizado por titular de tarjeta incorrecto
>**Dado** que el número de tarjeta 4567 corresponde a una tarjeta existente con fondos suficientes, la conexión con el servidor externo es exitosa y el nombre y apellido del titular de la tarjeta Pedro Pascal no se condicen con los registrados en la cuenta
>
>**Cuando** el usuario registrado ingresa el número de tarjeta 4567, el nombre Pedro, el apellido Pascal y presiona pagar
>
>**Entonces** el sistema informa que solo el titular de la tarjeta puede realizar la compra 