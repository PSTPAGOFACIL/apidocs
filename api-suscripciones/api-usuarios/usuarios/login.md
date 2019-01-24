# Login

### Endpoints

* Producción:  [https://api-app.pgf.cl/prod](https://api-app.pgf.cl/prod)
* Beta: [https://api-app.pgf.cl/beta](https://api-app.pgf.cl/beta)
* Desarrollo: [https://api-app.pgf.cl/dev](https://api-app.pgf.cl/dev)

El inicio de sesión como usuario se puede realizar de dos formas:

* Proporcionando usuario y password
* A través de un token de acceso previamente creado

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="login" %}
{% api-method-summary %}
/login
{% endapi-method-summary %}

{% api-method-description %}
Método de inicio de sesión mediante usuario y password
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
Username o Email del usuario
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Password del usuario
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "access_token_jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwczovL3NwYWpkei5hdXRoMC5jb20vIiwic3ViIjoiYXV0aDB8NWMwYzU5MGJkZjNiMGU2YjdjNDMwZWI1IiwiYXVkIjpbImFwcC51c3Vhcmlvcy5zdXNjcmlwY2lvbmVzLnBmYXV0aDAuY29tIl0sImlhdCI6MTU0NTI1Mzg1MiwiZXhwIjoxNTQ1MzQwMjUyLCJhenAiOiJKSVJkM1N4S3FPTE95UHJ0aHc5dUt1M0tEN215RnRkZCIsInNjb3BlIjoib3BlbmlkIHByb2ZpbGUiLCJndHkiOiJwYXNzd29yZCJ9.J_Zm_GiPcDvpDn9nBr9Lasddddd",
    "expires_in": 86400,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

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

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="loginToken" %}
{% api-method-summary %}
Login Token
{% endapi-method-summary %}

{% api-method-description %}
Método de inicio de sesión mediante token de acceso previamente creado
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token de acceso \(Bearer\) asociado a la cuenta del usuario
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

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

{% endapi-method-response-example-description %}

```javascript
{
    "error": "Invalid Authorization Header"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

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

{% api-method method="post" host="https://api-app.pgf.cl/prod/" path="tokens/createToken" %}
{% api-method-summary %}
Create Token
{% endapi-method-summary %}

{% api-method-description %}
Método que permite crear un token de acceso. Para realizar la llamada a este método se debe iniciar sesión previamente
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Token JWT de autorización
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "User": "USERID",
    "access_token": "TUACCESSTOKEN",
    "expiration_date": 1697730996,
    "token_type": "Bearer"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

