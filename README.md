---
description: >-
  Esta documentación está orientada a los que quieren crear sus propias
  conexiones con la plataforma no importando si son servicios web, plataformas,
  o aplicaciones.
---

# Foco de esta documentación

### Proceso de Pagos.

El proceso de pago comienza con la creación de la transacción en Pago Fácil a través de ejecutar un POST al endpoint [**initTransaction**](crear-una-transaccion.md#inittransaction) correspondiente al [ambiente](endpoints.md#distincion-de-los-ambientes) en el cual queramos generar la transacción \(Desarrollo, Beta, y Producción\).

![](.gitbook/assets/pfpaymentflow.png)

