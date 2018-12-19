---
description: Conexiones a la API de suscripciones y de registros de tarjetas.
---

# Suscripciones

### Endpoints

Desarrollo Suscripciones: [https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/](https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/) 

Desarrollo Registro: [https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/](https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/)

### Login

Permite realizar login de los usuarios

{% api-method method="post" host=" https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/" path="login" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
password del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "access_token_jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwczovL3NwYWpkei5hdXRoMC5jb20vIiwic3ViIjoiYXV0aDB8NWMwYzU5MGJkZjNiMGU2YjdjNDMwZWI1IiwiYXVkIjpbImFwcC51c3Vhcmlvcy5zdXNjcmlwY2lvbmVzLnBmYXV0aDAuY29tIl0sImlhdCI6MTU0NTI1Mzg1MiwiZXhwIjoxNTQ1MzQwMjUyLCJhenAiOiJKSVJkM1N4S3FPTE95UHJ0aHc5dUt1M0tEN215RnRkZCIsInNjb3BlIjoib3BlbmlkIHByb2ZpbGUiLCJndHkiOiJwYXNzd29yZCJ9.J_Zm_GiPcDvpDn9nBr9Lasddddd",
    "expires_in": 86400,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "error": "Wrong email or password."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Registrar Usuario

Permite registrar un usuario

{% api-method method="post" host=" https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/" path="registrar" %}
{% api-method-summary %}
Registrar usuario
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
username del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
contraseña del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se registro el usuario",
    "usuatio_token": "f8f75799-1b87-4161-9d3a-55aba8da7123"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    statusCode: 400,
    error: "<Nombre del error>",
    message: "<Mensaje de error>"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    statusCode: 409,
    message: "Usuario ya existe"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Obtener suscripciones

Permite obtener todas las suscripciones de un usuario

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/subscriptions/" path="getAll" %}
{% api-method-summary %}
Obtener Suscripciones
{% endapi-method-summary %}

{% api-method-description %}
Obtiene todas las suscripciones asociadas a un usuario
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Suscripciones encontradas con exito",
    "suscripciones": [
        {
            "email": "stephanie@pagofacil.cl",
            "estado": "SIN ACTIVAR",
            "estado_cobro": null,
            "descripcion_boton": "test",
            "recurrencia": "12",
            "boton_token": "15dcbdfd-ea43-4573-b74a-be68f26485ec",
            "codigo": "ZjgwOTdhMTUtM2RiYy00N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOmFmOGJlZWQ2LTcwMzMtNDc3NS1iOTI5LWUyYjQ4ZjY0N2I3NQ=="
        },
        {
            "email": "stephanie@pagofacil.cl",
            "estado": "ACTIVO",
            "estado_cobro": null,
            "descripcion_boton": "Desde Dashboard",
            "recurrencia": "20",
            "boton_token": "15dcbdfd-ea43-4573-b74a-be68f26485ec",
            "codigo": "ZjgwOTdhMTUtM2RiYy00N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOjc3ZDgyMDRmLTQ3NjctNDExMy1iMzQ5LTQ3ZmU3YmZiOWEzYg=="
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al obtener las suscripciones por email"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Crear Suscripción

Permite crear una suscripción

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/subscriptions" path="/create" %}
{% api-method-summary %}
Crear suscripción 
{% endapi-method-summary %}

{% api-method-description %}
Crea una suscripción asociada a un botón de suscripciones
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="boton\_token" type="string" required=true %}
Token del botón al cual va a estar asociada la suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se creo la suscripcion"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al obtener las suscripciones por email"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Activar Suscripción

Permite activar una suscripción

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/subscriptions" path="/activar" %}
{% api-method-summary %}
Activar suscripción
{% endapi-method-summary %}

{% api-method-description %}
Permite activar una suscripción indicando la tarjeta a usar
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="usuario\_oc\_token" type="string" required=true %}
Token de la tarjeta a la cual se va a asociar la transacción
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Token de la suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    message: "Se activo la suscripcion"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "no se pudo realizar la solicitud"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Desactivar Suscripción

Permite desactivar una suscripción

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/subscriptions" path="/desactivar" %}
{% api-method-summary %}
Desactivar suscripción
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="boton\_token" type="string" required=true %}
Token del botón de suscripción
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Token de la suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    message: "Se desactivo la suscripcion"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al desactivar suscripcion"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Obtener tarjetas

