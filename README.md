# API DOCS

## Referencia API

El API de ONVO utiliza **REST**. Nuestro API tiene URLs orientadas a recursos predecibles, acepta **JSON** en el cuerpo de las solicitudes así como también es el formato codificado de sus respuestas. 

| Base URL                |
| ----------------------- |
| https://api.onvopay.com |

Podés usar el API de ONVO en modo de prueba, que no afecta los datos del modo en vivo, ni interactúa con las redes bancarias. El API Key que usés para la autenticación de la solicitud determina si la solicitud será de modo de prueba o en vivo.

## Autenticación

El API de ONVO usa API Keys para autenticar las solicitudes. Podés ver y administrar tus API Keys en el dashboard de ONVO.

Las API Keys del modo de prueba tienen el prefijo `onvo_test_` y las de modo en vivo tienen el prefijo `onvo_live_`.

Tus API keys tienen muchos privilegios, mantenelas de forma segura. No compartás tus API Keys secretas ni las usés código client-side.

La autenticación del API es manejada con Bearer Auth mediante el HTTP Authorization header. (ej:  `Authorization: Bearer onvo_test_publishable_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ`).

Todos las solicitudes al API deben de hacerse mediante HTTPS. Solicitudes mediante HTTP fallarán, así como solicitudes sin autenticación. 



## Errores

## Paginación

## Clientes

Este objeto representa un cliente de tu comercio. Te permite crear cargos recurrentes y rastrear pagos que pertenecen al mismo cliente. 

### Endpoints
POST   /v1/customers
GET    /v1/customers/:id
POST   /v1/customers/:id
DELETE /v1/customers/:id
GET    /v1/customers

### El objeto Cliente

#### Atributos


___
##### id _string_
Identificador único del objeto.
___
##### address _hash_
La dirección del cliente.

**Atributos:**
###### address.city _string_
Nombre de ciudad o pueblo.
###### address.country _string_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### address.line1 _string_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### address.line2 _string_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### address.postalCode _string_
Código postal o código ZIP.
###### address.state _string_
Estado, provincia o región.
___
##### amountSpent _integer_
El monto total, en USD y en centavos/céntimos, acumulado de transacciones satisfactorias del cliente.

___
##### createdAt _datetime_
Fecha y hora, en UTC, en la que fue creado el objeto. 
___
##### description _string_
Texto arbitrario adjunto al objeto. Comúnmente útil para mostrar a usuarios.
___
##### email _string_
La dirección de correo electrónico del cliente.
___
##### lastTransactionAt _datetime_
Fecha y hora en UTC de la última transacción satisfactoria del cliente.
___
##### mode _string_
El modo en el que existen los datos del objeto. Ya sea `test` o `live`.
___
##### name _string_
El nombre completo del cliente
___
##### phone _string_
El número de teléfono del cliente, incluyendo código de área (Ej: +50688880000)
___
##### shipping _hash_
La dirección de entrega a domicilio del cliente.

**Atributos:**
###### shipping.address.city _string_
Nombre de ciudad o pueblo.
###### shipping.address.country _string_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### shipping.address.line1 _string_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### shipping.address.line2 _string_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### shipping.address.postalCode _string_
Código postal o código ZIP.
###### shipping.address.state _string_
Estado, provincia o región.
###### shipping.name _string_
Nombre del cliente.
###### shipping.phone _string_
Teléfono del cliente (incluyendo extensión).
___
##### transactionsCount _integer_
Conteo histórico de las transacciones satisfactorias del cliente.
___
##### updatedAt _datetime_
Fecha y hora, en UTC, en la que fue actualizado por última vez el objeto. 
___

