# Cliente
## Crear Cliente

Para crear un cliente se debe de hacer uso de la url:

`POST https://api.conpronto.com/v1/clientes/?token=<TOKEN>`

Por medio del método POST enviando en el cuerpo del requerimiento los datos del cliente:

``` json title="Estructura del JSON:"
{
    	"razon_social": "Andres Lopez",
    	"nombre_comercial": "Andres Lopez",
    	"nombre": null,
    	"apellido": null,
    	"tipo_identificacion": 0,
    	"identificacion": "0999954599001",
    	"tipo_persona": "Persona",
    	"direccion": "Guayaquil",
    	"contactos": 
		[{
    	   "nombre": "Prueba",
    	   "apellido": "Prueba1",
    	   "movil": "0942985587",
    	   "email": "noname@noname"
    	}]
}
```

Atributos necesarios para la creación de una instancia Customer:

Los tipos de identificación son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `0  `       | Cédula                               |
| `1  `       | Ruc|
| `2  `       | Pasaporte |

Los tipos de persona son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `0  `       | Persona                            |
| `1  `       | Empresa|

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `razon_social` | varchar  | 200       | Si*         |Razón comercial del cliente tipo empresa|
| `nombre_comercial `|varchar|200|Si*|Nombre comercial del cliente tipo empresa|
| `nombre`|varchar|200|Si*|Nombre cliente tipo persona|
| `apellido`|varchar|200|Si*|Apellido cliente tipo persona|
| `tipo_identificacion`|decimal|1|Si|Tipo de identificación del cliente|
| `identificacion`|varchar|15|Si|Número de cédula o ruc del cliente|
| `tipo_persona`|decimal|1|Si|Tipo de persona del cliente (Persona o Empresa)|
| `direccion`|varchar|200|Si|Dirección del cliente|
| `contacto`|objeto|-|Si|Objeto contenedor del contacto del cliente|

*NOTA:

:bangbang: En el caso de que se registre un cliente de tipo “Persona”, los parámetros razon_social y nombre_comercial no son obligatorios. Así mismo, en el caso de que se registre un cliente de tipo “Empresa”, los parámetros nombre y apellido no son obligatorios.

## Modificar Cliente

Para modificar un cliente se debe de hacer uso de la url:

`PUT https://api.conpronto.com/v1/clientes/?token=<TOKEN>`

Por medio del método PUT enviando en el cuerpo del requerimiento los datos del cliente.

``` json title="Estructura del JSON:"
{
        "cliente_id": "1235",
        "razon_social": null,
        "nombre_comercial": null,
        "nombre": "Andres",
        "apellido": "Lopez",
        "tipo_identificacion": 0,
        "identificacion": "0999999999001",
        "tipo_persona": 0,
        "direccion": "Guayaquil",
    	"contactos": 
		[{
    	    "nombre": "Prueba",
    	    "apellido": "Prueba1",
    	    "movil": "0942985587",
    	    "email ": "noname@noname"
    	}],
}
``` 

Atributos para la modificación de una instancia Customer:

| Parámetro   | Tipo    | Longitud | Obligatorio | Descripción |
| ----------- | ------- | -------- | ----------- | ----------- |
| `cliente_id`|decimal|10| Si|Identificador del cliente en el sistema|
| `razon_social`|varchar|200| Si*|Razón social del cliente tipo empresa|
| `nombre_comercial `|varchar|200|Si*|Nombre comercial del cliente tipo empresa|
| `nombre`|varchar|200|Si*|Nombre cliente tipo persona|
| `apellido`|varchar|200|Si*|Apellido cliente tipo persona|
| `tipo_identificacion`|decimal|1|Si|Tipo de identificación del cliente|
| `identificacion`|varchar|15|Si|Número de cédula o ruc del cliente|
| `tipo_persona`|decimal|1|Si|Tipo de persona del cliente (Persona o Empresa)|
| `direccion`|varchar|200|Si|Dirección del cliente|
| `contacto`|objeto|-|Si|Objeto contenedor del contacto del cliente|

*NOTA:

:bangbang: En el caso de modificar un cliente de tipo “Persona”, los parámetros razon_social y nombre_comercial no son obligatorios. Así mismo, en el caso de modificar un cliente de tipo “Empresa”, los parámetros nombre y apellido no son obligatorios.

