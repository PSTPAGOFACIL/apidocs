---
description: Método que permite remover una tarjeta
---

# Remover Tarjeta

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod​/user/" path="remove-tarjeta" %}
{% api-method-summary %}
/user/remove-tarjeta
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

* Para más información sobre como obtener el token de autorización sigue el siguiente link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token de la tarjeta sigue el siguiente link:

{% page-ref page="obtener-tarjetas.md" %}

