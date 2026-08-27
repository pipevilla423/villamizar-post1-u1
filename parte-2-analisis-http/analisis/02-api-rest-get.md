# Análisis 2: Peticiones GET a API REST — JSONPlaceholder

## Objetivo

Analizar el comportamiento de una API REST pública mediante dos peticiones HTTP GET realizadas a JSONPlaceholder. La primera petición consulta un recurso existente (`/posts/1`) y la segunda consulta un recurso inexistente (`/posts/999`), permitiendo comparar los códigos de estado `200 OK` y `404 Not Found`.

---

# Petición 1 — GET de recurso existente

## Información general

- URL: https://jsonplaceholder.typicode.com/posts/1
- Método HTTP: GET
- Código de estado: 200 OK
- Tipo de contenido recibido: application/json; charset=utf-8

El código `200 OK` indica que la petición fue procesada correctamente y que el recurso solicitado existe.

## Headers de Request

| Header | Valor |
|--------|-------|
| :authority | jsonplaceholder.typicode.com |
| User-Agent | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36 |
| Accept | text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7 |

## Headers de Response

| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | application/json; charset=utf-8 | Indica que el servidor devolvió información en formato JSON codificada en UTF-8. |
| Cache-Control | max-age=43200 | Permite almacenar la respuesta en caché durante un máximo de 43200 segundos, equivalentes a 12 horas. |
| Date | Thu, 27 Aug 2026 04:47:21 GMT | Indica la fecha y hora en que el servidor generó la respuesta HTTP. |

## Response

La respuesta obtenida fue:

    {
      "userId": 1,
      "id": 1,
      "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
      "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
    }

La respuesta contiene un objeto JSON con los campos `userId`, `id`, `title` y `body`. Esto confirma que el recurso `/posts/1` existe y que la API devolvió correctamente la información correspondiente a la publicación con identificador `1`.

---

# Petición 2 — GET de recurso inexistente

## Información general

- URL: https://jsonplaceholder.typicode.com/posts/999
- Método HTTP: GET
- Código de estado: 404 Not Found
- Tipo de contenido recibido: application/json; charset=utf-8

El código `404 Not Found` indica que el servidor recibió y procesó la petición, pero no encontró el recurso solicitado.

## Headers de Request

| Header | Valor |
|--------|-------|
| :authority | jsonplaceholder.typicode.com |
| User-Agent | Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36 |
| Accept | text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7 |

## Headers de Response

| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | application/json; charset=utf-8 | Indica que la respuesta enviada por el servidor utiliza formato JSON codificado en UTF-8. |
| Cache-Control | max-age=43200 | Permite almacenar la respuesta en caché durante un máximo de 43200 segundos, equivalentes a 12 horas. |
| Date | Thu, 27 Aug 2026 04:59:58 GMT | Indica la fecha y hora en que el servidor generó esta respuesta HTTP. |

## Response

La respuesta obtenida fue:

    {}

El servidor devolvió un objeto JSON vacío. Esto ocurre porque no existe una publicación asociada al identificador `999`.

Además, el código `404 Not Found` confirma que el recurso solicitado no fue encontrado.

---

# Comparación entre las dos peticiones a la API REST

| Característica | `/posts/1` | `/posts/999` |
|----------------|------------|--------------|
| Método HTTP | GET | GET |
| Código de estado | 200 OK | 404 Not Found |
| Recurso solicitado | Existente | Inexistente |
| Content-Type | application/json; charset=utf-8 | application/json; charset=utf-8 |
| Cache-Control | max-age=43200 | max-age=43200 |
| Response | Objeto JSON con datos | Objeto JSON vacío `{}` |
| Resultado | Petición exitosa | Recurso no encontrado |

Las dos solicitudes utilizan el mismo método HTTP `GET` y se realizan al mismo dominio. Sin embargo, el resultado cambia dependiendo de si el recurso solicitado existe.

La petición a `/posts/1` devuelve `200 OK` junto con un objeto JSON que contiene los datos de la publicación. En cambio, `/posts/999` devuelve `404 Not Found` y un objeto JSON vacío `{}`, debido a que el recurso solicitado no existe.

---

# Comparación entre página HTML y API REST

| Característica | Página HTML — example.com | API REST — JSONPlaceholder |
|----------------|---------------------------|----------------------------|
| Método HTTP | GET | GET |
| Código exitoso | 200 OK | 200 OK |
| Content-Type | text/html | application/json; charset=utf-8 |
| Tipo de información | Documento HTML | Datos estructurados en JSON |
| Uso principal | Mostrar contenido de una página web | Intercambiar datos entre cliente y servidor |

## Análisis de la comparación

Tanto una página web tradicional como una API REST pueden utilizar el método HTTP `GET` para solicitar información a un servidor. La diferencia principal observada se encuentra en el tipo de contenido que devuelve cada servicio.

En la petición realizada a `example.com`, el servidor respondió utilizando `Content-Type: text/html`, ya que el recurso corresponde a un documento HTML diseñado para ser interpretado por el navegador.

En las peticiones realizadas a JSONPlaceholder, el servidor respondió utilizando `Content-Type: application/json; charset=utf-8`. Esto indica que la información entregada por la API está estructurada en formato JSON, adecuado para el intercambio y procesamiento de datos entre aplicaciones.

También se observó la importancia de los códigos de estado HTTP. Una solicitud correcta a un recurso existente produjo `200 OK`, mientras que la solicitud a un recurso inexistente produjo `404 Not Found`.

---

# Conclusión

El análisis permitió observar el funcionamiento de peticiones HTTP GET realizadas a una API REST pública. La petición a `/posts/1` obtuvo una respuesta `200 OK` y devolvió un objeto JSON con la información del recurso solicitado. En cambio, la petición a `/posts/999` obtuvo `404 Not Found` y devolvió un objeto JSON vacío, indicando que el recurso no existe.

Además, la comparación con una página HTML permitió identificar la diferencia entre `Content-Type: text/html` y `Content-Type: application/json; charset=utf-8`. Los códigos de estado y los headers HTTP proporcionan información esencial para interpretar correctamente la comunicación entre un cliente y un servidor.