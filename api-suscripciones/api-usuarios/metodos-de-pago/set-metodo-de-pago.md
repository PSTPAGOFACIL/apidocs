# Set método de pago

### Endpoints

* Producción: [https://api-app.pgf.cl/prod/user/setMetodoPredefinido](https://api-app.pgf.cl/prod/user/setMetodoPredefinido)
* Beta: [https://api-app.pgf.cl/beta/user/setMetodoPredefinido](https://api-app.pgf.cl/beta/user/setMetodoPredefinido)
* Desarrollo: [https://api-app.pgf.cl/dev/user/setMetodoPredefinido](https://api-app.pgf.cl/dev/user/setMetodoPredefinido)

{% api-method method="post" host="https://api-app.pgf.cl/dev/user/setMetodoPredefinido" path="/user/setMetodoPredefinido" %}
{% api-method-summary %}
/user/setMetodoPredefinido
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
{% api-method-parameter name="metodo" type="string" required=true %}
Nombre del tipo de pago 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "status": "OK",
    "message": "Se agregó el metodo predefinido correctamente"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

