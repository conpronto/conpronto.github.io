# Contactos

## Crear Contacto

Este servicio permite agregar un nuevo contacto. Para crear un contacto se debe hacer uso de la url:

`POST https://api.conpronto.com/v1/contacto/?token=<TOKEN>`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del contacto.

``` json title="Estructura del JSON:"
{
  "cliente_id": "122",
  "nombre": "Prueba",
  "apellido": "Prueba1",
  "movil": "0942985587",
  "email ": "noname@noname"
}

```

Atributos necesarios para la creación de una instancia Contacto:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `cliente_id`|decimal|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `nombre`|varchar|200|Si|Nombre del contacto|
| `apellido`|varchar|200|Si|Apellido del contacto|
| `movil`|varchar|20|Si|Móvil del contacto|
| `email`|varchar|200|Si|Email del contacto|

## Modificar Contacto

Para modificar un contacto se debe de hacer uso de la url:

`PUT https://api.conpronto.com/v1/contacto/?token=<TOKEN>`

Por medio del método PUT enviando en el cuerpo del requerimiento los datos del contacto.

``` json title="Estructura del JSON:"
{
  "contacto_id": "1224",
  "cliente_id": "122",
  "nombre": "Prueba",
  "apellido": "Prueba1",
  "movil": "0942985587",
  "email ": "noname@noname"
}
``` 

Atributos para la modificación de un contacto:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `contacto_id`|decimal|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `cliente_id`|decimal|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `nombre`|varchar|200|Si|Nombre del contacto|
| `apellido`|varchar|200|Si|Apellido del contacto|
| `movil`|varchar|20|Si|Móvil del contacto|
| `email`|varchar|200|Si|Email del contacto|


## Obtener Contacto

Para obtener un listado de todos los contactos de un cliente se debe de hacer uso de la url:

`GET https://api.conpronto.com/cliente/<ID>/contactos/`

Devuelve los contactos del cliente con el <ID> del cliente solicitado.

``` json title="Respuesta al consultar los contactos:"
[
{
  "id": "1224",
  "nombre": "Prueba",
  "apellido": "Prueba1",
  "movil": "0942985587",
  "email ": "noname@noname"
},	
{
  "id": "12558",
  "nombre": "Prueba",
  "apellido": "Prueba1",
  "movil": "0942985587",
  "email ": "noname@noname"
}
]
```

Datos que devuelve al obtener la lista de contactos:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `contacto_id`|decimal|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `cliente_id`|decimal|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `nombre`|varchar|200|Si|Nombre del contacto|
| `apellido`|varchar|200|Si|Apellido del contacto|
| `movil`|varchar|20|Si|Móvil del contacto|
| `email`|varchar|200|Si|Email del contacto|