Obtiene todas las tarjetas asociadas al usuario

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/user" path="/getTarjetas" %}
{% api-method-summary %}
Obtener tarjetas
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "responseCode": 2,
    "message": "Se encontraron tarjetas",
    "existe": true,
    "tarjetas": [
        {
            "token": "5a3491f5-d90d-4085-901b-006bfac16ee2",
            "card_type": "Visa",
            "last4CardDigits": "6623"
        },
        {
            "token": "6a0a6931-af7c-4818-ada2-fff0d81e88ef",
            "card_type": "Visa",
            "last4CardDigits": "6623"
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al realizar la solicitud"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Verificación de suscripción

Verifica si un usuario ya esta suscrito a un botón específico

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/user" path="/verificar-usuario-boton" %}
{% api-method-summary %}
Verificar usuario y botón
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="boton\_token" type="string" required=true %}
Token del botón de suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    responseCode: 3,
    message: "Usuario ya se encuentra habilitado para realizar suscripcion",
    usuario_token: "059a21be-755b-4d08-9998-f70148f219e2",
    existe : true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    responseCode: 1,
    message : "Usuario no existe",
    existe: false,
    comercio: "123123123"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Registrar Tarjeta

Registra una tarjeta del usuario

{% api-method method="post" host="https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/registrar" path="" %}
{% api-method-summary %}
Registrar tarjeta
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="callbackUrl" type="string" required=true %}
Url a la cual se va a redireccionar luego de agregar la tarjeta
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="codigo\_comercio" type="string" required=true %}
Código al cual se va a registrar la tarjeta, este es devuelto por el método verificar usuario botón cuando el usuario no esta registrado
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ 
  success: 'true',
  usuario_token: '094b1dfc-7472-4f57-9122-a6b8f45cc52e',
  tokenSecret: '0bcf51f3-c166-4efa-abae-70c10090ab7d',
  username: 'holahola12344testcom',
  message: 'Inscripcion realizada con exito',
  errorCode: '0' 
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "success": false,
    "errorMessage": "No se pudo completar la transaccion",
    "errorCode": 3
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Obtener transacciones del usuario

Obtiene todas las transacciones del usuario

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/" path="transactions/getAll" %}
{% api-method-summary %}
Obtener transacciones
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización 
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se encontraron transacciones",
    "Count": 5,
    "trxs": [
        {
            "hash": "9c935b82-92d2-4828-ac17-bba70e5b38bd",
            "idTrx": "3866",
            "timestamp": 1544212415130,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NjozMzM3NTMz",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "7853b79c-439f-47ba-be25-6199f5bde4af",
            "idTrx": "3865",
            "timestamp": 1544211165011,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NTozNjQzNjY1",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "386713e8-3b3a-4781-9976-8de58904cd5b",
            "idTrx": "3863",
            "timestamp": 1544206599671,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2MzoxNTMwOTM5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "35c2803c-9373-4c0c-9f4a-866259843891",
            "idTrx": "3867",
            "timestamp": 1544212511335,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2Nzo2MDkwMDM5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "838371a7-f297-4994-b41a-90634d3c0f2d",
            "idTrx": "3864",
            "timestamp": 1544210647370,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NDo0MjIyMzc5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al obtener las transacciones del usuario"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Remover Tarjetas

Permite remover una tarjeta

{% api-method method="post" host="https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/remove" path="" %}
{% api-method-summary %}
Remover Tarjeta
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="callbackUrl" type="string" required=true %}
Url a la que se va a redireccionar luego de eliminar la tarjeta
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Token de la tarjeta
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ 
    success: true, 
    errorCode: 0
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

{ 
    success: false, 
    errorCode: 3
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Obtener transacciones por usuario y suscripción

Permite obtener las transacciones de una suscripción

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/" path="transactions/getBySubscription" %}
{% api-method-summary %}
Obtener Transacciones por Suscripción
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="idSubscription" type="string" required=true %}
Token de la suscripción
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se encontraron transacciones",
    "Count": 5,
    "trxs": [
        {
            "hash": "9c935b82-92d2-4828-ac17-bba70e5b38bd",
            "idTrx": "3866",
            "timestamp": 1544212415130,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NjozMzM3NTMz",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "7853b79c-439f-47ba-be25-6199f5bde4af",
            "idTrx": "3865",
            "timestamp": 1544211165011,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NTozNjQzNjY1",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "386713e8-3b3a-4781-9976-8de58904cd5b",
            "idTrx": "3863",
            "timestamp": 1544206599671,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2MzoxNTMwOTM5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "35c2803c-9373-4c0c-9f4a-866259843891",
            "idTrx": "3867",
            "timestamp": 1544212511335,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2Nzo2MDkwMDM5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        },
        {
            "hash": "838371a7-f297-4994-b41a-90634d3c0f2d",
            "idTrx": "3864",
            "timestamp": 1544210647370,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=Mzg2NDo0MjIyMzc5",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-5863a7558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al obtener las transacciones del usuario"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Obtener estado de tarjeta

Permite verificar el estado de una tarjeta mediante un código de verificación

{% api-method method="post" host="https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/user" path="/estadoTarjeta" %}
{% api-method-summary %}
Obtener estado de tarjeta
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="codigo" type="string" required=true %}
Código de verificación de la tarjeta
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se encontro la tarjeta",
    "estado": "ACTIVO"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error : "Error al obtener tarjeta"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Realizar pago

{% api-method method="post" host="https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/" path="authorization" %}
{% api-method-summary %}
Realizar pago
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="monto" type="integer" required=true %}
Monto a cobrar
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="tbk\_user" type="string" required=true %}
Tbk del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="codigo\_comercio" type="string" required=true %}
Codigo de comercio
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



