---
description: Método para cambiar la dirección asociada a una suscripción
---

# Cambiar dirección de la suscripción

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="subscriptions/changeDirection" %}
{% api-method-summary %}
/subscriptions/changeDirection
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
{% api-method-parameter name="token" type="string" required=true %}
Token de la suscripción a desactivar
{% endapi-method-parameter %}

{% api-method-parameter name="direccion\_token" type="string" required=true %}
Token de la dirección
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se cambió la dirección de la suscripción"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    error: "Suscripción no existe o no tienes accesos para acceder"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    error: "<Mensaje de error>"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



* Para más información sobre como obtener el token de autorización sigue el siguiente link:

  {% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token de la suscripción sigue el siguiente link:

  {% page-ref page="obtener-suscripciones.md" %}

* Para más información sobre como obtener el token de la dirección sigue el siguiente link:

  {% page-ref page="../direcciones/obtener-direcciones.md" %}

