# Crear Suscripción

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="subscriptions/create" %}
{% api-method-summary %}
/subscriptions/create
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
{% api-method-parameter name="direccion\_token" type="string" required=false %}
Token de la dirección
{% endapi-method-parameter %}

{% api-method-parameter name="variacion\_id" type="string" required=false %}
ID de la variación  
  
**EN CASO DE QUE EL BOTÓN SEA TIPO RECURRENTE VARIABLE EL CAMPO ES OBLIGATORIO**
{% endapi-method-parameter %}

{% api-method-parameter name="producto\_id" type="string" required=false %}
ID del producto  
  
**EN CASO DE QUE EL BOTÓN SEA TIPO RECURRENTE VARIABLE EL CAMPO ES OBLIGATORIO**
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="boton\_token" type="string" required=true %}
Token del botón asociado a la suscripción
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "message": "Se creo la suscripcion",
    "token": "17dd41e0-f399-45b0-953b-7b652a8f4f7a"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    error: "Error al crear la suscripción"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

* Para más información sobre como obtener el token de acceso sigue el link:

{% page-ref page="../usuarios/login.md" %}

* Para más información sobre como obtener el token del botón sigue el siguiente link:

{% page-ref page="../../api-comercios/botones-de-suscripciones.md" %}

