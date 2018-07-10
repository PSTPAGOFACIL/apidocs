---
description: Lista de funciones relacionadas a la creación y el pago de una transacción.
---

# Crear una Transacción

### initTransaction

Con este endpoint se inicializa una transacción a través de un método post generado por un formulario. Retorna una página con todos los métodos de pago disponibles para una divisa en particular.

#### Request initTransaction

| **Variable** | **Requerida** | **Tipo** | **Descripción** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| x\_account\_id | Si | String | Corresponde al Token Service relacionado al servicio con el que deseas generar el cobro. |
| x\_amount | Si | Number | Monto de la transacción. Admite decimales si la divisa utilizada los utiliza. |
| x\_currency | SI | String | Divisa que se utilizará para la transacción. Ejemplo ; CLP, USD, BOB. |
| x\_reference | SI | String | "Tú" número de orden. Esté número debería ser único por servicio para no tener problema de duplicidad de pagos. |
| x\_customer\_email | SI | String | Correo en dónde se enviará la confirmación de pago al cliente. |
| x\_url\_complete | SI | String | Dirección en dónde se redireccionará al momento de completar la transacción. Se enviará un POST a esta URL con los mismos datos del callback explicado en la sección response. |
| x\_url\_cancel | SI | String | Dirección en dónde se redireccionará en caso de cancelación. Se recomienda usar la dirección del carrito de compras. |
| x\_url\_callback | SI | String | Dirección en donde se avisará de los cambios en la transacción de manera asincrónica a través de un método POST. |
| x\_signature | SI | String | Mensaje Firmado. Por favor revisa la sección de [firmado](proceso-de-firmado.md#proceso) para saber como generarla. |
| x\_shop\_country | SI | [iso-3166-1alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1) | Por ejemplo CL // US  |
| x\_session\_id | SI | String | Identificador único de la sesión del usuario que realiza el pago. Se agrega como capa de seguridad para validar la transacción. |

### Response initTransaction.

El response se ejecuta en dos ocasiones; como callback por detrás del flujo de pago hacia la url designada con este fin, además de al volver a la url complete también designada. Si bien no es necesario que verifiques la información en los dos momentos, lo recomendamos.

| Variable | Tipo | Descripción |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| x\_account\_id | String | Corresponde al Token Service relacionado al servicio con el que deseas generar el cobro. |
| x\_amount | Number | El monto asociado a la orden. Puede ser decimal en caso de que el currency lo permita. |
| x\_currency | String | Divisa que se utilizará para la transacción |
| x\_gateway\_reference | Number | Corresponde al ID de la transacción en la plataforma. \(BigInt\) |
| x\_reference | String | Corresponde al número de la orden en tu tienda. |
| x\_result | String | Estado de la orden. Pueden ser completed, failed, o pending. |
| x\_timestamp | String | Tiempo en que la orden fue completada en UTC. iso-8601 in UTC \(2018-03-24T12:15:41Z\) |
| x\_test | Boolean | Identifica si la orden fue realizada en el ambiente de pruebas. \(true/false\) |
| x\_signature | String | Mensaje Firmado. Por favor revisa la sección de [firmado](proceso-de-firmado.md#proceso) para saber como generarla. |

