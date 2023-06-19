# Notificaciones

## Obtener un listado de notificaciones por rango de fechas

Se puede obtener una lista de todas las notificaciones enviadas por rango de fecha.

`GET https://api.conpronto.com/v1/notificacion/?fecha_inicial=<FECHA_INICIAL>&fecha_final=<FECHA_FINAL>`

``` json title="Respuesta al consultar un listado de notificaciones:"
[	
    {
	    "id": "5422",
        "campana": 
        {
            "campana_id": "5431",
            "tipo": "WhatsApp",
            "nombre_camp": "05.06.2023 11:01:16",
	    "plantilla": 
        {
            "plantilla_id": "452",
            "nombre_temp": "VENCIDO_PLANTILLA_B",
        }
        },
	    "contacto": 
        {
            "contacto_id": "113",
            "cliente_id": "491",
    	    "contacto_nombre": "Prueba",
    	    "contacto_apellido": "Prueba1",
    	    "contacto_movil": "0942985587",
    	    "contacto_email ": "noname@noname"
    	},
	    "fecha_envio": "05/06/2023 11:02:43",
        "fecha_actualizacion": "05/06/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
	{
	    "id": "5423",
        "campana": 
        {
            "campana_id": "5421",
            "tipo": "Email",
            "nombre_camp": "05.06.2023 11:02:50",
	    "plantilla": 
        {
            "plantilla_id": "453",
            "nombre_temp": "VENCIDO_PLANTILLA_B_EMAIL",
        }
       },
	    "contacto": 
        {
            "contacto_id": "113",
            "cliente_id": "491",
    	    "contacto_nombre": "Prueba",
    	    "contacto_apellido": "Prueba1",
    	    "contacto_movil": "0942985587",
    	    "contacto_email ": "noname@noname"
    	},
	    "fecha_envio": "05/06/2023 11:03:15",
        "fecha_actualizacion": "05/06/2023 11:02:47",
	    "estado": "Mailgun Read"
	}
],...
```

Datos al obtener un listado de notificaciones:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|decimal|10|Identificador de la notificación|
| `campana_id`|decimal|10|Identificador de la campaña a la que pertenece la notificación|
| `tipo`|varchar|15|Tipo de campaña (whatsapp o email)|
| `plantilla_id`|decimal|10|Identificador de la plantilla que se utilizó en la notificación|
| `nombre_plantilla`|varchar|200|Nombre de la plantilla que se utilizó en la notificación|
| `contacto_id`|decimal|10|Identificador del contacto|
| `cliente_id`|decimal|10|Identificador del cliente|
| `contacto_nombre`|varchar|200|Nombre del contacto|
| `contacto_apellido`|varchar|200|Apellido del contacto|
| `contacto_movil`|varchar|20|Movil del contacto|
| `contacto_email`|varchar|20|Email del contacto|
| `fecha_envio`|date|-|Fecha de envío de la notificación|
| `fecha_actualizacion`|date|-|Fecha de la actualización del estado del mensaje|
| `estado`|varchar|20|Estado de la notificación, leído, entregado, error|

## Obtener un listado de mensajes por cliente

`GET https://api.conpronto.com/cliente/<ID>/notificacion`

Devuelve las notificaciones enviadas a un cliente con el <ID> solicitado.

``` json title="Respuesta al consultar un listado de notificaciones:"
[	
    {
	    "id": "5422",
        "campana": 
        {
            "campana_id": "5431",
            "tipo": "WhatsApp",
            "nombre_camp": "05.06.2023 11:01:16",
	    "plantilla": 
        {
            "plantilla_id": "452",
            "nombre_temp": "VENCIDO_PLANTILLA_B",
        }
        },
	    "contacto": 
        {
            "contacto_id": "113",
            "cliente_id": "491",
    	    "contacto_nombre": "Prueba",
    	    "contacto_apellido": "Prueba1",
    	    "contacto_movil": "0942985587",
    	    "contacto_email ": "noname@noname"
    	},
	    "fecha_envio": "05/06/2023 11:02:43",
        "fecha_actualizacion": "05/06/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
	{
	    "id": "5423",
        "campana": 
        {
            "campana_id": "5421",
            "tipo": "Email",
            "nombre_camp": "05.06.2023 11:02:50",
	    "plantilla": 
        {
            "plantilla_id": "453",
            "nombre_temp": "VENCIDO_PLANTILLA_B_EMAIL",
        }
       },
	    "contacto": 
        {
            "contacto_id": "113",
            "cliente_id": "491",
    	    "contacto_nombre": "Prueba",
    	    "contacto_apellido": "Prueba1",
    	    "contacto_movil": "0942985587",
    	    "contacto_email ": "noname@noname"
    	},
	    "fecha_envio": "05/06/2023 11:03:15",
        "fecha_actualizacion": "05/06/2023 11:02:47",
	    "estado": "Mailgun Read"
	}
],...
```

Datos al obtener un listado de notificaciones:

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|decimal|10|Identificador de la notificación|
| `campana_id`|decimal|10|Identificador de la campaña a la que pertenece la notificación|
| `tipo`|varchar|15|Tipo de campaña (whatsapp o email)|
| `plantilla_id`|decimal|10|Identificador de la plantilla que se utilizó en la notificación|
| `nombre_plantilla`|varchar|200|Nombre de la plantilla que se utilizó en la notificación|
| `contacto_id`|decimal|10|Identificador del contacto|
| `cliente_id`|decimal|10|Identificador del cliente|
| `contacto_nombre`|varchar|200|Nombre del contacto|
| `contacto_apellido`|varchar|200|Apellido del contacto|
| `contacto_movil`|varchar|20|Movil del contacto|
| `contacto_email`|varchar|20|Email del contacto|
| `fecha_envio`|date|-|Fecha de envío de la notificación|
| `fecha_actualizacion`|date|-|Fecha de la actualización del estado del mensaje|
| `estado`|varchar|20|Estado de la notificación, leído, entregado, error|