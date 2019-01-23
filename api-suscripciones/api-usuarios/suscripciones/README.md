---
description: Métodos para administrar las suscripciones
---

# Suscripciones

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

Para acceder a los métodos de la API es necesario tener un token JWT de autorización. Para saber como obtener este token seguir el siguiente link:

{% page-ref page="../usuarios/login.md" %}

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

* Para más información sobre como obtener el token de autorización revisar [Login](./#login)
* Para más información sobre como obtener usuario\_oc\_token revisar[ Obtener Tarjetas](../tarjetas.md#obtener-tarjetas)
* Para más información sobre como obtener el token de la suscripción revisar [Obtener Suscripciones](./#obtener-suscripciones)

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

* Para más información sobre como obtener el token de autorización revisar [Login](./#login)
* Para más información sobre como obtener el boton\_token revisar [Obtener Botones](../../api-comercios/botones-de-suscripciones.md#obtener-botones-de-suscripcion)
* Para más información sobre como obtener el token de la suscripción revisar[ Obtener Suscripciones](./#obtener-suscripciones)

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

* Para más información sobre como obtener el token de autorización revisar [Login](./#login)
* Para más información sobre como obtener el boton\_token revisar [Obtener Botones](../../api-comercios/botones-de-suscripciones.md#obtener-botones-de-suscripcion)



