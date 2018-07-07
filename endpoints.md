---
description: >-
  Acá podrás encontrar los distintos enpoints que se usarán para crear las
  transacciones.
---

# Endpoints

### Distinción de los ambientes

| **Ambiente** | **Descripción** |
| --- | --- | --- | --- |
| **Desarrollo** | Acá podrás hacer tus integraciones y pruebas. Toda la información usada en este servidor es completamente ficticia. |
| **Beta** | Estos endpoints funcionan con los datos de producción, pero tienen las nuevas funcionalidades que aún se están probando. Las funcionalidades como nuevos métodos de pago pueden cambiar antes de pasar al servidor de producción. |
| **Producción** | En este ambiente se encuentran todas las funcionalidades ya probadas y es posible que sea el único al que necesites acceder. |

### Dashboards

En los dashboards crearás los distintos servicios que usarás en la plataforma. Es importante saber que si bien los usuarios son los mismos para el servidor de desarrollo y producción, los servicios asociados son completamente distintos.

* Desarrollo : [http://dashboard-dev.pagofacil.cl](http://dashboard-dev.pagofacil.cl)
* Beta : [http://dashboard-beta.pagofacil.cl/](http://dashboard-beta.pagofacil.cl/)
* Producción : [https://dashboard.pagofacil.cl](https://dashboard.pagofacil.cl)

### Crear Transacción

Para poder [crear una transacción](crear-una-transaccion.md#post-inittransaction) puedes usar los siguientes endpoints dependiendo del entorno al cual te quieras conectar. Todos los endpoints solo aceptan conexiones https. Recuerda revisar la sección de como [crear una transacción](crear-una-transaccion.md) para ver los datos necesarios para inicializar el pago.

* Desarrollo : https://gw-dev.pagofacil.cl
* Beta : https://gw-beta.pagofacil.cl 
* Producción : https://gw.pagofacil.cl



