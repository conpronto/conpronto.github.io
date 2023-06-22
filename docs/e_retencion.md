# Retención

## Objeto Retención
``` json title="Objeto Retención:"
[	
    {
       "id": "54222",
       "id_documento": "54244",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
	},
	{
       "id": "85682",
       "id_documento": "8824",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
	},
]...
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
| `valor`|decimal|1|Valor de la retención|
| `no_retencion`|varchar|50|Número de retención|
| `no_autorización`|varchar|49|Número de la retención|
| `estado`|varchar|1|Activo, anulado|

## Crear una retención (POST)

Para crear un retención se debe de hacer uso de la url:

`POST https://api.conpronto.com/documento/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del documento.  

``` json title="Estructura del JSON:"
[
    {
       "id_documento": "56051",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```
## Modificar una retención (PUT)

Este servicio permite modificar una retención creada por API.

Para modificar un documento se debe hacer uso de la url:

`PUT https://api.conpronto.com/documento/`

Los datos que se envían al momento de la actualización son los mismos que al momento de la creación aumentando el parámetro "id" dentro del json.

``` json title="Estructura del JSON:"
[
    {
       "id": "45552",
       "id_documento": "54610",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```

## Obtener una retención (GET)

`GET https://api.conpronto.com/documento/<ID>`

Devuelve una retención con el `<ID>` solicitado.

``` json title="Respuesta al consultar la retención:"
[
    {
       "id": "5452",
       "id_documento": "4454",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
    }
]
```
## Obtener un listado de retenciones (GET)

Obtener una lista de todas las retenciones ingresadas en el sistema.

`GET https://api.conpronto.com/documento/`

Respuesta al consultar un listado de retenciones:

``` json title="Respuesta al consultar un listado de retenciones:"
[	
    {
       "id": "54222",
       "id_documento": "54244",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
	},
	{
       "id": "85682",
       "id_documento": "8824",
       "fecha_modificacion": "22/06/2023",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": "1"
	},
]...
```