# Cliente
## Objeto Cliente

``` json title="Objeto Cliente:"
[
    {
        "id": "1234",
        "fecha_modificacion": "21/06/2023",
        "razon_social": null,
        "nombre_comercial": null,
        "nombre": "Andres",
        "apellido": "Lopez",
        "tipo_identificacion": "1",
        "identificacion": "0999999999",
        "tipo_persona": "1",
        "direccion": "Guayaquil",
    	"contactos":
		[{
            "id": "113",
    	    "nombre": "Andres",
    	    "apellido": "Lopez",
    	    "movil": "+593942985587",
    	    "email ": "alopez@gmail.com"
    	},
		{
            "id": "115",
    	    "nombre": "Juan",
    	    "apellido": "Lopez",
    	    "movil": "+593942952487",
    	    "email ": "jlopez@gmail.com"
    	}],
}]
```
Atributos del objeto Cliente.

Los tipos de identificación son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `1 `       | Cédula                               |
| `2 `       | Ruc|
| `3 `       | Pasaporte |

Los tipos de persona son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `1 `       | Persona                            |
| `2 `       | Empresa|

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|varchar|10|Identificador del cliente en el sistema|
| `fecha_modificacion`|date||Última fecha en la que se modificó el cliente|
| `razon_social`|varchar|200|Razón social del cliente tipo empresa|
| `nombre_comercial `|varchar|200|Nombre comercial del cliente tipo empresa|
| `nombre`|varchar|200|Nombre cliente tipo persona|
| `apellido`|varchar|200|Apellido cliente tipo persona|
| `tipo_identificacion`|varchar|1|Tipo de identificación del cliente|
| `identificacion`|varchar|15|Número de cédula o ruc del cliente|
| `tipo_persona`|varchar|1|Tipo de persona del cliente (Persona o Empresa)|
| `direccion`|varchar|200|Dirección del cliente|
| `contacto`|objeto|-|Si|Objeto contenedor del contacto del cliente|


## Crear Cliente (POST)

Para crear un cliente se debe de hacer uso de la url:

`POST https://api.conpronto.com/cliente/`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del cliente:

``` json title="Estructura del JSON:"
{
    	"razon_social": "Andres Lopez",
    	"nombre_comercial": "Andres Lopez",
    	"nombre": null,
    	"apellido": null,
    	"tipo_identificacion": "2",
    	"identificacion": "0999954599001",
    	"tipo_persona": "2",
    	"direccion": "Guayaquil",
    	"contactos": 
		[{
    	   "nombre": "Andres",
    	   "apellido": "Lopez",
    	   "movil": "+593942985587",
    	   "email": "noname@noname"
    	}]
}
```
*NOTA:

:bangbang: En el caso de que se registre un cliente de tipo “Persona”, los parámetros razon_social y nombre_comercial no son obligatorios. Así mismo, en el caso de que se registre un cliente de tipo “Empresa”, los parámetros nombre y apellido no son obligatorios.

## Modificar Cliente (PUT)

Para modificar un cliente se debe de hacer uso de la url:

`PUT https://api.conpronto.com/cliente/`

Por medio del método PUT enviando en el cuerpo del requerimiento los datos del cliente.

``` json title="Estructura del JSON:"
{
        "id": "1235",
        "razon_social": null,
        "nombre_comercial": null,
        "nombre": "Andres",
        "apellido": "Lopez",
        "tipo_identificacion": "1",
        "identificacion": "0999999999",
        "tipo_persona": "1",
        "direccion": "Guayaquil",
    	"contactos": 
		[{
    	    "nombre": "Andrés",
    	    "apellido": "Lopez",
    	    "movil": "+593942985587",
    	    "email ": "alopez@gmail.com"
    	}],
}
``` 
*NOTA :material-information-outline:{ title="Nota" }:

:bangbang: En el caso de modificar un cliente de tipo “Persona”, los parámetros razon_social y nombre_comercial no son obligatorios. Así mismo, en el caso de modificar un cliente de tipo “Empresa”, los parámetros nombre y apellido no son obligatorios.

## Obtener un Cliente (GET)

Para obtener un cliente se debe de hacer uso de la url:

`GET https://api.conpronto.com/cliente/<ID>/`

Devuelve un cliente con el <ID> solicitado.

``` json title="Respuesta al consultar un cliente:"
[
    {
        "id": "1234",
        "fecha_modificacion": "21/06/2023",
        "razon_social": null,
        "nombre_comercial": null,
        "nombre": "Andres",
        "apellido": "Lopez",
        "tipo_identificacion": "1",
        "identificacion": "0999999999",
        "tipo_persona": "1",
        "direccion": "Guayaquil",
		"contactos":
		[{
            "id": "113",
    	    "nombre": "Andres",
    	    "apellido": "Lopez",
    	    "movil": "+593942985587",
    	    "email ": "alopez@gmail.com"
    	},
		{
            "id": "115",
    	    "nombre": "Juan",
    	    "apellido": "Lopez",
    	    "movil": "+593942952487",
    	    "email ": "jlopez@gmail.com"
    	}],
}]
```

## Obtener un listado de Clientes (GET)

Para obtener un listado de todos los clientes creados en el sistema se debe de hacer uso de la url:

`GET https://api.conpronto.com/cliente/`

``` json title="Respuesta al consultar todos los clientes:"
[
	{
       "id": "4568",
       "fecha_modificacion": "21/06/2023",
       "razon_social": null,
       "nombre_comercial": null,
       "nombre": "Andres",
       "apellido": "Lopez",
       "tipo_identificacion": "1",
       "identificacion": "0999999999",
       "tipo_persona": "1",
       "direccion": "Guayaquil",
	   "contactos":
		[{
            "id": "113",
    	    "nombre": "Andres",
    	    "apellido": "Lopez",
    	    "movil": "+593942985587",
    	    "email ": "alopez@gmail.com"
    	},
		{
            "id": "115",
    	    "nombre": "Juan",
    	    "apellido": "Lopez",
    	    "movil": "+593942952487",
    	    "email ": "jlopez@gmail.com"
    	}],
 },
 {
       "id": "4956",
       "fecha_modificacion": "21/06/2023",
       "razon_social": "Pladsu S.A",
       "nombre_comercial": "Pronto",
       "nombre": null,
       "apellido": null,
       "tipo_identificacion": "2",
       "identificacion": "0999999945001",
       "tipo_persona": "2",
       "direccion": "Guayaquil",
		"contactos":
		[{
            "id": "123",
    	    "nombre": "Pronto",
    	    "apellido": "Cobranzas",
    	    "movil": "+593942985587",
    	    "email ": "cobranzas@gmail.com"
    	},
		{
            "id": "125",
    	    "nombre": "Pronto",
    	    "apellido": "ADministración",
    	    "movil": "+593942952487",
    	    "email ": "administracion@gmail.com"
    	}],	
 },...
```