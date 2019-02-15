---
description: Permite obtener el codigo postal
---

# Obtener Código Postal

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod" path="/getZipCode" %}
{% api-method-summary %}
/getZipCode
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="calle" type="string" required=false %}
Calle
{% endapi-method-parameter %}

{% api-method-parameter name="numero" type="string" required=false %}
Numero de la calle
{% endapi-method-parameter %}

{% api-method-parameter name="comuna" type="string" required=false %}
Nombre de la comuna
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "zip": 8330251,
    "address": "AVENIDA SANTA ROSA",
    "number": "265",
    "commune": "SANTIAGO"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

