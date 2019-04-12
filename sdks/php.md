# PHP

### 

#### Instalación

Para realizar la instalación de la librería se recomienda hacer uso de composer mediante el comando:

```text
composer require pagofacil/php-sdk
```

#### Uso

Para realizar el uso de la librería se debe, en primera instancia cargar el archivo autoload que genera el composer:

```php
include_once 'vendor/autoload.php';
```

Luego de esto se deben realizar los llamados a las clases Request y Transaction mediante sus namespaces, quedando el código de la siguiente manera:

```php
include_once 'vendor/autoload.php';
use PagoFacil\lib\Request;
use PagoFacil\lib\Transaction;
```

Una vez que se tienen importadas las clases necesarias se inicia el proceso para generar un pago, para esto se debe crear una variable tipo request, en donde se deben completar los parámetros necesarios para iniciar la transacción de la siguiente manera:

```php
$request = new Request(); // Se crea el objeto Request

$request->account_id = ''; // Token Service entregado por Pago Facil
$request->amount = 0; // Monto de la transaccion
$request->currency = 'CLP'; // Moneda de la transaccion
$request->reference = ''; // Numero de orden de la tienda
$request->customer_email = ''; // Email del cliente
$request->url_complete = ''; // URL a la cual se redirecciona el sistema
$request->url_cancel = ''; // URL de cancelacion
$request->url_callback = ''; // URL de response 
$request->shop_country = 'CL'; // ISO Code de pais
$request->session_id = date('Ymdhis').rand(0,9).rand(0,9).rand(0,9); // ID de Session, Max 61 caracteres. Se recominda que sea un valor dificil de replicar

```

Luego de tener esta variable se crea una nueva transacción a la cual se le pasa por parámetro la variable request creada anteriormente:

```php
$transaction = new Transaction($request); // Se crea la transaccion
$transaction->environment = 'DESARROLLO'; // Se especifica el ambiente en el cual se va a trabajar, puede ser DESSARROLLO, BETA o PRODUCCION

$transaction->setToken(''); // Se debe colocar el Token Secret entregado por Pago Facil

$transaction->initTransaction($request); // Se inicia la transaccion enviando por parametros el request creado
```

Al realizar la llamada a initTransaction el sistema redirecciona a pago fácil para realizar la transacción, una vez realizada el sistema enviara mediante POST un response a la url especificada en url\_callback. En este punto se debe verificar que tanto la firma como el monto concuerde.

Para verificar la firma se puede hacer uso de la funcion validate\(\) de la transacción, a esta función se le pasa por parámetros un arreglo con los datos recibidos del POST, por ejemplo:

```php
$transaction = new Transaction();
$transaction->setToken(''); // Se debe colocar el Token Secret entregado por Pago Fácil

if($transaction->validate($_POST)){
  error_log('TRANSACCION CORRECTA');
}else{
  error_log('ERROR FIRMA');
}
```

Luego de realizar el validate se debe realizar una verificación del monto recibido para tener mayor seguridad de la respuesta, así como cualquier otra verificación que se desee realizar.

Si la respuesta esta OK el sistema enviara a la url especificada en url\_complete, una vez en esa dirección se debe verificar nuevamente que la firma y monto correspondan, por ejemplo:

```php
$transaction = new Transaction();
$transaction->setToken(''); // Se debe colocar el Token Secret entregado por Pago Fácil

if($transaction->validate($_POST)){
  echo 'Orden recibida exitosamente';
  error_log('TRANSACCION CORRECTA');
}else{
  echo 'Error en firma';
  error_log('ERROR FIRMA');
}

```

Luego de realizar el validate se debe realizar una verificación del monto recibido para tener mayor seguridad de la respuesta, así como cualquier otra verificación que se desee realizar.

