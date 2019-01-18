---
description: Permite registrar un usuario en el sistema
---

# Registrar

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="registrar" %}
{% api-method-summary %}
Registrar
{% endapi-method-summary %}

{% api-method-description %}
Método que permite registrar un usuario
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="rec\_email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password del usuario.   
Debe cumplir los siguientes criterios:  
  
- Mínimo de 8 caracteres  
- Al menos 1 caracter en minúscula \(a-z\)  
- Al menos 1 caracter en mayúscula \(A-Z\)  
- Al menos un numero \(0-9\)  
- Al menos un caracter especial \(!@\#$%^&\*\)
{% endapi-method-parameter %}

{% api-method-parameter name="rec\_nombre" type="string" required=false %}
Nombre del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="rec\_apellido" type="string" required=false %}
Apellido del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="rec\_fono" type="string" required=false %}
Teléfono del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="rec\_rut" type="string" required=false %}
RUT del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se registro el usuario",
    "usuatio_token": "f8f75799-1b87-4161-9d3a-55aba8da7123"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    statusCode: 400,
    error: "<Nombre del error>",
    message: "<Mensaje de error>"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    statusCode: 409,
    message: "Usuario ya existe"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

