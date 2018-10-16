---
description: >-
  Este endpoint retorna los detalles de la transacción asociada a uno de los
  servicios de tu cuenta en Pago Fácil.
---

# Detalles de la Transacción

{% api-method method="get" host="https://api.pgf.cl" path="/trx-details/:id" %}
{% api-method-summary %}
Get Transaction Details
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Incluye el token obtenido en la etapa de Login de la API \(Bearer\)
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name=":id" type="string" required=true %}
El ID de la transacción en mall \( id en Pago Fácil \) de la cual se quiere obtener mayor información.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Detalles de la Transacción retornados de manera exitosa.
{% endapi-method-response-example-description %}

```javascript
{
    "idUser": "IDUSUARIO",
    "idTrx": "332637",
    "details": {
        "idTrxs": "332637",
        "source": "WebpayPST",
        "details": {
            "accountingDate": "1016",
            "detailOutput": {
                "amount": "20000",
                "authorizationCode": "XXXX",
                "sharesNumber": 0,
                "commerceCode": "CODIGOCOMERCIO",
                "paymentTypeCode": "VD",
                "buyOrder": "332637",
                "responseCode": 0
            },
            "cardDetail": {
                "cardNumber": "0064"
            },
            "sessionId": "201810116028",
            "transactionDate": {},
            "buyOrder": "332637",
            "VCI": "TSY",
            "urlRedirection": "https://webpay3g.transbank.cl:443/webpayserver/voucher.cgi"
        },
        "timestamp": 1539721866107
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
No existen permisos para acceder a la transacción o transacción inexistente.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "Sin permisos para acceder a la transaccion"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



