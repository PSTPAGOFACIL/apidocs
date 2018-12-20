---
description: Conexiones para administrar los botones de suscripciones
---

# Botones de suscripciones

### Endpoints

Desarrollo: [https://api-dev.pgf.cl/](https://api-dev.pgf.cl/subscription/create-button)

### Login

Para crear un nuevo botón de suscripciones primero se debe hacer login como comercio. Para tener mayor información sobre como realizar el login mediante API revisar la documentación de [Login](../api-usuario/login.md#login)

{% api-method method="post" host="https://api-dev.pgf.cl/subscription/" path="create-button" %}
{% api-method-summary %}
Crear Botón
{% endapi-method-summary %}

{% api-method-description %}
Este método permite la creación de un botón de suscripciones, el botón puede ser de tipo recurrente o de tipo servicio
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="dia\_pago" type="number" required=false %}
Día de pago del mes en el cuál se realizará el cobro al cliente. **El valor del campo debe ser menor o igual a 28.  
  
Este campo solo aplica si el botón es de tipo Recurrente.**
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_recurrence" type="number" required=false %}
Período en días en el cual se realizará el cobro al cliente.  
  
Ejemplo:   
  
Si se envía 6, se realizará un cobro cada 6 días.  
  
**Este campo solo aplica si el botón es de tipo Recurrente.**
{% endapi-method-parameter %}

{% api-method-parameter name="cantidad\_pagos" type="number" required=false %}
Cantidad de pagos que se le van a realizar al cliente.  
  
**Este campo solo aplica si el botón es de tipo Recurrente.**
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=false %}
Monto a cobrar al usuario, este valor debe ser mayor a 1000.  
  
**En caso de el tipo de botón sea Recurrente este valor es OBLIGATORIO.  
  
Este campo solo aplica si el botón es de tipo Recurrente.**
{% endapi-method-parameter %}

{% api-method-parameter name="tipo" type="string" required=true %}
Tipo de botón, puede ser:  
  
- Recurrente  
- Servicio
{% endapi-method-parameter %}

{% api-method-parameter name="idService" type="string" required=true %}
ID de servicio en Pago Fácil
{% endapi-method-parameter %}

{% api-method-parameter name="access\_token" type="string" required=true %}
Token que se genera al hacer llamado a la función de crear token. Para mas información sobre como crear un token revisar documentación "Tokens de Autenticación"
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "message": "Se creó el boton de suscripción",
    "token": "46206a5a-b9a7-403d-a2d4-3bae221f41a2"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    error: "Error al crear el botón de suscripción"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización revisar [Login](../api-usuario/login.md#login-1)
* Para más información sobre como obtener el access\_token revisar [Create Token](../api-usuario/tokens.md#createtoken)

{% api-method method="post" host="https://api-dev.pgf.cl/subscription/" path="getAllButtons" %}
{% api-method-summary %}
Obtener Botones de suscripción
{% endapi-method-summary %}

{% api-method-description %}
Obtiene los botones de suscripción 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="idService" type="string" required=true %}
ID del servicio en Pago Fácil
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "responseCode": 2,
    "message": "Botones encontrados",
    "botones": [
        {
            "dia_pago": null,
            "tipo": "Servicio",
            "token": "912ba7c5-e756-40af-ae8b-619b08964e0a",
            "idService": "215",
            "timestamp": 1545160833551,
            "payment_recurrence": null,
            "amount": null,
            "description": "Testr",
            "estado": "ACTIVO",
            "access_token": "78e313660-6c24-4d52-b4f7-260907b53cf5"
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
    error: "<Mensaje de error>"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización revisar [Login](../api-usuario/login.md#login-1)



