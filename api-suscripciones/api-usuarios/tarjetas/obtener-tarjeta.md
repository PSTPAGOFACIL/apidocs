---
description: Método que permite obtener información de una tarjeta
---

# Obtener Tarjeta

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="get" host="https://api-app.pgf.cl/prod/" path="user/getTarjeta/:token" %}
{% api-method-summary %}
/user/getTarjeta/:token
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
Token de la tarjeta a consultar
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "tarjeta": {
        "token": "87a654b4-68f4-365e-8da6-aab361f130a7",
        "usuario_token": "43fb60e9-11a9-458f-bfbe-b21c648b363c",
        "email": "ejemplo@gmail.com",
        "estado": "ACTIVO",
        "cardType": "Visa",
        "cardNumber": "XXXXXXXXXXXX6621",
        "cardOrigin": "NATIONAL_CARD"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "error": "No existe tarjeta o usuario no tiene accesos para ejecutar esta accion"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    message: "Error al obtener tarjeta"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de acceso sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token de la tarjeta sigue el siguiente link:

{% page-ref page="obtener-tarjetas.md" %}

