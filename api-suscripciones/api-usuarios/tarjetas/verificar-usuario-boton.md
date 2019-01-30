---
description: >-
  Método que permite verificar si un usuario tiene tarjeta registrada que pueda
  usar con un botón específico
---

# Verificar Usuario Botón

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="user/verificar-usuario-boton" %}
{% api-method-summary %}
/user/verificar-usuario-boton
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
Token del botón 
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

```javascript
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

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token del botón sigue el siguiente link:

{% page-ref page="../../api-comercios/botones-de-suscripciones.md" %}

