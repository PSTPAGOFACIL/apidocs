---
description: Método que permite obtener las suscripciones de un usuario
---

# Obtener Suscripciones

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="subscriptions/getAll" %}
{% api-method-summary %}
/subscriptions/getAll
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
            "tarjeta_token": "324ht5fr-hy67-8876-fr43-ygt566485o9",
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
    error: "Error al obtener las suscripciones"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Para más información sobre como obtener el token de autorización ver el siguiente link:

{% page-ref page="../usuarios/login.md" %}

