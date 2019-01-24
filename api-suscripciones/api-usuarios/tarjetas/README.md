---
description: Conexiones para administrar las tarjetas de los usuarios
---

# Tarjetas

### Endpoints

Producción: [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)

Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)

Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

### Tarjetas de Prueba transbank

|  |  |
| :--- | :--- |
| Numero de tarjeta | 4051885600446623 |
| Año de expiración | Cualquiera |
| Mes de Expiración | Cualquiera |
| CVV | 123 |

{% api-method method="post" host="https://api-app.pgf.cl/prod​/" path="user/registrar-tarjeta" %}
{% api-method-summary %}
Registrar Tarjeta
{% endapi-method-summary %}

{% api-method-description %}
Permite registrar una tarjeta. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="callbackUrl" type="string" required=true %}
URL a la cual se redireccionará al usuario una vez se registra la tarjeta. Esta url sera llamada por método GET y se adicionará un código de verificación con el cual se puede obtener el estado del registro de la tarjeta.   
  
**La url debe ir sin "/" al final.**
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email del usuario al cual se va a agregar la tarjeta
{% endapi-method-parameter %}

{% api-method-parameter name="codigo\_comercio" type="string" required=true %}
Código de comercio al cual se asociara la tarjeta. Este código se puede obtener del método "Verificar Usuario Botón"
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el código de comercio revisar [Verificar Usuario Botón](../suscripciones/#verificar-usuario-y-boton)
* Para más información sobre como obtener el token de autorización revisar [Login](../suscripciones/#login)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/user/" path="remove-tarjeta" %}
{% api-method-summary %}
Remover Tarjeta  
{% endapi-method-summary %}

{% api-method-description %}
Permite eliminar una tarjeta
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorizacion
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="callbackUrl" type="string" required=true %}
URL a la cuál se redireccionará al usuario una vez que se elimine la tarjeta.  Esta URL será llamada por método GET y se adicionará un código de verificación con el cual se puede obtener el estado de la tarjeta.  
  
**La url debe ir sin "/" al final.**
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Token de la tarjeta
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de la tarjeta revisar [Obtener Tarjetas](./#obtener-tarjetas)

{% api-method method="post" host=" https://api-app.pgf.cl/prod​/user" path="/estadoTarjeta" %}
{% api-method-summary %}
Estado de tarjeta
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

* Para más información sobre como obtener el token de autorización revisar [Login](../suscripciones/#login)
* Para mas información sobre como obtener el código de verificación revisar [Obtener Tarjetas](./#obtener-tarjetas)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/user" path="/cobrar" %}
{% api-method-summary %}
Realizar cobro
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
{% api-method-parameter name="codigo\_verificacion" type="string" required=true %}
Código de verificación de tarjeta
{% endapi-method-parameter %}

{% api-method-parameter name="suscripcion\_token" type="string" required=true %}
Token de suscripción
{% endapi-method-parameter %}

{% api-method-parameter name="monto" type="number" required=true %}
Monto a cobrar.   
  
**Este valor debe ser mayor o igual a 1000.**
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se realizo el cobro"
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

* Para más información sobre como obtener el token de autorización revisar [Login](../suscripciones/#login)
* Para más información sobre como obtener el código de verificación revisar [Obtener Tarjetas](./#obtener-tarjetas)
* Para más información sobre como obtener el token de suscripción revisar[ Obtener Suscripciones](../suscripciones/#obtener-suscripciones)

