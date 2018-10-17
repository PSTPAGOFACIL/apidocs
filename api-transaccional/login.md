---
description: >-
  Todas las llamadas al Servicio de APIs deben de estar autentificadas a través
  de un token JWT ( JSON Web Tokens )
---

# Login

### Endpoints

* https://api.pgf.cl Para Producción
* https://api-dev.pgf.cl Para Desarrollo

{% api-method method="post" host="https://api.pgf.cl" path="/login" %}
{% api-method-summary %}
/login
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint retorna un token valido por 24 horas con el que se pueden realizar las llamadas al resto de los endpoints del API. Sin este token no se pueden acceder a los endpoints.  
  
Los parámetros deben ser enviados a través de un JSON.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
Nombre del usuario o email en la plataforma
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password del usuario en la plataforma
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
El token fue obtenido de manera correcta.
{% endapi-method-response-example-description %}

```javascript
{
    "access_token": "TU JWT TOKEN",
    "expires_in": 86400,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
No se pudo validar la combinación email/username con la clave.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "Wrong email or password."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



