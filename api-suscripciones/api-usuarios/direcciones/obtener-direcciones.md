---
description: Método que retorna todas las direcciones de un usuario
---

# Obtener todas las direcciones

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="users/directions/getAll" %}
{% api-method-summary %}
/users/directions/getAll
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
    "message": "Se encontraron las direcciones",
    "count": 2,
    "direcciones": [
        {
            "idAuth0": "auth0|5ba500d49gh7122d847a3b87",
            "token": "588b1f48-9432-4ad3-a5b3-eeceb24458e9",
            "depto": "122",
            "estado": "ACTIVO",
            "ciudad": "Santiago",
            "direccion": "Direccion 1"
        },
        {
            "idAuth0": "auth0|5ba500d49gh7122d847a3b87",
            "token": "b18382e0-6aeu-4a67-ad48-6c7311701646",
            "depto": "33",
            "estado": "ACTIVO",
            "ciudad": "Santiago",
            "direccion": "Direccion 3"
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
    message: "No se encontraron direcciones",
    count: 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

