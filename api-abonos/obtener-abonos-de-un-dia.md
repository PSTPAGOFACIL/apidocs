# Obtener abonos de un dia

### Endpoints

* Producción: [https://api.pgf.cl](https://api.pgf.cl)
* Desarrollo: [https://api-dev.pgf.cl](https://api-dev.pgf.cl)

{% api-method method="post" host="https://api.pgf.cl/" path="remittances/getRemittance/:fecha" %}
{% api-method-summary %}
/remittances/getRemittance/:fecha
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="fecha" type="string" required=true %}
Fecha que se desea buscar en formato YYYY-MM-DD
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="limit" type="string" required=false %}
Cantidad de registros a buscar, por defecto es 10
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se encontraron remittances",
    "remittances": [
        {
            "idAuth0": "google-oauth2|555528313185555055555",
            "trxData": {
                "messageToAddressee": "Saldos Pago Facil IDXXX"
            },
            "clientData": {
                "rutAddressee": "111111111-1",
                "nameAddressee": "Cuenta Bancaria",
                "emailAddressee": "ejemplo@gmail.com"
            },
            "status": "processing",
            "timestamp": 1545609600,
            "amount": 15238,
            "bankData": {
                "bankSBIFNumber": "001",
                "bankAccountNumber": "110"
            }
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../api-comercios/login.md" %}

