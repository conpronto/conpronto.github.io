# Introducción
¡Bienvenido a Pronto!

A continuación, encontrarás toda la documentación necesaria para integrarse a Pronto mediante nuestra API (Application Programming Interface).

``` html title="Url Base:"
https://api.conpronto.com/
```
## Autenticación

Pronto utiliza una clave de acceso, conocida como API Key, para acceder a sus servicios. Para obtenerla, es necesario tener una cuenta en Pronto y solicitarla a través del servicio de atención al cliente. Esta clave debe ser incluida y enviada como un parámetro en el encabezado de autenticación (AUTHORIZATION) en cada llamada al servicio que se utilice.

La API Key es el identificador único de tu Organización. Tiene la siguiente forma:
``` html title="API Key:"
01e108dbecdae02e315e6fdc0885b2c4
```
## Métodos Soportados

Los endpoints disponibles se deben invocar por alguno de los siguientes métodos HTTP.

| Metodos     |Uso                                 |
| ----------- | ---------------------------------- |
| `GET`       | Consulta                           |
| `POST`      | Inserción|
| `PUT`       | Modificación |
| `DELETE`    | Eliminación |

## Códigos de respuesta

Las respuestas a las llamadas a la API de Pronto utilizan la convención de códigos de estado HTTP para indicar si la llamada fue exitosa o fallida.

| Status   | Significado  | Descripción |
| ----------- | ------- | -------- 
| `200`|[OK](https://datatracker.ietf.org/doc/html/rfc7231#section-6.3.1)|La llamada fue exitosa|
| `201`|[Created](https://datatracker.ietf.org/doc/html/rfc7231#section-6.3.2)|Creado. La llamada fue exitosa y un nuevo objeto o grupo de objetos fue creado|
| `401`|[Unauthorized](https://datatracker.ietf.org/doc/html/rfc7235#section-3.1)|Falta de credenciales. No has incluido la API Key en el encabezado de la llamada, o lo has hecho utilizando un formato incorrecto.|
| `403`|[Forbidden](https://datatracker.ietf.org/doc/html/rfc7231#section-6.5.3)|Falta de permisos. La API Key que especificaste en el encabezado no tiene los permisos adecuados para realizar esta llamada.|
| `404`|[Not Found](https://datatracker.ietf.org/doc/html/rfc7231#section-6.5.4)|No encontrado. Según la API Key indicada en el Header, el recurso no existe. Esto también puede indicar que no tienes permitido realizar este tipo de llamada.|
| `422`|[Unprocessable Entity](https://datatracker.ietf.org/doc/html/rfc2518#section-10.3)|No Procesable. La solicitud está correctamente estructurada, pero presenta errores en cuanto a su significado. Es posible que hayas omitido campos obligatorios o incluido campos que no son pertinentes.|
| `429`|[Too Many Requests](https://datatracker.ietf.org/doc/html/rfc6585#section-4)|Demasiadas solicitudes. Llamaste muchas veces seguidas a la API.|

## URL's
Las siguientes son url's válidas para uso del api:

### Url's de cliente

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/cliente/`| POST |
| `https://api.conpronto.com/cliente/`| PUT |
| `https://api.conpronto.com/cliente/`| GET |
| `https://api.conpronto.com/cliente/`| GET |

### Url's de contactos

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/contacto/`| POST |
| `https://api.conpronto.com/contacto/`| PUT |
| `https://api.conpronto.com/cliente/<ID>/contacto/`| GET |

### Url's de documentos

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/registro/documento/`| POST |
| `https://api.conpronto.com/documento/`| PUT |
| `https://api.conpronto.com/documento/<ID>`| GET |
| `https://api.conpronto.com/documento/`| GET |

### Url's de cobros

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.contifico.com/documento/<ID>/cobro/`| POST |
| `https://api.conpronto.com/documento/<ID>/cobro/`| GET |
| `https://api.conpronto.com/cobro/datafast/`| GET |
| `https://api.conpronto.com/cobro/payphone/`| GET |

### Url's de retencion

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/documento/`| POST |
| `https://api.conpronto.com/documento/`| PUT |
| `https://api.conpronto.com/documento/<ID>`| GET |
| `https://api.conpronto.com/documento/`| GET |

### Url's de notificaciones

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/notificacion/?fecha_inicial=<FECHA_INICIAL>&fecha_final=<FECHA_FINAL>`| GET |
| `https://api.conpronto.com/cliente/<ID>/notificacion`| GET |