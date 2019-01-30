---
description: Método que permite registrar una tarjeta
---

# Registrar Tarjeta

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/" path="user/registrar-tarjeta" %}
{% api-method-summary %}
/user/registrar-tarjeta
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
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el código de comercio sigue el siguiente link:

{% page-ref page="verificar-usuario-boton.md" %}

