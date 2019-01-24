---
description: Método que retorna una dirección en específico
---

# Obtener dirección

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="htps://api-app.pgf.cl/prod/" path="users/directions/getDirection" %}
{% api-method-summary %}
/users/directions/getDirection
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
    "message": "Se encontró la dirección exitosamente",
    "direccion": {
        "idAuth0": "auth0|5g7745gt8u5a4cb52btc235a",
        "token": "aa838fh2-6bef-4a52-ad48-6c7356701699",
        "depto": "33",
        "estado": "ACTIVO",
        "ciudad": "Santiago",
        "direccion": "Direccion 3"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Direccion no existe, esta deshabilitada o no tienes acceso"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token de la dirección sigue el siguiente link:

{% page-ref page="obtener-direcciones.md" %}

