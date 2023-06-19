# Cobros

## Crear Cobros

Para crear un cobro se debe de hacer uso de la url:

`POST https://api.contifico.com/v1/documento/<ID>/cobro/`

Cambiando el parámetro por el id del documento (devuelto al momento de crear el documento).

``` json title="Estructura del JSON:"
{
    "id_documento": "455852",
    "fecha_emision": "13/06/2023",
    "forma_cobro": 0,
    "total": "11200.0",
}
```
Atributos necesarios para la creación de un cobro:

Los tipos de cobros soportados vía API son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `0  `       | Efectivo                             |
| `1  `       | Transferencia|
| `2  `       | Tarjeta de credito |
| `3  `       | Cheque |
| `4  `       | Cruce de documentos |

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `id_documento`|decimal|10| Si|Identificador del documento en el sistema|
| `fecha_emision`|date|-| Si|Fecha que se realiza la transacción|
| `forma_cobro`|decimal|1|Si|Tipo de cobro: (Efectivo, Transferencia, Tarjeta Crédito, Cheque, Cruce de Documento)|
| `tipo_identificacion` |decimal|10|Si|Valor total del cobro|    

## Obtener Cobros

Podemos consultar los cobros que tiene un documento por medio de la url:

`GET https://api.conpronto.com/v1/documento/<ID>/cobro/`

Usando el id devuelto en la creación de documento.

``` json title="Respuesta al consultar los cobros:"
[
   {
	"id_cobro": "7423",
	"id_documento": "1234",
	"fecha_modificacion": null,
	"fecha_emision": "13/06/2023",
	"forma_cobro": 1,
	"total": "1100.0",
   }
]
``` 

Atributos para la consulta de una instancia Payment y PaymentDetail:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id_documento`|decimal|10| Identificador del documento en el sistema|
| `fecha_emision`|date|-|Fecha que se realiza la transacción|
| `forma_cobro`|decimal|1|Tipo de cobro: (Efectivo, Transferencia, Tarjeta Crédito, Cheque, Cruce de Documento)|
| `tipo_identificacion` |decimal|10|Valor total del cobro|

## Obtener cobros realizados por Datafast o Payphone

Podemos consultar los cobros realizados por Datafast o Payphone por medio de la url:

`GET https://api.conpronto.com/v1/cobro/datafast/`
`GET https://api.conpronto.com/v1/cobro/payphone/`

``` json title="Respuesta al consultar los cobros:"
[
   {
	"id_cobro": "7423",
	"id_documento": "1234",
    "payment_brand": “VISA”,
	"fecha_emision": "13/06/2023 13:21:01",
	"forma_cobro": 2,
	"total": "1100.0",
   },
   {
	"id_cobro": "7425",
	"id_documento": "1238",
    "payment_brand": “MASTERCARD”,
	"fecha_emision": "21/06/2023 13:23:01",
	"forma_cobro": 2,
	"total": "1283.0",
   }
]
```

Atributos para la consulta de un cobro:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id_cobro`|decimal|10| Identificador del cobro en el sistema|
| `id_documento`|decimal|10| Identificador del documento en el sistema|
| `payment_brand`|varchar|20| Marca de tarjeta de crédito   |
| `fecha_emision`|date|-| Fecha que se realiza la transacción|
| `forma_cobro`|decimal|1| Tipo de cobro: (Efectivo, Transferencia, Tarjeta Crédito, Cheque, Cruce de Documento)|
| `total` |decimal|10|Valor total del cobro|