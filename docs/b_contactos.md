# Contacto

## Objeto Contacto

``` json title="Objeto Contacto:"
[{
  "id": "1224",
  "nombre": "Andrés",
  "apellido": "López",
  "movil": "+593942985587",
  "email ": "alopez@gmail.com"
},	
{
  "id": "12558",
  "nombre": "Juan",
  "apellido": "López",
  "movil": "+593942985587",
  "email ": "jlopez@gmail.com"
}]
```
Atributos del objeto contacto:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `id`|varchar|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `cliente_id`|varchar|10| Si|Identificador del cliente al que se desea agregar un contacto|
| `nombre`|varchar|200|Si|Nombre del contacto|
| `apellido`|varchar|200|Si|Apellido del contacto|
| `movil`|varchar|20|Si|Móvil del contacto|
| `email`|varchar|200|Si|Email del contacto|

## Crear Contacto (POST)

Este servicio permite agregar un nuevo contacto. Para crear un contacto se debe hacer uso de la url:

`POST https://api.conpronto.com/contacto/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del contacto.

``` json title="Estructura del JSON:"
{
  "cliente_id": "122",
  "nombre": "Andrés",
  "apellido": "Lopez",
  "movil": "+593942985587",
  "email ": "alopez@gmail.com"
}

```

## Modificar Contacto (PUT)

Para modificar un contacto se debe de hacer uso de la url:

`PUT https://api.conpronto.com/contacto/`

Por medio del método PUT enviando en el cuerpo del requerimiento los datos del contacto.

``` json title="Estructura del JSON:"
{
  "id": "1224",
  "cliente_id": "122",
  "nombre": "Andrés",
  "apellido": "López",
  "movil": "+593942985587",
  "email ": "alopez@gmail.com"
}
``` 

## Obtener Contacto (GET)

Para obtener un listado de todos los contactos de un cliente se debe de hacer uso de la url:

`GET https://api.conpronto.com/cliente/<ID>/contacto/`

Devuelve los contactos del cliente con el <ID> del cliente solicitado.

``` json title="Respuesta al consultar los contactos:"
[
  {
    "id": "1224",
    "nombre": "Andrés",
    "apellido": "Lopez",
    "movil": "+593942985587",
    "email ": "alopez@gmail.com"
  },	
  {
    "id": "12558",
    "nombre": "Juan",
    "apellido": "Lopez",
    "movil": "+593957235284",
    "email ": "jlopez@gmail.com"
  }
]
```