```json 
{
  "id": "string",
  "address": {
    "city": "string",
    "country": "string",
    "line1": "string",
    "line2": "string",
    "postalCode": "string",
    "state": "string"
  },
  "amountSpent": 0,
  "createdAt": "2022-06-12T21:21:10.587Z",
  "description": "string",
  "email": "string",
  "lastTransactionAt": "2022-06-12T21:21:10.587Z",
  "mode": "string",
  "name": "string",
  "phone": "string",
  "shipping": {
    "name": "string",
    "phone": "string",
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postalCode": "string",
      "state": "string"
    }

  },
  "transactionsCount": 0,
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Crear un Cliente
```
POST /v1/customers
```
#### Parámetros

___
##### address _optional_
La dirección del cliente.

**Parámetros:**
###### address.city _optional_
Nombre de ciudad o pueblo.
###### address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### address.line2 _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### address.postalCode _optional_
Código postal o código ZIP.
###### address.state _optional_
Estado, provincia o región.

___
##### description _optional_
Texto arbitrario adjunto al objeto. Comúnmente útil para mostrar a usuarios.
___
##### email _optional_
La dirección de correo electrónico del cliente.
___
##### name _optional_
El nombre completo del cliente
___
##### phone _optional_
El número de teléfono del cliente, incluyendo código de área (Ej: +50688880000)
___
##### shipping _optional_
La dirección de entrega a domicilio del cliente.

**Parámetros:**
###### shipping.address.city _optional_
Nombre de ciudad o pueblo.
###### shipping.address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### shipping.address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### shipping.address.line2 _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### shipping.address.postalCode _optional_
Código postal o código ZIP.
###### shipping.address.state _optional_
Estado, provincia o región.
###### shipping.name _optional_
Nombre del cliente.
###### shipping.phone_optional_
Teléfono del cliente (incluyendo extensión).

**Retorna:**
Retorna el objeto de Cliente, si la creación fue satisfactoria. Retorna un error si los parámetros son inválidos (Ej: Enviando `Costa Rica` en lugar de `CR`, para el parámetro de `address.country`).

```
POST /v1/customers
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 
{ 
  "address": {
    "country": "CR",
  },
  "description": "Cliente creado para demostración",
  "email": "email@onvopay.com",
  "name": "Nombre del cliente"
}
```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "address": {
    "city": null,
    "country": "CR",
    "line1": null,
    "line2": null,
    "postalCode": null,
    "state": null
  },
  "amountSpent": 0,
  "createdAt": "2022-06-12T21:21:10.587Z",
  "description": "Cliente creado para demostración",
  "email": "email@onvopay.com",
  "lastTransactionAt": null,
  "mode": "test",
  "name": "Nombre del cliente",
  "phone": null,
  "shipping": {
    "name": null,
    "phone": null,
    "address": {
      "city": null,
      "country": null,
      "line1": null,
      "line2": null,
      "postalCode": null,
      "state": null
    }
  },
  "transactionsCount": 0,
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Obtener un Cliente
```
GET /v1/customers/:id
```
#### Parámetros

___
Sin parámetros.

**Retorna:**
Retorna el objeto de Cliente para un id válido. 

```
GET /v1/customers/cl40muorw00493ndp0okzk2g3
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "address": {
    "city": null,
    "country": "CR",
    "line1": null,
    "line2": null,
    "postalCode": null,
    "state": null
  },
  "amountSpent": 0,
  "createdAt": "2022-06-12T21:21:10.587Z",
  "description": "Cliente creado para demostración",
  "email": "email@onvopay.com",
  "lastTransactionAt": null,
  "mode": "test",
  "name": "Nombre del cliente",
  "phone": null,
  "shipping": {
    "name": null,
    "phone": null,
    "address": {
      "city": null,
      "country": null,
      "line1": null,
      "line2": null,
      "postalCode": null,
      "state": null
    }
  },
  "transactionsCount": 0,
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Actualizar un Cliente
```
POST /v1/customers/:id
```

Actualiza el cliente indicado usando los parámetros enviados. Parámetros no enviados no se cambiarán. 

#### Parámetros

___
##### address _optional_
La dirección del cliente.

