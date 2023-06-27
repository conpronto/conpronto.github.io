# Retención

## Objeto Retención
``` json title="Objeto Retención:"
[{
       "id": "54222",
       "id_documento": "54244",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "total": "100.0",
       "numero": "001-001-000005361",
       "autorizacion": "45678932598466966",
       "estado": "1"
}]
```
Atributos del objeto Retención:

Los estados de la retención son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `1  `       | Activo                               |
| `0  `       | Anulado|

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|varchar|1|Identificador de la retención|
| `id_documento`|varchar|1|Identificador del documento al que pertenece la retención en el sistema|
| `fecha_emision`| date  |-|Fecha que se realiza la transacción|
| `fecha_modificacion`| date  |-|Última fecha en la que se modificó|
| `total`|decimal|10|Valor de la retención|
| `retencion`|varchar|50|Número de retención|
| `autorización`|varchar|50|Número de la retención|
| `estado`|varchar|1|Activo, anulado|

## Crear una retención (POST)

Para crear un retención se debe de hacer uso de la url:

`POST https://api.conpronto.com/retencion/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del documento.  

``` json title="Estructura del JSON:"
[
    {
       "id_documento": "56051",
       "fecha_emision": "13/06/2023",
       "total": "100.0",
       "numero": "001-001-000005361",
       "autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```
## Modificar una retención (PUT)

Este servicio permite modificar una retención creada por API.

Para modificar un documento se debe hacer uso de la url:

`PUT https://api.conpronto.com/retencion/`

Los datos que se envían al momento de la actualización son los mismos que al momento de la creación aumentando el parámetro "id" dentro del json.

``` json title="Estructura del JSON:"
[
    {
       "id": "45552",
       "id_documento": "54610",
       "fecha_emision": "13/06/2023",
       "total": "100.0",
       "numero": "001-001-000005361",
       "autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```

## Obtener una retención (GET)

`GET https://api.conpronto.com/retencion/<ID>/`

Devuelve una retención con el `<ID>` solicitado.

``` json title="Respuesta al consultar la retención:"
[
    {
       "id": "5452",
       "id_documento": "4454",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "total": "100.0",
       "numero": "001-001-000005361",
       "autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```
## Obtener Retenciones por rango de fechas (GET)

Para obtener las retenciones de un rango de fechas determinado hacemos uso del endpoint:

`GET https://api.conpronto.com/retencion/?fecha_inicial=<FECHA_INICIAL>&fecha_final=<FECHA_FINAL>/`

Ejemplo:

`GET https://api.conpronto.com/retencion/?fecha_inicial=1/02/2023&fecha_final=28/02/2023/`

``` json title="Respuesta al consultar un listado de retenciones:"
[	
    {
       "id": "54222",
       "id_documento": "54244",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/02/2023",
       "total": "100.0",
       "numero": "001-001-000005361",
       "autorizacion": "45678932598466966",
       "estado": "1"
	},
	{
       "id": "85682",
       "id_documento": "8824",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "20/02/2023",
       "total": "100.0",
       "numero": "001-001-000005745",
       "autorizacion": "20218932598466966",
       "estado": "1"
	},
]...
```