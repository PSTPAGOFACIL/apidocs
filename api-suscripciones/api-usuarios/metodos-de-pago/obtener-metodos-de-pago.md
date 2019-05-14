# Obtener métodos de pago



### Endpoints

* Producción: [https://api-app.pgf.cl/prod/user/getMetodosPago](https://api-app.pgf.cl/prod/user/getMetodosPago)
* Beta: [https://api-app.pgf.cl/beta/user/getMetodosPago](https://api-app.pgf.cl/beta/user/getMetodosPago)
* Desarrollo: [https://api-app.pgf.cl/dev/user/getMetodosPago](https://api-app.pgf.cl/dev/user/getMetodosPago)

{% api-method method="post" host="https://api-app.pgf.cl/prod/user/getMetodosPago" path="/user/getMetodosPago" %}
{% api-method-summary %}
/user/getMetodosPago
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
    "status": "OK",
    "message": "Métodos de pago",
    "data": {
        "metodos": [
            "OneclickMall",
            "WebPay",
            "Khipu",
            "Multicaja",
            "Pago46"
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

