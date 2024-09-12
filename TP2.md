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