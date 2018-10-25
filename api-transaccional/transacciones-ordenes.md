---
description: Acá podrás encontrar todas las APIs relacionadas a las transacciones.
---

# Transacciones // Ordenes

{% api-method method="post" host="https://api.pgf.cl" path="/trxs/create" %}
{% api-method-summary %}
Create Transaction
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite crear una nueva transacción mientras que retorna el id de esta y la url en dónde realizar el pago.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Token JWT de Autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="x\_shop\_country" type="string" required=false %}
País de donde se realiza la transacción. Por defecto CL.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_url\_callback" type="string" required=true %}
URL en dónde se enviará la información relacionada al pago de la transacción.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_url\_cancel" type="string" required=true %}
URL en dónde se redireccionará al usuario en caso de cancelar.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_url\_complete" type="string" required=true %}
Url a dónde se redireccionará el usuario al momento de pago exitoso.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_customer\_email" type="string" required=true %}
Email del cliente a quién se le cobra. Se le enviará el comprobante a este correo.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_reference" type="string" required=true %}
ID de la transacción en tu plataforma.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_currency" type="string" required=false %}
Divisa de la transacción. Por defecto CLP.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_account\_id" type="string" required=true %}
Id del servicio con el cual se genera la orden.
{% endapi-method-parameter %}

{% api-method-parameter name="x\_amount" type="number" required=true %}
Monto de la transacción. Acepta Decimales si la divisa lo permite.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Se crea la transacción de manera exitosa.
{% endapi-method-response-example-description %}

```javascript
{
    "idTrx": 337756,
    "payUrl": "https://gw.pagofacil.cl/payTransaction/?Authorization=MzM3NzU2OjMwMTE0Mjg="
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
La transacción ya ha sido creada con anterioridad.
{% endapi-method-response-example-description %}

```javascript
{
    "idTrx": 337756,
    "x_account_id": "5",
    "x_reference": "ABCDEF1234356",
    "error": "TRX Ya existe."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Servicio no existe, o no existen permisos de acceso relacionados.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "Servicio Inexistente, Deshabilitado, o Sin Acceso por el usuario."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.pgf.cl" path="/trxs/status/:id" %}
{% api-method-summary %}
Estado de una orden
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint retorna el estado de una orden si es que esta existe y tienes autorización de acceso.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="number" required=false %}
Corresponde al ID de la transacción en Pago Fácil
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "idTrx": 332405,
    "idService": 77,
    "amount": "20000.00",
    "status": "completed",
    "source" : "WebPayPST",
    "createdAt": "2018-10-16T16:50:27.000Z",
    "updatedAt": "2018-10-16T16:56:18.000Z"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "error": "TRX inexistente o no tienes permisos."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "error": "Error Obteniendo TRX"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

