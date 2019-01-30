---
description: Método que permite obtener el estado de una tarjeta
---

# Estado de Tarjeta

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/user" path="/estadoTarjeta" %}
{% api-method-summary %}
/user/estadoTarjeta
{% endapi-method-summary %}

{% api-method-description %}
Permite obtener el estado de una tarjeta mediante un código de verificación
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="codigo" type="string" required=true %}
Código de verificación de la tarjeta
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se encontro la tarjeta",
    "estado": "ACTIVO"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    error : "Error al obtener tarjeta"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el código de verificación sigue el siguiente link:

{% page-ref page="obtener-tarjetas.md" %}

