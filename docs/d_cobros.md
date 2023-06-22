# Cobro

## Objeto Cobro

``` json title="Objeto Cobro:"
[
   {
	"id": "7423",
	"documento_id": "1234",
    "payment_brand": “VISA”,
	"fecha_emision": "13/06/2023 13:21:01",
	"tipo_cobro": "TC",
	"total": "1100.0"
   },
   {
	"id": "7434",
	"documento_id": "1234",
	"fecha_modificacion": "22/06/2023",
	"fecha_emision": "13/06/2023",
	"tipo_cobro": "CH",
	"total": "1100.0"
   }
]
```
Atributos del objeto Cobro.
Los tipos de cobros soportados vía API son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `EF  `       | Efectivo                             |
| `TR `       | Transferencia|
| `TC  `       | Tarjeta de credito |
| `CH  `       | Cheque |
| `CR  `       | Cruce de documentos |

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|varchar|10| Identificador del cobro en el sistema|
| `documento_id`|varchar|10| Identificador del documento en el sistema|
| `payment_brand`|varchar|20| Marca de tarjeta de crédito   |
| `fecha_emision`|date|-| Fecha que se realiza la transacción|
| `tipo_cobro`|varchar|10| Tipo de cobro: (Efectivo, Transferencia, Tarjeta Crédito, Cheque, Cruce de Documento)|
| `total` |decimal|10|Valor total del cobro|

## Crear Cobros

Para crear un cobro se debe de hacer uso de la url:

`POST https://api.conpronto.com/documento/<ID>/cobro/`

Cambiando el parámetro por el id del documento (devuelto al momento de crear el documento).

``` json title="Estructura del JSON:"
{
    "documento_id": "455852",
    "fecha_emision": "13/06/2023",
    "tipo_cobro": "EF",
    "total": "11200.0"
}
```

## Obtener Cobros

Podemos consultar los cobros que tiene un documento por medio de la url:

`GET https://api.conpronto.com/documento/<ID>/cobro/`

Usando el id devuelto en la creación de documento.

``` json title="Respuesta al consultar los cobros:"
[
   {
	"id": "7423",
	"documento_id": "1234",
	"fecha_modificacion": "22/06/2023",
	"fecha_emision": "13/06/2023",
	"tipo_cobro": "CH",
	"total": "1100.0"
   }
]
``` 

## Obtener cobros realizados por Datafast o Payphone

Podemos consultar los cobros realizados por Datafast o Payphone por medio de la url:

`GET https://api.conpronto.com/cobro/datafast/`

`GET https://api.conpronto.com/cobro/payphone/`

``` json title="Respuesta al consultar los cobros:"
[
   {
	"id": "7423",
	"documento_id": "1234",
    "payment_brand": “VISA”,
	"fecha_emision": "13/06/2023 13:21:01",
	"tipo_cobro": "TC",
	"total": "1100.0"
   },
   {
	"id": "7425",
	"documento_id": "1238",
    "payment_brand": “MASTERCARD”,
	"fecha_emision": "21/06/2023 13:23:01",
	"tipo_cobro": "TC",
	"total": "1283.0"
   }
]
```