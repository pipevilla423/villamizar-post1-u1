# Análisis 1: Petición GET — example.com

## Información general
- URL: https://example.com
- Método: GET
- Código de estado: [200 OK]

## Headers de Request
| Header | Valor |
|--------|-------|
| Host | [example.com] |
| User-Agent | [Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36] |
| Accept | [text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7] |

## Headers de Response
| Header | Valor | Significado |
|--------|-------|-------------|
| Content-Type | [text/html] | [indica que la respuesta tiene contenido html] |
| Cache-Control | [no aparece en esta respuesta] | [no fue enviado por el servidor en esta captura] |

## Tiempos de carga
| Fase | Tiempo (ms) |
|------|------------|
| DNS Lookup | [no registrado] |
| TTFB | [58.66 ms] |

## Conclusión
[La petición realizada a https://example.com/ utilizó el método GET y respondió correctamente con un código 200 OK. El servidor devolvió contenido de tipo text/html, lo que confirma que la respuesta corresponde a una página web en formato HTML. El tiempo de espera del servidor (TTFB) fue de 58.66 ms y la descarga del contenido tomó 0.33 ms, mostrando una respuesta rápida. Las fases de DNS, conexión inicial y SSL no aparecieron registradas en esta medición, probablemente porque el navegador reutilizó una conexión previamente establecida.]