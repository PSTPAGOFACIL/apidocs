---
description: Conexiones para obtener las transacciones de los usuarios
---

# Transacciones

{% api-method method="post" host=" https://api-app.pgf.cl/" path="transactions/getAll" %}
{% api-method-summary %}
Obtener Transacciones
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
Transacciones del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se encontraron transacciones",
    "Count": 1,
    "trxs": [
        {
            "hash": "9c935b82-92d2-4828-a117-bba70e5b38bd",
            "idTrx": "3866111",
            "timestamp": 1544212415130,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=M1g2NjozMzM3NTMz",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-586317558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
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
    error: "<Mensaje de error>"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token revisar [Login](suscripciones.md#login)

{% api-method method="post" host=" https://api-app.pgf.cl/" path="transactions/getBySubscription" %}
{% api-method-summary %}
Obtener transacciones por suscripción
{% endapi-method-summary %}

{% api-method-description %}
Permite obtener las transacciones por suscripción
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

{% api-method-parameter name="idSubscription" type="string" required=true %}
Token de la suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se encontraron transacciones",
    "Count": 1,
    "trxs": [
        {
            "hash": "9c935b82-92d2-4828-a117-bba70e5b38bd",
            "idTrx": "3866111",
            "timestamp": 1544212415130,
            "amount": "15000",
            "payUrl": "https://gw-dev.pagofacil.cl/payTransaction/?Authorization=M1g2NjozMzM3NTMz",
            "idSubcription": "a6e4ffc9-e595-4e10-8bb7-586317558422",
            "subscription": "Nuevo boton de suscripcion recurrente"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización revisar [Login](suscripciones.md#login)
* Para más información sobre como obtener el id de suscripción revisar [Obtener Suscripciones](suscripciones.md#obtener-suscripciones)



