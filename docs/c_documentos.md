# Documento
## Objeto Documento

``` json title="Objeto Documento:"
[{
    "id": "7466",
    "cliente_id": "52235",
    "fecha_modificacion": "22/06/2023",
    "fecha_emision": "13/06/2023",
    "fecha_vencimiento": "17/10/2023",
    "no_factura ": "001-001-000000251",
    "no_autorizacion": "45678932598466966",
    "subtotal_0": "0.0",
    "impuesto": "0.0",
    "total": "11200.0",
    "saldo": "10000.0",
    "cobro": 
    [{
	    "id": "455852",
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
    }],
    "retencion":
    [{
      "id": "56051",
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
    }],
 },
 {
    "id": "5453",
    "cliente_id": "54522",
    "fecha_modificacion": "22/06/2023",
    "fecha_emision": "13/05/2023",
    "fecha_vencimiento": "17/05/2023",
    "numero ": "001-001-000000471",
    "numero": "456789325984646466966",
    "subtotal": "0.0",
    "impuesto": "0.0",
    "total": "11200.0",
    "saldo": "10000.0",
    "cobro": 
    [{
	    "id": "455852",
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
    }],
    "retencion": 
    [{
      "id": "56051",
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
    }],
 },
 ...
]
```
Atributos del objeto Documento:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `id` | varchar | 10 | Si | Identificador del cliente al que pertenece el documento en el sistema|
| `cliente_id` | varchar | 10 | Si | Identificador del cliente al que pertenece el documento en el sistema|
| `fecha_modificacion` | date | - | Si| Fecha límite de vigencia del documento|
| `fecha_emision ` | date | - | Si| Fecha de creación del documento|
| `fecha_vencimiento ` | date | - | Si| Fecha límite de vigencia del documento|
| `numero`|varchar|17|Si|Número del documento|
| `autorizacion`|varchar|49|Si|Número de autorización del documento|
| `subtotal`|decimal|10|Si|Representa el valor Subtotal del documento|
| `impuesto`|decimal|10|Si|Representa el valor del impuesto del documento|
| `total`|decimal|10|Si|Representa el valor total del documento|
| `saldo`|decimal|10|Si|Representa el valor del saldo del documento|
| `cobro `| objeto | - | No| Objeto contenedor del cobro del documento|
| `retencion`|objeto|-|No|Objeto contenedor de la retención del documento|

## Crear Documento (POST)

Para crear un documento se debe de hacer uso de la url:

`POST https://api.conpronto.com/registro/documento/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del documento.

``` json title="Estructura del JSON:"
 {
	"cliente_id": "5662",
	"fecha_emision": "13/06/2023",
	"fecha_vencimiento": "17/07/2023",
	"numero": "001-002-000000451",
	"autorizacion": "565645678932448598466966",
	"subtotal": "0.0",
	"impuesto": "0.0",
	"total": "11200.0",
	"saldo": "10000.0",
  "cobro":
  [{
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
  }],
  "retencion":
  [{
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
  }],
}
```
## Modificar Documento (PUT)

Este servicio permite modificar un documento creado por API.

Para modificar un documento se debe hacer uso de la url:

`PUT https://api.conpronto.com/documento/`

Los datos que se envían al momento de la actualización son los mismos que al momento de la creación aumentando el parámetro "id" dentro del json.

``` json title="Estructura del JSON:"
{
	"id": "7856",
	"cliente_id": "45248",
	"fecha_emision": "13/06/2023",
	"fecha_vencimiento": "17/10/2023",
	"numero ": "001-001-000000251",
	"autorizacion": "45678932598466966",
	"subtotal": "0.0",
	"impuesto": "0.0",
	"total": "11200.0",
	"saldo": "10000.0",
  "cobro": 
  [{
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
  }],
  "retencion": 
  [{
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero ": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
  }],
}
``` 

## Obtener un Documento (GET)

Para obtener un documento se debe de hacer uso de la url:

`GET https://api.conpronto.com/documento/<ID>`

Devuelve un documento con el <ID> solicitado.

Respuesta al consultar un documento:

``` json title="Respuesta al consultar un documento:"
[
  {
    "id": "7466",
    "cliente_id": "52235",
    "fecha_modificacion": "22/06/2023",
    "fecha_emision": "13/06/2023",
    "fecha_vencimiento": "17/10/2023",
    "numero": "001-001-000000251",
    "autorizacion": "45678932598466966",
    "subtotal": "0.0",
    "impuesto": "0.0",
    "total": "11200.0",
    "saldo": "10000.0",
    "cobro": 
    [{
	    "id": "7466",
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
    }],
      "retencion": 
    [{
      "id": "7466",
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
    }],
  }
]
```

## Obtener un listado de Documentos (GET)

Para obtener todos los documentos de la cuenta hacemos uso del endpoint:

`GET https://api.conpronto.com/documento/`

Datos que devuelve al obtener un listado de documentos:

``` json title="Respuesta al consultar todos los documentos:"
[
 { 
    "id": "7466",
    "cliente_id": "52235",
    "fecha_modificacion": "22/06/2023",
    "fecha_emision": "13/06/2023",
    "fecha_vencimiento": "17/10/2023",
    "no_factura ": "001-001-000000251",
    "no_autorizacion": "45678932598466966",
    "subtotal_0": "0.0",
    "impuesto": "0.0",
    "total": "11200.0",
    "saldo": "10000.0",
    "cobro": 
    [{
	    "id": "455852",
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
    }],
    "retencion":
    [{
      "id": "56051",
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
    }],
 },
 {
    "id": "5453",
    "cliente_id": "54522",
    "fecha_modificacion": "22/06/2023",
    "fecha_emision": "13/05/2023",
    "fecha_vencimiento": "17/05/2023",
    "numero ": "001-001-000000471",
    "numero": "456789325984646466966",
    "subtotal": "0.0",
    "impuesto": "0.0",
    "total": "11200.0",
    "saldo": "10000.0",
    "cobro": 
    [{
	    "id": "455852",
	    "fecha_emision": "13/06/2023",
	    "tipo_cobro": "EF",
	    "total": "11200.0"
    }],
    "retencion": 
    [{
      "id": "56051",
      "fecha_emision": "13/06/2023",
      "valor": "100.0",
      "numero": "001-001-000005361",
      "autorizacion": "45678932598466966",
      "estado": "1"
    }],
 },
 ...
] 
```