## Obtener un Cliente

Para obtener un cliente se debe de hacer uso de la url:

`GET https://api.conpronto.com/v1/clientes/<ID>/`

Devuelve un cliente con el <ID> solicitado.

``` json title="Respuesta al consultar un cliente:"
[
    {
        "cliente_id": "1234",
        "fecha_modificacion": null,
        "razon_social": null,
        "nombre_comercial": null,
        "nombre": "Andres",
        "apellido": "Lopez",
        "tipo_identificacion": 0,
        "identificacion": "0999999999001",
        "tipo_persona": 0,
        "direccion": "Guayaquil",
    	"contactos":
		[{
            "id": "113",
    	    "nombre": "Prueba",
    	    "apellido": "Prueba1",
    	    "movil": "0942985587",
    	    "email ": "noname@noname"
    	}],
}]
```

Datos que devuelve al obtener un cliente de una instancia Customer:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `cliente_id`|decimal|10|Identificador del cliente en el sistema|
| `fecha_modificacion`|date||Última fecha en la que se modificó el cliente|
| `razon_social`|varchar|200|Razón social del cliente tipo empresa|
| `nombre_comercial `|varchar|200|Nombre comercial del cliente tipo empresa|
| `nombre`|varchar|200|Nombre cliente tipo persona|
| `apellido`|varchar|200|Apellido cliente tipo persona|
| `tipo_identificacion`|decimal|1|Tipo de identificación del cliente|
| `identificacion`|varchar|15|Número de cédula o ruc del cliente|
| `tipo_persona`|decimal|1|Tipo de persona del cliente (Persona o Empresa)|
| `direccion`|varchar|200|Dirección del cliente|
| `contacto`|objeto|-|Si|Objeto contenedor del contacto del cliente|

## Obtener un listado de Clientes

Para obtener un listado de todos los clientes creados en el sistema se debe de hacer uso de la url:

`GET https://api.conpronto.com/v1/clientes/`

``` json title="Respuesta al consultar todos los clientes:"
[
	{
       "id": "4568",
       "fecha_modificacion": null,
       "razon_social": null,
       "nombre_comercial": null,
       "nombre": "Andres",
       "apellido": "Lopez",
       "tipo_identificacion": 0,
       "identificacion": "0999999999001",
       "tipo_persona": 0,
       "direccion": "Guayaquil",
       "contactos":
	    [{
     	    "id": "113",          
    	    "nombre": "Prueba",
    	    "apellido": "Prueba1",
    	    "movil": "0942985587",
    	    "email ": "noname@noname"
    	}],
 },
	{
       "id": "4956",
       "fecha_modificacion": null,
       "razon_social": "razon social prueba",
       "nombre_comercial": "nombre comercial prueba",
       "nombre": null,
       "apellido": null,
       "tipo_identificacion": 0,
       "identificacion": "0999999945001",
       "tipo_persona": 1,
       "direccion": "Guayaquil",
       "contactos":
		[{
            "id": "122",
    	    "nombre": "Prueba",
    	    "apellido": "Prueba1",
    	    "movil": "0942985587",
    	    "email ": "noname@noname"
    	}],  	
	},...
```

Datos que devuelve al obtener un cliente de una instancia Customer:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `cliente_id`|decimal|10|Identificador del cliente en el sistema|
| `fecha_modificacion`|date||Última fecha en la que se modificó el cliente|
| `razon_social`|varchar|200|Razón social del cliente tipo empresa|
| `nombre_comercial `|varchar|200|Nombre comercial del cliente tipo empresa|
| `nombre`|varchar|200|Nombre cliente tipo persona|
| `apellido`|varchar|200|Apellido cliente tipo persona|
| `tipo_identificacion`|decimal|1|Tipo de identificación del cliente|
| `identificacion`|varchar|15|Número de cédula o ruc del cliente|
| `tipo_persona`|decimal|1|Tipo de persona del cliente (Persona o Empresa)|
| `direccion`|varchar|200|Dirección del cliente|
| `contacto`|objeto|-|Si|Objeto contenedor del contacto del cliente|