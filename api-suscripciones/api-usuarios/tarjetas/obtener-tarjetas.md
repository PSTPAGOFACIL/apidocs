---
description: Método que retorna todas las tarjetas activas de un usuario
---

# Obtener Tarjetas

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="user/getTarjetas" %}
{% api-method-summary %}
/user/getTarjetas
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
    "responseCode": 2,
    "message": "Se encontraron tarjetas",
    "existe": true,
    "tarjetas": [
        {
            "token": "5a3491f2-d90d-4085-901b-006bfac16ee2",
            "card_type": "Visa",
            "last4CardDigits": "XXXXXXXXXXXX6623",
            "codigo_verificacion": "ZjgwOTdhMTUtM2RiYy40N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOmFmOGJlZWQ2LTcwMzMtNDc3NS1iOTI5LWTRDjQ4ZjY0N2I3NQ"
        },
        {
            "token": "6a1a6931-af7c-4818-ada2-fff0d81e88ef",
            "card_type": "Visa",
            "last4CardDigits": "XXXXXXXXXXXX6623",
            "codigo_verificacion": "ZjgwOTdhMTUtM2RiYy40N2QyLTkxMGYtZGQ0NzEyMTUyNWRkOmFmOGJlZWQ2LTcwMzMtNDc3NS1iOTI5LWTRDjQ4ZjY0N2I3NQ"
       
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
    error: "Error al realizar la solicitud"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

