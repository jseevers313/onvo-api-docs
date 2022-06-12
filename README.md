# API DOCS

## Referencia API

El API de ONVO utiliza **REST**. Nuestro API tiene URLs orientadas a recursos predecibles, acepta **JSON** en el cuerpo de las solicitudes así como también es el formato codificado de sus respuestas. 

## Referencia API

El API de ONVO utiliza **REST**. Nuestro API tiene URLs orientadas a recursos predecibles, acepta **JSON** en el cuerpo de las solicitudes así como también es el formato codificado de sus respuestas. 

| Base URL    |
| ----------- |
| https://api.onvopay.com |   

Podés usar el API de ONVO en modo de prueba, que no afecta los datos del modo en vivo, ni interactúa con las redes bancarias. El API Key que usés para la autenticación de la solicitud determina si la solicitud será de modo de prueba o en vivo.


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

Este objecto representa un cliente de tu comercio. Te permite crear cargos recurrentes y rastrear pagos que pertenecen al mismo cliente. 

### Endpoints
POST   /v1/customers
GET    /v1/customers/:id
POST   /v1/customers/:id
DELETE /v1/customers/:id
GET    /v1/customers

### El objecto Cliente

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
##### createdAt _datetime_
Fecha y hora en la que fue creado el objecto en UTC. 
___
##### description _string_
Texto arbitrario adjunto al objecto. Comúnmente útil para mostrar a usuarios.
___
##### email _string_
La dirección de correo electrónico del cliente.
___
##### mode _string_
El modo en el que existen los datos del objecto. Ya sea `test` o `live`.
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
##### updatedAt _datetime_
Fecha y hora en la que fue actualizado por última vez el objecto en UTC. 
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
  "createdAt": "2022-06-12T21:21:10.587Z",
  "description": "string",
  "email": "string",
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
  "updatedAt": "2022-06-12T21:21:10.587Z",
}
```
### Crear un Cliente

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
Texto arbitrario adjunto al objecto. Comúnmente útil para mostrar a usuarios.
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

___
## Payment Methods
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
