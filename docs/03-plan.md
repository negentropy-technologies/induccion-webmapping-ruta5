# 03. Plan técnico

El plan dice cómo se construye lo que dice la especificación. Cada decisión indica por qué se tomó.

## Arquitectura

Sitio **estático**: el servidor (GitHub Pages) solo entrega archivos y todo el cálculo ocurre en el navegador de cada persona (R-02). En rigor, no es una arquitectura serverless: no usa servicios de terceros ni funciones propias en un proveedor (Fowler, 2016; MDN, "Client-Server overview"). Comparte con serverless que no se administra ningún servidor.

## Tecnología

Versiones exactas en `00-parametros.md`, tabla P-19.

| Función | Elección | Por qué |
|---|---|---|
| Mapa | Leaflet | Es la librería del visor de referencia de Negentropy |
| Agrupación de puntos | leaflet.markercluster | Misma que el visor de referencia |
| Dibujar ráster en el mapa | georaster-layer-for-leaflet | Lee GeoTIFF en el navegador |
| Valor y estadísticas de ráster | GeoBlaze | Ofrece consulta de punto (identify) y estadísticas por geometría; no ofrece funciones de terreno |
| Reproyección del clic | proj4 | GeoBlaze exige que el punto y el ráster compartan el sistema de coordenadas (P-04) |
| Dibujo de áreas | Leaflet-Geoman | Mantenimiento más reciente que Leaflet.draw. Compatibilidad con Leaflet 1.9.4 por probar |
| Publicación | GitHub Pages con GitHub Actions | Gratuito y estático (P-16) |

**Por qué no TiTiler.** TiTiler ofrece teselas con paleta a medida, consulta de valor en un punto y estadísticas por polígono, y es la opción natural cuando hay servidor. En un sitio público de GitHub Pages no es posible, porque Pages no ejecuta servidores. Se mantiene como modo local opcional.

## Cálculo de pendiente

- **Camino A (núcleo).** El docente calcula en QGIS un ráster de pendiente a partir del DEM, que está en metros (P-04), por lo que no hay problema de escala en grados. El visor calcula la media y el máximo de ese ráster dentro del área dibujada. Coincide con QGIS por construcción.
- **Camino B (ampliación).** El visor calcula la pendiente desde el DEM. Requiere implementar un algoritmo de pendiente (por ejemplo, el de Horn, 1981) y verificarlo contra QGIS. Solo para quien termine antes.

## Estructura del repositorio

| Ruta | Contenido | Quién lo edita |
|---|---|---|
| `docs/` | Método de trabajo (SDD) y diagramas | Docente |
| `site/` | Núcleo común del visor y carpeta de datos | Docente |
| `participantes/<nombre>/` | Variante de cada participante (P-14) | Cada participante |
| `.github/` | Plantilla de PR y flujo de publicación | Docente |

## Modos de ejecución

| Modo | Qué usa | Para qué |
|---|---|---|
| Local simple | Un servidor de archivos estáticos | Trabajo diario |
| Publicado | GitHub Pages desde `master` (P-16) | URL pública |
| Local con Docker (opcional) | Servidor de teselas vectoriales y TiTiler | Mostrar la arquitectura completa; fuera del núcleo |

## Flujo de ramas

1. Se clona el repositorio.
2. Se crea una rama desde `develop` con el nombre del participante (P-13).
3. Se trabaja solo en la carpeta propia (R-08).
4. Se abre un pull request hacia `develop` con el checklist.
5. El docente revisa y, cuando todo cumple, pasa `develop` a `master`, que publica el sitio.

## Fuentes

- Fowler, M. (2016). Serverless Architectures. https://martinfowler.com/articles/serverless.html
- MDN Web Docs. Client-Server overview. https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview
- GeoBlaze. https://geoblaze.io
- georaster-layer-for-leaflet. https://github.com/GeoTIFF/georaster-layer-for-leaflet
- TiTiler. Endpoints COG. https://developmentseed.org/titiler/endpoints/cog/
- Horn, B. K. P. (1981). Hill shading and the reflectance map. Proceedings of the IEEE, 69(1), 14 a 47. (Pendiente de verificar en línea.)