**Parámetros:**
###### address.city _optional_
Nombre de ciudad o pueblo.
###### address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### address.line2 _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### address.postalCode _optional_
Código postal o código ZIP.
###### address.state _optional_
Estado, provincia o región.

___
##### description _optional_
Texto arbitrario adjunto al objeto. Comúnmente útil para mostrar a usuarios.
___
##### email _optional_
La dirección de correo electrónico del cliente.
___
##### name _optional_
El nombre completo del cliente
___
##### phone _optional_
El número de teléfono del cliente, incluyendo código de área (Ej: +50688880000)
___
##### shipping _optional_
La dirección de entrega a domicilio del cliente.

**Parámetros:**
###### shipping.address.city _optional_
Nombre de ciudad o pueblo.
###### shipping.address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### shipping.address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### shipping.address.line2 _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### shipping.address.postalCode _optional_
Código postal o código ZIP.
###### shipping.address.state _optional_
Estado, provincia o región.
###### shipping.name _optional_
Nombre del cliente.
###### shipping.phone_optional_
Teléfono del cliente (incluyendo extensión).

**Retorna:**
Retorna el objeto de Cliente, si la actualización fue satisfactoria. Retorna un error si los parámetros son inválidos (Ej: Enviando `Costa Rica` en lugar de `CR`, para el parámetro de `address.country`).

