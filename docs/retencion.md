# Retenciones

## Crear una retención

Para crear un retención se debe de hacer uso de la url:

`POST https://api.conpronto.com/v1/documento/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del documento.  

``` json title="Estructura del JSON:"
[
    {
       "id_documento": "56051",
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": 1,
    }
]
```

Atributos necesarios para la creación de una retención:

Los estados de la retención son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `0  `       | Activo                               |
| `1  `       | Anulado|

Datos para la creación de la retención:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `id_documento`|decimal|10|Si|Identificador del documento al que pertenece la retención en el sistema|
| `fecha_emision`| date|-| Si |Fecha que se realiza la transacción|
| `valor`|decimal|1|Si|Valor de la retención|
| `no_retencion`|varchar|50|Si|Número de retención|
| `no_autorización`|varchar|49|Si|Número de la retención|
| `estado`|decimal|1|Si|Activo, anulado|

## Modificar una retención

Este servicio permite modificar una retención creada por API.

Para modificar un documento se debe hacer uso de la url:

`PUT https://api.conpronto.com/v1/documento/`

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
       "estado": 1,
    }
]
```

Atributos necesarios para la modificación de una retención:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `id`|decimal|1|Si|Identificador de la retención|
| `id_documento`|decimal|1|Si|Identificador del documento al que pertenece la retención en el sistema|
| `fecha_emision`| date  |-| Si |Fecha que se realiza la transacción|
| `valor`|decimal|1|Si|Valor de la retención|
| `no_retencion`|varchar|50|Si|Número de retención|
| `no_autorización`|varchar|49|Si|Número de la retención|
| `estado`|decimal|1|Si|Activo, anulado|

## Obtener una retención

`GET https://api.conpronto.com/v1/documento/<ID>`

Devuelve una retención con el <ID> solicitado.

``` json title="Respuesta al consultar la retención:"
[
    {
       "id": "5452",
       "id_documento": "4454",
       "fecha_modificacion": null,
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": 1,
    }
]
```
Datos al obtener una retención:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|decimal|1|Identificador de la retención|
| `id_documento`|decimal|1|Identificador del documento al que pertenece la retención en el sistema|
| `fecha_emision`| date  |-|Fecha que se realiza la transacción|
| `fecha_modificacion`| date  |-|Última fecha en la que se modificó|
| `valor`|decimal|1|Valor de la retención|
| `no_retencion`|varchar|50|Número de retención|
| `no_autorización`|varchar|49|Número de la retención|
| `estado`|decimal|1|Activo, anulado|

## Obtener un listado de retenciones

Obtener una lista de todas las retenciones ingresadas en el sistema.

`GET https://api.conpronto.com/v1/documento/`

Respuesta al consultar un listado de retenciones:

``` json title="Respuesta al consultar un listado de retenciones:"
[	
    {
       "id": "54222",
       "id_documento": "54244",
       "fecha_modificacion": null,
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": 1,
	},
	{
       "id": "85682",
       "id_documento": "8824",
       "fecha_modificacion": null,
       "fecha_emision": "13/06/2023",
       "valor": "100.0",
       "no_retencion ": "001-001-000005361",
       "no_autorizacion": "45678932598466966",
       "estado": 1,
	},
]...
```

Datos al obtener un listado de retenciones:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|decimal|1|Identificador de la retención|
| `id_documento`|decimal|1|Identificador del documento al que pertenece la retención en el sistema|
| `fecha_emision`| date  |-|Fecha que se realiza la transacción|
| `fecha_modificacion`| date  |-|Última fecha en la que se modificó|
| `valor`|decimal|1|Valor de la retención|
| `no_retencion`|varchar|50|Número de retención|
| `no_autorización`|varchar|49|Número de la retención|
| `estado`|decimal|1|Activo, anulado|