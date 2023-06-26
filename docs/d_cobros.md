# Cobro

## Objeto Cobro

``` json title="Objeto Cobro:"
[
   {
    "id": "7423",
    "documento_id": "1234",
    "marca_tarjeta": "MASTERCARD",
    "pasarela_pago": "DT",	
    "fecha_emision": "13/06/2023 13:21:01",
    "fecha_modificacion": "22/06/2023",	
    "tipo_cobro": "TC",
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

Los tipos de pasarela de pagos soportados para pago con tarjeta son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `DT  `       | Datafast                            |
| `PH `       | Payphone|

| Parámetro       | Tipo    | Longitud | Obligatorio | Descripción |
| -----------   | ------- | -------- |-------|----------- |
| `id`|varchar|10|Si| Identificador del cobro en el sistema|
| `documento_id`|varchar|10|Si| Identificador del documento en el sistema|
| `marca_tarjeta`|varchar|20|Si*| Marca de tarjeta de crédito   |
| `pasarela_pagos`|varchar|10|Si*|Pasarela de pagos usada (Payphone, datafast)|
| `fecha_emision`|date|-|Si| Fecha que se realiza la transacción  |
| `fecha_modificacion` |date|-|No|Última fecha en la que se modificó |
| `tipo_cobro`|varchar|10|Si| Tipo de cobro: (Efectivo, Transferencia, Tarjeta Crédito, Cheque, Cruce de Documento)|
| `total` |decimal|10|Si|Valor total del cobro|

## Crear Cobros (POST)

Para crear un cobro se debe de hacer uso de la url:

`POST https://api.conpronto.com/documento/<ID>/cobro/`

Cambiando el parámetro por el id del documento (devuelto al momento de crear el documento).

``` json title="Estructura del JSON:"
{
    "id": "7423",
    "documento_id": "1234",
    "marca_tarjeta": Null,
    "pasarela_pago": Null,	
    "fecha_emision": "13/06/2023 13:21:01",
    "fecha_modificacion": "22/06/2023",	
    "tipo_cobro": "EF",
    "total": "1100.0"
}
```
*NOTA :material-information-outline:{ title="Nota" }:

:bangbang: Los campos marca_tarjeta y pasarela_pagos solo son obligatorios cuando el tipo de cobro es tarjeta.

## Obtener Cobros (GET)

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

## Obtener cobros realizados por Datafast o Payphone (GET)

Podemos consultar los cobros realizados por Datafast o Payphone por medio de la url:

`GET https://api.conpronto.com/cobro/datafast/`

`GET https://api.conpronto.com/cobro/payphone/`

``` json title="Respuesta al consultar los cobros:"
[
   {
	"id": "7423",
	"documento_id": "1234",
    "payment_brand": "VISA",
	"fecha_emision": "13/06/2023 13:21:01",
	"tipo_cobro": "TC",
	"total": "1100.0"
   },
   {
	"id": "7425",
	"documento_id": "1238",
    "payment_brand": "MASTERCARD",
	"fecha_emision": "21/06/2023 13:23:01",
	"tipo_cobro": "TC",
	"total": "1283.0"
   }
]
```