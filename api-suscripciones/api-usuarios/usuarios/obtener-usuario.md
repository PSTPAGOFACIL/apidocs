---
description: Método que permite obtener los datos principales del usuario
---

# Obtener Usuario

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="get" host="https://api-app.pgf.cl/prod/" path="user/getData" %}
{% api-method-summary %}
/user/getData
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "usuario": {
        "token": "3dfb60e9-11d9-458f-a43e-b21c325a543b",
        "email": "ejemplo@gmail.cl",
        "estado": "ACTIVO",
        "nombre": "Nombre",
        "apellido": "Apellido",
        "telefono": "123123132"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    message: "Error al obtener usuario"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de acceso sigue el link: 

{% page-ref page="login.md" %}

