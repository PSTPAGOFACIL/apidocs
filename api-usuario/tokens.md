---
description: >-
  Los tokens de autenticación son usados para generar los tokens JWT de manera
  segura sin necesidad de exponer los datos críticos del usuario. ( Usuario /
  Password ).
---

# Tokens de Autenticación

{% api-method method="post" host="https://api.pgf.cl" path="/tokens/createToken" %}
{% api-method-summary %}
createToken
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite crear un Access Token con el que podemos loguearnos en el API y crear un Token JWT.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Un Token JWT Válido asociado a tu usuario en Pago Fácil.  \)\(Bearer\).
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Access Token creado de manera exitosa.
{% endapi-method-response-example-description %}

```javascript
{
    "User": "USERID",
    "access_token": "TUACCESSTOKEN",
    "expiration_date": 1697730996,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No pudo ser verificado tu token de acceso JWT.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Invalid Token"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