```
POST /v1/customers/cl40muorw00493ndp0okzk2g3
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 
{ 
  "name": "Nombre del cliente actualizado"
}
```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "address": {
    "city": null,
    "country": "CR",
    "line1": null,
    "line2": null,
    "postalCode": null,
    "state": null
  },
  "amountSpent": 0,
  "createdAt": "2022-06-12T21:21:10.587Z",
  "description": "Cliente creado para demostración",
  "email": "email@onvopay.com",
  "lastTransactionAt": null,
  "mode": "test",
  "name": "Nombre del cliente actualizado",
  "phone": null,
  "shipping": {
    "name": null,
    "phone": null,
    "address": {
      "city": null,
      "country": null,
      "line1": null,
      "line2": null,
      "postalCode": null,
      "state": null
    }
  },
  "transactionsCount": 0,
  "updatedAt": "2022-06-12T21:49:20.129Z",
}
```
### Borrar un Cliente
```
DELETE /v1/customers/:id
```
#### Parámetros

___
Sin parámetros.

**Retorna:**
Permanentemente elimina el cliente. No se puede deshacer y automáticamente cancela cualquier suscripción activa que pueda tener el cliente.

```
DELETE /v1/customers/cl40muorw00493ndp0okzk2g3
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "deleted": true
}
```
### Listar todos los clientes
```
GET /v1/customers
```
#### Parámetros

##### createdAt _optional_
Un filtro basado en el atributo de `createdAt`

**Parámetros:**
###### createdAt.gt _optional_
Retorna los resultados donde `createdAt` es mayor que el valor enviado. 
###### createdAt.gte _optional_
Retorna los resultados donde `createdAt` es mayor o igual que el valor enviado. 
###### createdAt.lt _optional_
Retorna los resultados donde `createdAt` es menor que el valor enviado. 
###### createdAt.lte _optional_
Retorna los resultados donde `createdAt` es menor o igual que el valor enviado. 

___
##### email _optional_
Un filtro de la lista basado en el correo electrónico del cliente. El valor debe de ser `string`.
___
##### endingBefore _optional_
Un cursor usado para paginación. `endingBefore` es el id de un objeto de Cliente que define el punto actual en la lista. Por ejemplo, si hacés una solicitud que recibe 100 objetos, empezando con un objeto de id `cl40muorw00493ndp0okzk2g3`, la solicitud siguiente puede incluir `endingBefore=cl40muorw00493ndp0okzk2g3` para obtener la anterior página de la lista. 
___

##### limit _optional_
Un límite en la cantidad de objetos a retornar. Puede ser un valor entre 1 y 100, el valor por defecto es 10.
___
##### startingAfter _optional_
Un cursor usado para paginación. `startingAfter` es el id de un objeto de Cliente que define el punto actual en la lista. Por ejemplo, si hacés una solicitud que recibe 100 objetos, terminando con un objeto de id `cl40muorw00493ndp0okzk2g3`, la solicitud siguiente puede incluir `startingAfter=cl40muorw00493ndp0okzk2g3` para obtener la siguiente página de la lista. 
___
**Retorna:**
Retorna una lista de objetos de Cliente.

```
GET /v1/customers?createdAt[gte]=2022-06-01T21:00:00.000Z&email=email@onvopay.com&limit=3
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
{
  "data": [
    {
      "id": "cl40muorw00493ndp0okzk2g3",
      "address": {
        "city": null,
        "country": "CR",
        "line1": null,
        "line2": null,
        "postalCode": null,
        "state": null
      },
      "amountSpent": 0,
      "createdAt": "2022-06-12T21:21:10.587Z",
      "description": "Cliente creado para demostración",
      "email": "email@onvopay.com",
      "lastTransactionAt": null,
      "mode": "test",
      "name": "Nombre del cliente actualizado",
      "phone": null,
      "shipping": {
        "name": null,
        "phone": null,
        "address": {
          "city": null,
          "country": null,
          "line1": null,
          "line2": null,
          "postalCode": null,
          "state": null
        },
      },
      "transactionsCount": 0,
      "updatedAt": "2022-06-12T21:49:20.129Z",
    },
    { ... },
    { ... },
  ],
  "meta": {
    "total": 20,
    "pages": 7,
    "limit": 3,
    "cursorNext": "cl26qre4o019801lhjl7qdj7e",
    "cursorBefore": "cl40muorw00493ndp0okzk2g3"
  }
}
```


___
## Métodos de pago

Este objeto representa los métodos de pago de tus clientes

### Endpoints

POST /v1/payment-methods
GET /v1/payment-methods/:id
POST /v1/payment-methods/:id
GET /v1/payment-methods
POST /v1/payment-methods/:id/detach
GET /v1/customers/:customerId/payment-methods

### El objeto Método de Pago

#### Atributos


___
##### id _string_
Identificador único del objeto.
___
##### bankAccount _hash_
La información sobre la cuenta IBAN, cuando el tipo de método de pago es `bank_account`.

**Atributos:**
###### bankAccount.currency _string_
La moneda de la cuenta bancaria. Puede ser `CRC` o `USD`.
###### bankAccount.entity _string_
El nombre de la entidad bancaria a la que pertenece la cuenta.
###### bankAccount.maskedIBAN _string_
El número de la cuenta IBAN, con los dígitos parcialmente ocultos.
___
##### billing _hash_
La dirección de facturación del método de pago.

**Atributos:**
###### billing.address.city _string_
Nombre de ciudad o pueblo.
###### billing.address.country _string_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### billing.address.line1 _string_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### billing.address.line2 _string_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### billing.address.postalCode _string_
Código postal o código ZIP.
###### billing.address.state _string_
Estado, provincia o región.
###### billing.email _string_
Correo del cliente.
###### billing.name _string_
Nombre del cliente.
###### billing.phone _string_
Teléfono del cliente (incluyendo extensión).
___
##### card _hash_
La información sobre la tarjeta de crédito o débito, cuando el tipo de método de pago es `card`.

**Atributos:**
###### card.brand _string_
El nombre de la marca de la tarjeta. Puede ser `visa` o `mastercard`.
###### card.expMonth _string_
El mes de expiración de la tarjeta.
###### card.expYear _string_
El año de expiración de la tarjeta.
###### card.last4 _string_
Los últimos cuatro dígitos del número de la tarjeta.
___
##### createdAt _datetime_
Fecha y hora, en UTC, en la que fue creado el objeto. 
___
##### mobileNumber _hash_
La información sobre el número para SINPE Móvil, cuando el tipo de método de pago es `mobile_number`.

**Atributos:**
###### mobileNumber.maskedNumber _string_
El número de teléfono, con los dígitos parcialmente ocultos.
___
##### mode _string_
El modo en el que existen los datos del objeto. Ya sea `test` o `live`.
___
##### status _string_
El estado actual del método de pago. Puede ser uno de los siguientes:

A la espera de autorización automática: `awaiting_authorization`. Es un estado para los métodos de pago de tipo `bank_account`. Es determinado por un proceso que se concreta automáticamente, sin necesidad de intervención del usuario. Una vez concretado, el estado cambia a `active` o `requires_verification`, si aún no ha sido verificado. 

Requiere verificación: `requires-verification`. Es un estado para los métodos de pago de tipo `bank_account`. Estos métodos de pago requieren que el cliente verifique su cuenta bancaria antes de que se pueda realizar una transacción, como medida de seguridad para proteger la cuenta bancaria ante usos fraudulentos.

Activo: `active`: Es el estado en el que los métodos de pago pueden ser utilizados para realizar transacciones. Es el estado por defecto para los métodos de pago de tipo `mobile_number` y `card`.

Detached: `detached`. Es el estado en el que quedan los métodos de pago luego de haber sido removidos de un cliente. Este estatus es irreversible y el método de pago no se puede volver a utilizar.

Suspended: `suspended`. Es un estado para los métodos de pago que han recibido una suspensión por parte de la plataforma. Estos métodos de pago no pueden ser utilizados para realizar transacciones.
___

##### type _string_
El tipo de método de pago. Puede ser uno de los siguientes:
Tarjetas de crédito/débito VISA o MASTERCARD: `card`
SINPE IBAN: `bank_account`
SINPE Móvil: `mobile_number`
___
##### updatedAt _datetime_
Fecha y hora, en UTC, en la que fue actualizado por última vez el objeto. 
___

```json 
{
  "id": "string",
  "bankAccount": {
    "currency": "string",
    "entity": "string",
    "maskedIBAN": "string"
  },
  "billing": {
    "address": {
      "city": "string",
      "country": "string",
      "line1": "string",
      "line2": "string",
      "postalCode": "string",
      "state": "string"
    },
    "email": "string",
    "name": "string",
    "phone": "string",
  },
  "card": {
    "brand": "string",
    "last4": "string",
    "expMonth": 12,
    "expYear": 2022
  },
  "createdAt": "2022-06-12T21:21:10.587Z",
  "mobileNumber": {
    "maskedNumber": "string",
  },
  "mode": "string",
  "status": "string",
  "type": "string",
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Crear un Método de Pago
```
POST /v1/payment-methods
```

#### Parámetros

___
##### bankAccount _optional_
La información sobre la cuenta IBAN, requerido cuando el tipo de método de pago es `bank_account`.

**Atributos:**
###### bankAccount.identification _required_
El número de identificación asociado a la cuenta SINPE. 
___
###### bankAccount.identificationType _required_
El tipo de identificación asociado a la cuenta SINPE. 
___
###### bankAccount.IBAN _required_
El número de la cuenta IBAN.
___
##### billing _optional_
La dirección de facturación del método de pago.

**Parámetros:**
###### billing.address.city _optional_
Nombre de ciudad o pueblo.
###### billing.address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### billing.address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### billing.address.line2  _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### billing.address.postalCode _optional_
Código postal o código ZIP.
###### billing.address.state _optional_
Estado, provincia o región.
###### billing.email _optional_
Correo del cliente.
###### billing.name _optional_
Nombre del cliente.
###### billing.phone _optional_
Teléfono del cliente (incluyendo extensión).
___
##### card _optional_
La información sobre la tarjeta de crédito o débito, requerido cuando el tipo de método de pago es `card`.

**Parámetros:**
###### card.holderName _required_
El nombre del titular de la tarjeta.
###### card.expMonth _required_
El mes de expiración de la tarjeta.
###### card.expYear _required_
El año de expiración de la tarjeta.
###### card.number _required_
El número de la tarjeta de crédito o débito.

___

##### mobileNumber _optional_
La información sobre el número para SINPE Móvil, requerido cuando el tipo de método de pago es `mobile_number`.

**Parámetros:**
###### mobileNumber.identification _required_
El número de identificación asociado a la cuenta de SINPE Móvil. 
___
###### mobileNumber.identificationType _required_
El tipo de identificación asociado a la cuenta de SINPE Móvil. 
___
###### mobileNumber.number _required_
El número de teléfono asociado a SINPE Móvil.
___
##### type _required_
El tipo de método de pago. Puede ser uno de los siguientes:
Tarjetas de crédito/débito VISA o MASTERCARD: `card`
SINPE IBAN: `bank_account`
SINPE Móvil: `mobile_number`
___

**Retorna:**
Retorna el objeto de Método de Pago, si la creación fue satisfactoria. Retorna un error si los parámetros son inválidos (Ej: Enviando un parámetro diferente a `bank_account`, `card`,  o `mobile_number` para `type`).

```
POST /v1/payment-methods
Authorization: Bearer onvo_test_publishable_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 
{ 
  "card": {
    "cvc": "123",
    "expMonth": 12,
    "expYear": 2022,
    "holderName": "Juan Pérez",
    "number": "4242424242424242",
  },
  "type": "card",
}
```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "card": {
    "brand": "Visa",
    "last4": "4199",
    "expMonth": 12,
    "expYear": 2022
  },
  "createdAt": "2022-06-12T21:21:10.587Z",
  "customerId": "cl40muorw00493ndp0okzk2g3",
  "mode": "test",
  "status": "active",
  "type": "card",
  "updatedAt": "2022-06-12T21:21:10.587Z",
}

