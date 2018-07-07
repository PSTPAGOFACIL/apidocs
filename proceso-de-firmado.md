# Proceso de Firmado

## ¿ Cómo funciona ?

Para validar que la información sea enviada desde la persona que corresponda, esta se verifica a través de una firma generada por el algoritomo  [HMAC SHA256](https://es.wikipedia.org/wiki/HMAC#Ejemplos_de_HMAC_%28MD5,_SHA1,_SHA256%29). Para generar esta firma se necesita una "**Clave Secreta**" que es proporcionada al generar el servicio en Pago Fácil. Cómo bien dice su nombre, esta clave es secreta y no debe de ser compartida con nadie, ya que esto podría causar que la información del estado de la transacción no sea fidedigna hacia el comercio.

{% hint style="warning" %}
Este proceso no es complejo pero es importante seguir los pasos en orden para que no se vuelva frustrante.
{% endhint %}

#### Proceso

1. Se debe de obtener un arreglo con todos las variables que comiencen con x\_ desde el body del POST \(AKA: Payload.\)
2. Este arreglo se debe de ordenar de manera alfabética.
3. Una vez obtenido el arreglo, se crea un string con todas las variables y sus valores concatenados.
4. El string resultando se firma con el algoritmo SHA256 mencionado anteriormente.

### Ejemplo en Ruby

```ruby
  def sign(fields, key=@key)
    Digest::HMAC.hexdigest(fields.sort.join, key, Digest::SHA256)
  end
```

### Ejemplo en JavaScript

```javascript
//Recuerda que el arreglo siempre debe de estar ordenado antes de firmar.
let sortedArray = Object.entries(payload).sort();

function signPayload(payload, secret, prefix = "x_", signature = "signature") {
    console.log("signPayload");
    let payloadFirmado;
    let firma = prefix + signature;
    let mensaje = "";
    for (let index = 0; index < payload.length; index++) {
        console.log(payload[index]);
        if (payload[index][0] != firma) {
            mensaje += payload[index][0] + payload[index][1];
        }
    }
    let hmac = crypto.createHmac('sha256', secret);
    hmac.setEncoding('hex');
    hmac.write(mensaje);
    hmac.end();
    payloadFirmado = hmac.read();
    return payloadFirmado;
}
```

### Ejemplo en PHP

```php
function firmarArreglo($arreglo) {
    //Ordeno Arreglo
    ksort($arreglo);
    //Concateno Arreglo
    $mensaje = $this->concatenarArreglo($arreglo);
    //Firmo Mensaje
    $mensajeFirmado = $this->firmarMensaje($mensaje, $this->ct_token_secret);
    //Guardo y retorno el mensaje firmado
    $this->ct_firma = $mensajeFirmado;
    return $mensajeFirmado;
}
function firmarMensaje($mensaje, $claveCifrado) {
    $mensajeFirmado = hash_hmac('sha256', $mensaje, $claveCifrado);
    return $mensajeFirmado;
}
public function concatenarArreglo($arreglo) {
    $resultado = "";
    foreach ($arreglo as $field => $value) {
        $resultado .= $field . $value;
    }
    return $resultado;
}
```

