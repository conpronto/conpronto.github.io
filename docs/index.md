# Introducción
A continuación, encontrarán toda la documentación necesaria para integrarse a Pronto mediante nuestra API (Application Programming Interface)

## Métodos Soportados

Los endpoints disponibles se deben invocar por alguno de los siguientes métodos HTTP.

| Metodos     |Uso                                 |
| ----------- | ---------------------------------- |
| `GET`       | Consulta                           |
| `POST`      | Inserción|
| `PUT`       | Modificación |

## URL's
Las siguientes son url's válidas para uso del api:

### Url's de cliente

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/v1/clientes/?token=<TOKEN>`| POST |
| `https://api.conpronto.com/v1/clientes/?token=<TOKEN>`| PUT |
| `https://api.conpronto.com/v1/clientes/<ID>/`| GET |
| `https://api.conpronto.com/v1/clientes/`| GET |

### Url's de contactos

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/v1/contacto/?token=<TOKEN>`| POST |
| `https://api.conpronto.com/v1/contacto/?token=<TOKEN>`| PUT |
| `https://api.conpronto.com/cliente/<ID>/contactos/`| GET |

### Url's de documentos

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/registro/documento/`| POST |
| `https://api.conpronto.com/v1/documento/`| PUT |
| `https://api.conpronto.com/v1/documento/<ID>`| GET |
| `https://api.conpronto.com/v1/documento/`| GET |

### Url's de cobros

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.contifico.com/v1/documento/<ID>/cobro/`| POST |
| `https://api.conpronto.com/v1/documento/<ID>/cobro/`| GET |
| `https://api.conpronto.com/v1/cobro/datafast/`| GET |
| `https://api.conpronto.com/v1/cobro/payphone/`| GET |

### Url's de retencion

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/v1/documento/`| POST |
| `https://api.conpronto.com/v1/documento/`| PUT |
| `https://api.conpronto.com/v1/documento/<ID>`| GET |
| `https://api.conpronto.com/v1/documento/`| GET |

### Url's de notificaciones

| URL     |Método                                 |
| ----------- | ---------------------------------- |
| `https://api.conpronto.com/v1/notificacion/?fecha_inicial=<FECHA_INICIAL>&fecha_final=<FECHA_FINAL>`| GET |
| `https://api.conpronto.com/cliente/<ID>/notificacion`| GET |