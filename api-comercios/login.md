---
description: >-
  Todas las llamadas al Servicio de APIs deben de estar autentificadas a través
  de un token JWT ( JSON Web Tokens ).
---

# Login

### Como obtener los Tokens JWT

Los tokens  JWT pueden ser obtenidos a través de un API Call a login usando usuario y clave o con un token de autentificación creado previamente. Estos tokens de autentifcación deben de ser creados previamente en el dashboard, o pueden ser creados  a través del API.

### Endpoints

* Producción: [https://api.pgf.cl ](https://api.pgf.cl)
* Desarrollo: [https://api-dev.pgf.cl](https://api-dev.pgf.cl)

## Login

Como mencionamos, se puede ingresar al sistema de dos maneras. Usando el login con usuario y clave, o a través de los tokens de autentificación. Sin embargo, el login usando usuario y clave tiene un tiempo de vida de 24 horas, mientras que el usando tokens es válido por el periodo determinado por el usuario.

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
    "access_token_jwt": "TU JWT TOKEN",
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

#### Ejemplos

{% code title="Ejemplo de conexión usando CURL" %}
```bash
curl -X POST \
  https://api.pgf.cl/login \
  -H 'Cache-Control: no-cache' \
  -H 'Content-Type: application/json' \
  -d '{
	"username":  "MIMAILOUSUARIO",
	"password" : "MICLAVE"
}'
```
{% endcode %}

{% code title="Ejemplo usando Javascript." %}
```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://api.pgf.cl/login',
  headers: 
   { 'Cache-Control': 'no-cache',
     'Content-Type': 'application/json' },
  body: 
   { username: 'MIMAILOUSUARIO',
     password: 'MICLAVE' },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```
{% endcode %}

{% code title="Ejemplo usando PHP" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.pgf.cl/login",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\n\t\"username\":  \"MIMAILOUSUARIO\",\n\t\"password\" : \"MICLAVE
\"\n}",
  CURLOPT_HTTPHEADER => array(
    "Cache-Control: no-cache",
    "Content-Type: application/json",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```
{% endcode %}

{% api-method method="post" host="https://api.pgf.cl" path="/loginToken" %}
{% api-method-summary %}
/loginToken
{% endapi-method-summary %}

{% api-method-description %}
Este tipo de login retorna un token JWT con el que se pueden usar las llamadas por un periodo determinado por el usuario. En caso de no ser especificado será usado por un año.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token asociado a tu cuenta \(Bearer\)
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="expDate" type="number" required=false %}
Fecha en UNIX TIMESTAMP hasta cuando será valido el token JWT. De no ser especificado el token durará un año.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
El caso de éxito responde el token que ocuparemos y en cuanto tiempo expirará.
{% endapi-method-response-example-description %}

```javascript
{
    "access_token_jwt": "TU JWT TOKEN",
    "expires_in": 31536000,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Si el token usado en la autorización no es válido.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "Invalid Authorization Header"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Si el token no está habilitado o si está expirado.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "Not a valid or expired token"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Ejemplos

{% code title="Curl" %}
```bash
curl -X POST \
  https://api.pgf.cl/loginToken \
  -H 'Authorization: Bearer TUACCESSTOKEN' \
  -H 'Cache-Control: no-cache' 
```
{% endcode %}

{% code title="JavaScript" %}
```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'https://api.pgf.cl/loginToken',
  headers: 
   { 'Cache-Control': 'no-cache',
     Authorization: 'Bearer TUACCESSTOKEN' } };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});

```
{% endcode %}

{% code title="PHP" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.pgf.cl/loginToken",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer e0a7eefa-de1a-4507-82f5-eb9ec482fe2a",
    "Cache-Control: no-cache",
    "Postman-Token: 585cef54-e002-4791-8bd2-b9ce58d1cf6b"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```
{% endcode %}

