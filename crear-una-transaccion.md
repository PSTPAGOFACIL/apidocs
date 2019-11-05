---
description: Lista de funciones relacionadas a la creación y el pago de una transacción.
---

# Crear una Transacción

### initTransaction

Con este endpoint se inicializa una transacción a través de un método post generado por un formulario. Retorna una página con todos los métodos de pago disponibles para una divisa en particular.

#### Request initTransaction

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Variable</b>
      </th>
      <th style="text-align:left"><b>Requerida</b>
      </th>
      <th style="text-align:left"><b>Tipo</b>
      </th>
      <th style="text-align:left"><b>Descripci&#xF3;n</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">x_account_id</td>
      <td style="text-align:left">Si</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Corresponde al Token Service relacionado al servicio con el que deseas
        generar el cobro.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_amount</td>
      <td style="text-align:left">Si</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">Monto de la transacci&#xF3;n. Admite decimales si la divisa utilizada
        los utiliza.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_currency</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left"><a href="https://en.wikipedia.org/wiki/ISO_4217">ISO_4217</a>
      </td>
      <td style="text-align:left">
        <p>Divisa que se utilizar&#xE1; para la transacci&#xF3;n.</p>
        <p>Ejemplo: CLP, USD, BOB.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">x_reference</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&quot;T&#xFA;&quot; n&#xFA;mero de orden. Est&#xE9; n&#xFA;mero deber&#xED;a
        ser &#xFA;nico por servicio para no tener problema de duplicidad de pagos.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_customer_email</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Correo en d&#xF3;nde se enviar&#xE1; la confirmaci&#xF3;n de pago al cliente.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_url_complete</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Direcci&#xF3;n en d&#xF3;nde se redireccionar&#xE1; al momento de completar
        la transacci&#xF3;n. Se enviar&#xE1; un POST a esta URL con los mismos
        datos del callback explicado en la secci&#xF3;n response.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_url_cancel</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Direcci&#xF3;n en d&#xF3;nde se redireccionar&#xE1; en caso de cancelaci&#xF3;n.
        Se recomienda usar la direcci&#xF3;n del carrito de compras.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_url_callback</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Direcci&#xF3;n en donde se avisar&#xE1; de los cambios en la transacci&#xF3;n
        de manera asincr&#xF3;nica a trav&#xE9;s de un m&#xE9;todo POST.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_signature</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Mensaje Firmado. Por favor revisa la secci&#xF3;n de <a href="proceso-de-firmado.md#proceso">firmado</a> para
        saber como generarla.</td>
    </tr>
    <tr>
      <td style="text-align:left">x_shop_country</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left"><a href="https://en.wikipedia.org/wiki/ISO_3166-1">iso-3166-1alpha-2</a>
      </td>
      <td style="text-align:left">
        <p>Divisa que utiliza la tienda.</p>
        <p>Por ejemplo: CL, US.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">x_session_id</td>
      <td style="text-align:left">SI</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">Identificador &#xFA;nico de la sesi&#xF3;n del usuario que realiza el
        pago. Se agrega como capa de seguridad para validar la transacci&#xF3;n.
        Max. 61 caracteres.</td>
    </tr>
  </tbody>
</table>### Response initTransaction.

El response se ejecuta en dos ocasiones; como callback por detrás del flujo de pago hacia la url designada con este fin, además de al volver a la url complete también designada. Si bien no es necesario que verifiques la información en los dos momentos, lo recomendamos.

| Variable | Tipo | Descripción |
| :--- | :--- | :--- |
| x\_account\_id | String | Corresponde al Token Service relacionado al servicio con el que deseas generar el cobro. |
| x\_amount | Number | El monto asociado a la orden. Puede ser decimal en caso de que el currency lo permita. |
| x\_currency | String | Divisa que se utilizará para la transacción |
| x\_gateway\_reference | Number | Corresponde al ID de la transacción en la plataforma. \(BigInt\) |
| x\_reference | String | Corresponde al número de la orden en tu tienda. |
| x\_result | String | Estado de la orden. Pueden ser completed, failed, o pending. |
| x\_timestamp | String | Tiempo en que la orden fue completada en UTC. iso-8601 in UTC \(2018-03-24T12:15:41Z\) |
| x\_test | Boolean | Identifica si la orden fue realizada en el ambiente de pruebas. \(true/false\) |
| x\_signature | String | Mensaje Firmado. Por favor revisa la sección de [firmado](proceso-de-firmado.md#proceso) para saber como generarla. |

