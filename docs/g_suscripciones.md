# Suscripciones
## Objeto Suscripción

``` json title="Objeto Suscripción:"
[
   {
       "id": "65141",
       "cliente_id": "56051",
       "contrato_id": "85652",
       "fecha_inicio": "13/06/2023",
       "recurrente": "1",
       "valor": "100.0",
       "impuesto": "12.0",
       "estado": "1",
   }
]
```
Atributos del objeto Suscripción.

Los estados de la suscripción son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `1  `       | Activo                               |
| `2  `       | Inactivo|

Los valores de recurrencia en la suscripción son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `1  `       | Cada mes                        |
| `2  `       | Cada dos meses|
| `3  `       | Cada tres meses|
| `n  `       | Cada "n" meses|

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|decimal|10|Identificador de la suscripción en el sistema|
| `cliente_id`|decimal|10|Identificador del cliente al que pertenece la suscripción en el sistema|
| `contrato_id`|decimal|10|Identificador del contrato del cliente en el sistema |
| `fecha_inicio`|date|-|Fecha de inicio de la suscripción|
| `recurrente`|decimal|10|Recurrencia de la suscripción|
| `valor`|decimal|50|Valor de la suscripción|
| `impuesto`|decimal|50|Valor del impuesto de la suscripción|
| `estado`|decimal|10|Activo, Inactivo|

## Crear Suscripción (POST)

Para crear una sucripción se debe de hacer uso de la url:

`POST https://api.contifico.com/documento/<ID>/suscripcion/`

Cambiando el parámetro por el id del cliente (devuelto al momento de crear el cliente).

``` json title="Estructura del JSON:"
{
       "contrato_id": "85652",
       "fecha_inicio": "13/06/2023",
       "recurrente": "1",
       "valor": "100.0",
       "impuesto": "12.0",
       "estado": "1",
}
```

## Modificar Suscripción (PUT)

Para modificar una suscripción se debe de hacer uso de la url:

`PUT https://api.conpronto.com/suscripcion/`

Por medio del método PUT enviando en el cuerpo del requerimiento los datos de la suscripción.

``` json title="Estructura del JSON:"
{
       "id": "65141",
       "cliente_id": "56051",
       "contrato_id": "85652",
       "fecha_inicio": "13/06/2023",
       "recurrente": "1",
       "valor": "100.0",
       "impuesto": "12.0",
       "estado": "1",
}
```
## Obtener una Suscripción (GET)

Para obtener una suscripción se debe de hacer uso de la url:

`GET https://api.conpronto.com/suscripcion/<ID>/`

Devuelve una suscripción con el <ID> solicitado.

``` json title="Respuesta al consultar una Suscripción:"
[
   {
       "id": "65141",
       "cliente_id": "56051",
       "contrato_id": "85652",
       "fecha_inicio": "13/06/2023",
       "recurrente": "1",
       "valor": "100.0",
       "impuesto": "12.0",
       "estado": "1",
   }
]
```
## Obtener un listado de Suscripciones (GET)

Para obtener un listado de todos las Suscripciones creadas en el sistema se debe de hacer uso de la url:

`GET https://api.conpronto.com/suscripcion/`

``` json title="Respuesta al consultar un listado de Suscripciones:"
[
   {
       "id": "65141",
       "cliente_id": "56051",
       "contrato_id": "85652",
       "fecha_inicio": "13/06/2023",
       "recurrente": "1",
       "valor": "100.0",
       "impuesto": "12.0",
       "estado": "1",
   },
      {
       "id": "45215",
       "cliente_id": "78523",
       "contrato_id": "72358",
       "fecha_inicio": "31/06/2023",
       "recurrente": "2",
       "valor": "120.0",
       "impuesto": "12.0",
       "estado": "1",
   }
]
```