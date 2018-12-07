---
description: Conexiones a la API de suscripciones y de registros de tarjetas
---

# Suscripciones

### Endpoints

Desarrollo Suscripciones: [https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/](https://0g3bkdv10a.execute-api.us-west-2.amazonaws.com/dev/) 

Desarrollo Registro: [https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/](https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/)



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
            "codigo": "ZjgwOTdhMTUtM2RiYy00N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOmFmOGJlZWQ2LTcwMzMtNDc3NS1iOTI5LWUyYjQ4ZjY0N2I3NQ=="
        },
        {
            "email": "stephanie@pagofacil.cl",
            "estado": "ACTIVO",
            "estado_cobro": null,
            "descripcion_boton": "Desde Dashboard",
            "recurrencia": "20",
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
{% api-method-parameter name="codigo" type="string" required=true %}
Código para desactivar, se encuentra en el response de obtener las suscripciones
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
    responseCode: 2,
    message : "Se encontraron tarjetas",
    existe: true,
    tarjetas : [
        {
            token : "fc27a987-3999-4b5b-b24e-b210c0fee8a0",
            usuario_oc_token : "059a21be-755b-4d08-9998-f70148f219e2",
            card : "6623"
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

{% api-method method="get" host="https://dusvl5v59l.execute-api.us-west-2.amazonaws.com/dev/registrar" path="/:codigo\_comercio/:email" %}
{% api-method-summary %}
Registrar tarjeta
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="codigo\_comercio" type="string" required=true %}
Código al cual se va a registrar la tarjeta, este es devuelto por el método verificar usuario botón cuando el usuario no esta registrado
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
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

