# Notificación

## Objeto Notificaciones

``` json title="Objeto Notificaciones:"
[	
    {
	"id": "5422",
    "campana": 
    {
        "campana_id": "5431",
        "tipo": "WS",
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
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "05/06/2023 11:02:43",
        "fecha_actualizacion": "05/06/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	}
]
```

Atributos de un objeto Notificaciones:

Los tipos de campaña son:

| Valor       | Tipo                                 |
| ----------- | ------------------------------------ |
| `WS`       | Whatsapp                               |
| `EM`       | Email|

| Parámetro   | Tipo    | Longitud | Descripción |
| ----------- | ------- | -------- | ----------- |
| `id`|varchar|10|Identificador de la notificación|
| `campana_id`|varchar|10|Identificador de la campaña a la que pertenece la notificación|
| `tipo`|varchar|15|Tipo de campaña (whatsapp o email)|
| `plantilla_id`|varchar|10|Identificador de la plantilla que se utilizó en la notificación|
| `nombre_plantilla`|varchar|200|Nombre de la plantilla que se utilizó en la notificación|
| `contacto_id`|varchar|10|Identificador del contacto|
| `cliente_id`|varchar|10|Identificador del cliente|
| `contacto_nombre`|varchar|200|Nombre del contacto|
| `contacto_apellido`|varchar|200|Apellido del contacto|
| `contacto_movil`|varchar|20|Movil del contacto|
| `contacto_email`|varchar|20|Email del contacto|
| `fecha_envio`|date|-|Fecha de envío de la notificación|
| `fecha_actualizacion`|date|-|Fecha de la actualización del estado del mensaje|
| `estado`|varchar|20|Estado de la notificación, leído, entregado, error|

## Obtener notificaciones por rango de fechas (GET)

Se puede obtener una lista de todas las notificaciones enviadas por rango de fecha.

`GET https://api.conpronto.com/notificacion/?fecha_inicial=<FECHA_INICIAL>&fecha_final=<FECHA_FINAL>/`

Ejemplo:

`GET https://api.conpronto.com/notificacion/?fecha_inicial=1/02/2023&fecha_final=28/02/2023/`

``` json title="Respuesta al consultar un listado de notificaciones:"
[	
    {
	"id": "5422",
    "campana": 
    {
        "campana_id": "5431",
        "tipo": "WS",
        "nombre_camp": "05.02.2023 11:01:16",
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
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "05/02/2023 11:02:43",
        "fecha_actualizacion": "05/02/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
    {
	"id": "5688",
    "campana": 
    {
        "campana_id": "8545",
        "tipo": "EM",
        "nombre_camp": "25.02.2023 11:01:16",
	"plantilla": 
        {
        "plantilla_id": "784",
        "nombre_temp": "VENCIDO_PLANTILLA_B",
        }
    },
	"contacto": 
    {
        "contacto_id": "115",
        "cliente_id": "754",
        "contacto_nombre": "Juan",
        "contacto_apellido": "López",
        "contacto_movil": "+593978545512",
        "contacto_email ": "jlopez@gmail.com"
    },
	    "fecha_envio": "25/02/2023 11:02:43",
        "fecha_actualizacion": "25/02/2023 11:02:45",
	    "estado": "Mailgun Delivered"
	},
]
```

## Obtener notificaciones por cliente (GET)

`GET https://api.conpronto.com/cliente/<ID>/notificacion`

Devuelve las notificaciones enviadas a un cliente con el <ID> solicitado.

``` json title="Respuesta al consultar un listado de notificaciones:"
[	
    {
	"id": "5422",
    "campana": 
    {
        "campana_id": "5431",
        "tipo": "WS",
        "nombre_camp": "05.02.2023 11:01:16",
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
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "05/02/2023 11:02:43",
        "fecha_actualizacion": "05/02/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
    {
	"id": "5688",
    "campana": 
    {
        "campana_id": "8545",
        "tipo": "EM",
        "nombre_camp": "25.02.2023 11:01:16",
	"plantilla": 
        {
        "plantilla_id": "784",
        "nombre_temp": "VENCIDO_PLANTILLA_B",
        }
    },
	"contacto": 
    {
        "contacto_id": "113",
        "cliente_id": "491",
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "25/02/2023 11:02:43",
        "fecha_actualizacion": "25/02/2023 11:02:45",
	    "estado": "Mailgun Delivered"
	},
]
```

## Obtener notificaciones por tipo de campaña (GET)

`GET https://api.conpronto.com/notificacion/<TIPO_CAMPAÑA>/`

Usando el código del tipo de campaña (WS o EM) de pago en la creación del cobro.

``` json title="Respuesta al consultar un listado de notificaciones:"
[	
    {
	"id": "5422",
    "campana": 
    {
        "campana_id": "5431",
        "tipo": "WS",
        "nombre_camp": "05.02.2023 11:01:16",
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
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "05/02/2023 11:02:43",
        "fecha_actualizacion": "05/02/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
    {
	"id": "5688",
    "campana": 
    {
        "campana_id": "8545",
        "tipo": "WS",
        "nombre_camp": "25.02.2023 11:01:16",
	"plantilla": 
        {
        "plantilla_id": "784",
        "nombre_temp": "VENCIDO_PLANTILLA_B",
        }
    },
	"contacto": 
    {
        "contacto_id": "113",
        "cliente_id": "491",
        "contacto_nombre": "Andrés",
        "contacto_apellido": "López",
        "contacto_movil": "+593942985587",
        "contacto_email ": "alopez@gmail.com"
    },
	    "fecha_envio": "25/02/2023 11:02:43",
        "fecha_actualizacion": "25/02/2023 11:02:45",
	    "estado": "WhatsApp Delivered"
	},
]
```