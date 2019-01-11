---
description: Conexiones a la API de suscripciones y de registros de tarjetas.
---

# Suscripciones

### Endpoints

Producción: [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)

Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)

Desarrollo Suscripciones: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/" path="login" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}
Login de Usuarios en la plataforma
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Password del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username o email del usuario
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

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/" path="registrar" %}
{% api-method-summary %}
Registrar usuario
{% endapi-method-summary %}

{% api-method-description %}
Permite registrar un usuario en la plataforma
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
username del usuario \(máximo 100 caracteres\)
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

```javascript
{
    "message": "Se registro el usuario",
    "usuatio_token": "f8f75799-1b87-4161-9d3a-55aba8da7123"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
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

```javascript
{
    statusCode: 409,
    message: "Usuario ya existe"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/subscriptions/" path="getAll" %}
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

```javascript
{
    "message": "Suscripciones encontradas con exito",
    "suscripciones": [
        {
            "token": "a6e4ffc9-e595-4e10-8bb7-5863a7558152",
            "email": "stephanie@pagofacil.cl",
            "estado": "SIN ACTIVAR",
            "estado_cobro": null,
            "descripcion_boton": "test",
            "recurrencia": "12",
            "boton_token": "132cbdfd-ea43-4573-b74a-be68f26485ec",
            "codigo": "ZjgwOTdg4rUtM2RiYy00N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOmFmOGJlZWQ2LTcwMzMtNDc3NS1iOTI5LWUyYjQ4ZjY0N2I3NQ=="
        }
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    error: "Error al obtener las suscripciones por email"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/subscriptions" path="/create" %}
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

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)
* Para más información sobre como obtener el boton\_token revisar [Obtener Botones](botones-de-suscripciones.md#obtener-botones-de-suscripcion)

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/subscriptions" path="/activar" %}
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

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)
* Para más información sobre como obtener usuario\_oc\_token revisar[ Obtener Tarjetas](tarjetas.md#obtener-tarjetas)
* Para más información sobre como obtener el token de la suscripción revisar [Obtener Suscripciones](suscripciones.md#obtener-suscripciones)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/subscriptions" path="/desactivar" %}
{% api-method-summary %}
Desactivar suscripción
{% endapi-method-summary %}

{% api-method-description %}
Permite desactivar una suscripción
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

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)
* Para más información sobre como obtener el boton\_token revisar [Obtener Botones](botones-de-suscripciones.md#obtener-botones-de-suscripcion)
* Para más información sobre como obtener el token de la suscripción revisar[ Obtener Suscripciones](suscripciones.md#obtener-suscripciones)

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/user" path="/verificar-usuario-boton" %}
{% api-method-summary %}
Verificar usuario y botón
{% endapi-method-summary %}

{% api-method-description %}
Verifica si un usuario ya esta suscrito a un botón especifico
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

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)
* Para más información sobre como obtener el boton\_token revisar [Obtener Botones](botones-de-suscripciones.md#obtener-botones-de-suscripcion)



