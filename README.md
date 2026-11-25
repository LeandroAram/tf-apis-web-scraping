# tf-apis-web-scraping
Trabajo Final Evaluativo de APIs y Web Crawling/Web Scraping — Aramayo Pedro Mauricio Leandro (3.er año, Ciencias de Datos e IA).

**Abrir en Colab:** https://colab.research.google.com/github/LeandroAram/tf-apis-web-scraping/blob/devin/1795598835-notebook-tf/TF_APIs_WebScraping.ipynb
(cuando la rama se una a `main`, reemplazar el nombre de la rama por `main` en el enlace y en la variable `RAMA` de la primera celda).

## Contenido
- `TF_APIs_WebScraping.ipynb`: los 10 ejercicios con la numeración del PDF, ejecutado y con salidas guardadas. Al final tiene la tabla de estado y el guion de 2 minutos.
- `datos/`: datos reales recolectados para repetir la demostración sin depender de recolecciones lentas.

| Archivo | Ejercicio | Contenido |
|---|---|---|
| `ej1_historial_mercadolibre.csv` | 1 | Se crea solo si Mercado Libre deja leer la página (hoy bloquea con captcha). |
| `ej2_historial_avisos.csv` | 2 | Avisos de Gol Trend de RosarioGarage, Autocosmos y Kavak, con fecha de cada ejecución. |
| `ej3_busqueda_inflacion.csv` / `noticias_inflacion.csv` | 3, 10 | Resultados de Google News por diario y 130 notas con texto completo (13 por diario). |
| `ej3_busqueda_economia.csv` / `noticias_economia.csv` | 9 | 80 notas de economía de los mismos diarios, para la expansión de consultas. |
| `ej4_sedici_informatica.csv` | 4 | 2.618 registros OAI-PMH de SEDICI (Facultad de Informática, UNLP). |
| `ej7_x_indec.csv` | 7 | 70 publicaciones de @INDECArgentina vía Nitter. |
| `ej8_tuit_principal.csv` / `ej8_respuestas_tuit.csv` | 8 | Un tuit de @INDECArgentina y 80 respuestas. |
| `ej9_tesauro_unesco.csv` | 9 | Términos del Tesauro UNESCO relacionados con "Inflación" (copia de respaldo del SPARQL). |
| `prueba_clase.txt` | 5 | Documento con la palabra "ornitorrinco" para probar el indexador. |

## Cómo repetir la demo
1. Abrir el enlace de Colab y ejecutar *Entorno de ejecución → Ejecutar todas*. La primera celda clona este repositorio para tener la carpeta `datos/`.
2. Las celdas de búsqueda en vivo (puntos 2, 3, 4 y 9) consultan las fuentes en el momento. Las recolecciones lentas usan los CSV; se repiten poniendo `RECOLECTAR_TEXTOS`, `RECOLECTAR_SEDICI` o `RECOLECTAR_X` en `True`.
3. Cada ejecución del punto 2 agrega una fila por aviso al historial y compara contra la ejecución anterior para emitir alertas.

## Limitaciones verificadas
- **Mercado Libre (1):** la búsqueda redirige a `captcha/wall/web-risk-verification` y la API responde 403 desde IPs de centros de datos. No se usaron datos inventados.
- **Facebook (6):** la página de Infobae redirige a inicio de sesión; sin login no se ven publicaciones.
