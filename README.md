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
Nombre de ciudad o pueblo.
###### address.postalCode _string_
Código postal o código ZIP.
###### address.state _string_
Estado, provincia o región.
___
##### description _string_
Texto arbitrario adjunto al objecto. Comúnmente útil para mostrar a usuarios
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
