# Post-contenido — Unidad 1: Fundamentos de la Web

## Descripción

Repositorio del laboratorio de la Unidad 1 de Programación Web — Séptimo Semestre. Contiene dos partes: configuración del entorno de desarrollo (`parte-1-entorno/`) y análisis de peticiones HTTP con Chrome DevTools y Postman (`parte-2-analisis-http/`).

## Parte 1 — Entorno de desarrollo

Página HTML básica desarrollada con HTML, CSS y JavaScript e inspeccionada utilizando Chrome DevTools.

Ver:

`parte-1-entorno/`

## Parte 2 — Análisis de peticiones HTTP

| # | Tipo               | URL                                            | Código        |
| - | ------------------ | ---------------------------------------------- | ------------- |
| 1 | GET HTML           | https://example.com                            | 200 OK        |
| 2 | GET JSON (exitoso) | https://jsonplaceholder.typicode.com/posts/1   | 200 OK        |
| 3 | GET JSON (fallido) | https://jsonplaceholder.typicode.com/posts/999 | 404 Not Found |
| 4 | POST JSON          | https://jsonplaceholder.typicode.com/posts     | 201 Created   |

Los análisis detallados se encuentran en:

`parte-2-analisis-http/analisis/`

## Herramientas utilizadas

* Visual Studio Code
* Git
* GitHub
* Google Chrome
* Chrome DevTools
* Postman

## Conclusiones

Durante el laboratorio se configuró un entorno básico de desarrollo web utilizando VS Code, Git y GitHub, permitiendo gestionar los cambios del proyecto mediante commits y un repositorio remoto. Con Chrome DevTools fue posible inspeccionar la estructura del DOM y analizar peticiones HTTP reales, identificando métodos, códigos de estado, headers y tipos de contenido. También se analizaron respuestas exitosas y fallidas de una API REST, observando códigos como `200 OK` y `404 Not Found`. Finalmente, mediante Postman se realizó una petición `POST` que respondió con `201 Created` y se verificó su funcionamiento mediante tests automatizados.