```
### Obtener un Método de Pago
```
GET /v1/payment-methods/:id
```
#### Parámetros

___
Sin parámetros.

**Retorna:**
Retorna el objeto de Método de Pago para un id válido. 

```
GET /v1/payment-methods/cl40muorw00493ndp0okzk2g3
Authorization: Bearer onvo_test_publishable_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
 {
  "id": "cl40muorw00493ndp0okzk2g3",
  "card": {
    "brand": "Visa",
    "last4": "4199",
    "expMonth": 12,
    "expYear": 2022
  },
  "createdAt": "2022-06-12T21:21:10.587Z",
  "customerId": "cl40muorw00493ndp0okzk2g3",
  "mode": "test",
  "status": "active",
  "type": "card",
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Actualizar un Método de Pago
```
POST /v1/payment-method/:id
```

Actualiza el método de pago indicado usando los parámetros enviados. Parámetros no enviados no se cambiarán. 

#### Parámetros

___
##### billing _optional_
La dirección de facturación del método de pago.

**Parámetros:**
###### billing.address.city _optional_
Nombre de ciudad o pueblo.
###### billing.address.country _optional_
El código de país en dos caracteres (ISO 3166-1 alpha-2).
###### billing.address.line1 _optional_
Primera línea de la dirección. (Ej: Calle, nombre de empresa).
###### billing.address.line2  _optional_
Segunda línea de la dirección. (Ej: Edificio, apartamento, número de casa).
###### billing.address.postalCode _optional_
Código postal o código ZIP.
###### billing.address.state _optional_
Estado, provincia o región.
###### billing.email _optional_
Correo del cliente.
###### billing.name _optional_
Nombre del cliente.
###### billing.phone _optional_
Teléfono del cliente (incluyendo extensión).
___
##### card _optional_
La información sobre la tarjeta de crédito o débito, requerido cuando el tipo de método de pago es `card`.

**Parámetros:**
###### card.expMonth _required_
El mes de expiración de la tarjeta.
###### card.expYear _required_
El año de expiración de la tarjeta.
___

**Retorna:**
Retorna el objeto de Método de Pago, si la actualización fue satisfactoria. Retorna un error si los parámetros son inválidos (Ej: Enviando `Costa Rica` en lugar de `CR`, para el parámetro de `billing.address.country`).

```
POST /v1/payment-methods/cl40muorw00493ndp0okzk2g3
Authorization: Bearer onvo_test_publishable_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 
{ 
  "card": {
    "expYear": 2023,
  }
}
```
`Respuesta:`
```json 
 {
  "id": "cl40muorw00493ndp0okzk2g3",
  "card": {
    "brand": "Visa",
    "last4": "4199",
    "expMonth": 12,
    "expYear": 2023
  },
  "createdAt": "2022-06-12T21:21:10.587Z",
  "customerId": "cl40muorw00493ndp0okzk2g3",
  "mode": "test",
  "status": "active",
  "type": "card",
  "updatedAt": "2022-06-12T21:49:20.129Z",
}

```
### Desconectar un Método de Pago
```
POST /v1/payment-methods/:id/detach
```
#### Parámetros

___
Sin parámetros.

**Retorna:**
Permanentemente desconecta el método de pago. No se puede deshacer y no se puede volver a conectar ni utilizar en futuras transacciones.

```
POST /v1/payment-methods/cl40muorw00493ndp0okzk2g3/detach
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
{
  "id": "cl40muorw00493ndp0okzk2g3",
  "status": "detached",
}
```
### Listar todos los métodos de pago de un cliente
```
GET /v1/customers/:customerId/payment-methods
```
#### Parámetros

##### endingBefore _optional_
Un cursor usado para paginación. `endingBefore` es el id de un objeto de Cliente que define el punto actual en la lista. Por ejemplo, si hacés una solicitud que recibe 100 objetos, empezando con un objeto de id `cl40muorw00493ndp0okzk2g3`, la solicitud siguiente puede incluir `endingBefore=cl40muorw00493ndp0okzk2g3` para obtener la anterior página de la lista. 
___

##### limit _optional_
Un límite en la cantidad de objetos a retornar. Puede ser un valor entre 1 y 100, el valor por defecto es 10.
___
##### startingAfter _optional_
Un cursor usado para paginación. `startingAfter` es el id de un objeto de Cliente que define el punto actual en la lista. Por ejemplo, si hacés una solicitud que recibe 100 objetos, terminando con un objeto de id `cl40muorw00493ndp0okzk2g3`, la solicitud siguiente puede incluir `startingAfter=cl40muorw00493ndp0okzk2g3` para obtener la siguiente página de la lista. 
___
**Retorna:**
Permanentemente un listado con los métodos de pago del cliente.

```
GET /v1/customers/cl40muorw00493ndp0okzk2g/payment-methods&limit=3
Authorization: Bearer onvo_test_secret_key_VL3ln7fwTC1DiJGvGE0H5A-XYPNJDmoGtwcduXYTRtsuKRc4d1PXEh33Ju9RZRXGJkX0KsRV5-F540ciRCQosQ
```
```json 

```
`Respuesta:`
```json 
{
  "data": [
     {
      "id": "cl40muorw00493ndp0okzk2g3",
      "card": {
        "brand": "Visa",
        "last4": "4199",
        "expMonth": 12,
        "expYear": 2023
      },
      "createdAt": "2022-06-12T21:21:10.587Z",
      "customerId": "cl40muorw00493ndp0okzk2g3",
      "mode": "test",
      "status": "active",
      "type": "card",
      "updatedAt": "2022-06-12T21:49:20.129Z",
    }
    { ... },
    { ... },
  ],
  "meta": {
    "total": 5,
    "pages": 2,
    "limit": 3,
    "cursorNext": "cl26qre4o019801lhjl7qdj7e",
    "cursorBefore": "cl40muorw00493ndp0okzk2g3"
  }
}
```


___
## Payment Intents
## Subscriptions
## Subscription Items
## Prices
## Products
## Coupons
## Promotion Codes
## Checkout Sessions
## Payment Links
## Shipping Rates
## Refunds
