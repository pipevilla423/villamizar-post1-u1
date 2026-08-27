# Análisis 3: Petición POST simulada con Postman

## Objetivo

Realizar y analizar una petición HTTP POST utilizando Postman contra la API pública de pruebas JSONPlaceholder. La petición permite observar el envío de un cuerpo JSON, la respuesta del servidor, los headers relevantes y la ejecución de tests automatizados.

---

## Configuración de la petición

- Método HTTP: POST
- URL: https://jsonplaceholder.typicode.com/posts
- Content-Type: application/json

## Body enviado

    {
      "title": "Laboratorio Programacion Web",
      "body": "Analisis de peticiones HTTP con Postman.",
      "userId": 1
    }

El cuerpo fue enviado en formato JSON utilizando la opción `Body → raw → JSON` de Postman.

---

## Respuesta recibida

### Código de estado

- Código: 201 Created

El código `201 Created` indica que el servidor recibió correctamente la petición y simuló la creación de un nuevo recurso.

### Body de respuesta

    {
      "title": "Laboratorio Programacion Web",
      "body": "Analisis de peticiones HTTP con Postman.",
      "userId": 1,
      "id": 101
    }

La respuesta contiene los mismos datos enviados en la petición y agrega el campo `id` con valor `101`, asignado por el servidor.

---

## Headers de Response

| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | application/json; charset=utf-8 | Indica que la respuesta está estructurada en formato JSON y utiliza codificación UTF-8. |
| X-Powered-By | Express | Indica que el servidor utiliza Express como tecnología del lado del servidor. |
| Location | https://jsonplaceholder.typicode.com/posts/101 | Indica la ubicación asociada al recurso creado de forma simulada. |

---

## Tests automatizados

Se agregaron los siguientes tests en Postman:

    pm.test("Status 201 Created", () => {
      pm.response.to.have.status(201);
    });

    pm.test("Respuesta incluye id asignado", () => {
      const json = pm.response.json();
      pm.expect(json).to.have.property("id");
      pm.expect(json.title).to.equal("Laboratorio Programacion Web");
    });

## Resultado de los tests

| Test | Resultado |
|------|-----------|
| Status 201 Created | PASSED |
| Respuesta incluye id asignado | PASSED |

Los dos tests fueron ejecutados correctamente y Postman mostró un resultado de `2/2` tests aprobados.

El primer test verifica que el código HTTP de respuesta sea `201`. El segundo comprueba que el objeto JSON retornado incluya un campo `id` y que el título recibido corresponda al valor enviado originalmente.

---

## Comparación entre GET y POST

| Característica | GET | POST |
|----------------|-----|------|
| Propósito | Obtener información de un recurso | Enviar información para crear un recurso |
| Body de Request | Normalmente no se utiliza | Contiene los datos enviados al servidor |
| Ejemplo utilizado | GET /posts/1 | POST /posts |
| Código exitoso observado | 200 OK | 201 Created |
| Datos enviados | No se envió un cuerpo JSON | Se envió un objeto JSON |
| Respuesta | Recurso solicitado | Recurso creado de forma simulada con un nuevo id |

## Análisis de la comparación

El método HTTP `GET` se utilizó anteriormente para consultar recursos existentes sin enviar un cuerpo con información al servidor. En cambio, el método `POST` permitió enviar un objeto JSON para simular la creación de un nuevo recurso.

La petición GET exitosa respondió con `200 OK`, mientras que la petición POST respondió con `201 Created`. Esta diferencia refleja el propósito de cada método: `200 OK` indica que una solicitud fue procesada correctamente, mientras que `201 Created` se utiliza cuando la operación produce la creación de un recurso.

Además, en la petición POST fue necesario especificar `Content-Type: application/json`, ya que el cliente envió información estructurada en formato JSON al servidor.

---

## Conclusión

La petición POST realizada con Postman permitió observar el proceso de envío de información en formato JSON hacia una API REST. El servidor respondió con el código `201 Created` y retornó los datos enviados junto con un campo `id` igual a `101`.

También se verificó el funcionamiento de la respuesta mediante dos tests automatizados, los cuales fueron aprobados correctamente. La actividad permitió identificar diferencias importantes entre los métodos GET y POST, especialmente en cuanto al propósito de la petición, el uso de un cuerpo de solicitud y los códigos de estado devueltos por el servidor.