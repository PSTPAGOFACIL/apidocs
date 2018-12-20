---
description: Conexiones para administrar los botones de suscripciones
---

# Botones de suscripciones

### Endpoints

Desarrollo: [https://api-dev.pgf.cl/](https://api-dev.pgf.cl/subscription/create-button)

### Login

Para crear un nuevo botón de suscripciones primero se debe hacer login como comercio. Para tener mayor información sobre como realizar el login mediante API revisar la documentación de [Login](../api-usuario/login.md#login)

### Crear Botón

Este método permite la creación de un botón de suscripciones, el botón puede ser de tipo recurrente o de tipo servicio.

{% api-method method="post" host="https://api-dev.pgf.cl/subscription/" path="create-button" %}
{% api-method-summary %}
Crear Botón
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



