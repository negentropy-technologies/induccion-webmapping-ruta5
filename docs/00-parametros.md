# 00. Parámetros del proyecto

Esta es la única tabla con valores propios del proyecto. Los demás archivos citan cada valor con su identificador, por ejemplo "(P-08: 1 m)". Para reutilizar el paquete, cambie esta tabla y luego actualice cada identificador en los demás archivos (ver `README.md`).

| ID | Parámetro | Valor en este proyecto | Estado |
|---|---|---|---|
| P-01 | Nombre del proyecto | Visor web de la Ruta 5 en la Región Metropolitana | Cerrado |
| P-02 | Territorio de trabajo | Comuna de Colina, Región Metropolitana | Propuesto |
| P-03 | Referencia de verificación | QGIS (herramientas Identificar y Estadísticas zonales) | Cerrado |
| P-04 | Sistema de coordenadas de los ráster | EPSG:32719 (UTM 19 sur, metros) | Verificado en los archivos |
| P-05 | Mapas base | Esri oscuro, Esri satélite y OpenStreetMap | Cerrado |
| P-06 | Tolerancia de clase de cobertura | Coincidencia exacta con QGIS | Propuesto |
| P-07 | Tolerancia de altura | 1 m o menos de diferencia con QGIS | Cerrado |
| P-08 | Tolerancia de pendiente media de un área (diferencia permitida con QGIS, en grados; no es lo mismo que las clases de P-20) | 1 grado, provisional; el docente la confirma o ajusta tras medir la solución de referencia | Provisional |
| P-09 | Puntos de control por participante | 10 puntos | Propuesto |
| P-10 | Polígonos de control por participante | 3 polígonos, cada uno en una clase de pendiente distinta (P-20) | Propuesto |
| P-11 | Tamaño máximo por archivo | 25 MiB | Verificado (límite de subida web de GitHub) |
| P-12 | Intentos máximos por criterio antes de escalar | 3 | Propuesta práctica, sin sustento bibliográfico |
| P-13 | Ramas | `master` (publica), `develop` (integración), una rama por participante con su nombre | Cerrado |
| P-14 | Carpeta de trabajo de cada participante | `participantes/<nombre>/` | Propuesto |
| P-15 | Variantes de trabajo | A cobertura, B relieve, C riesgo | Propuesto |
| P-16 | Publicación | GitHub Pages desde `master` | Cerrado |
| P-17 | Cobertura del suelo | MapBiomas Chile, año 2024, 30 m, 16 clases presentes | Verificado en el archivo |
| P-18 | Elevación | DEM de la Región Metropolitana, altura en metros enteros, píxel de 12,5 m declarado | Resolución por confirmar |

## Clases de pendiente (P-20)

La pendiente se expresa en **grados**. Las clases sirven para clasificar y para elegir los polígonos de control. Definidas por el responsable del proyecto.

| Clase | Rango (grados) | Rango equivalente en porcentaje |
|---|---|---|
| 1, plana | 0 a 5 | 0 a 8,7 % |
| 2 | 5 a 10 | 8,7 a 17,6 % |
| 3 | 10 a 25 | 17,6 a 46,6 % |
| 4 | 25 o más (incluye todo lo que supera los 45) | 46,6 % o más |

El terreno de más de 45 grados se agrupa en la clase 4 (decisión del responsable). Los porcentajes se calculan como 100 por la tangente del ángulo.

## Versiones de librerías (P-19)

Versiones fijas. Nunca se usa "latest". Consultadas en npm el 18-10-2026.

| Librería | Versión | Uso |
|---|---|---|
| Leaflet | 1.9.4 | Mapa y capas |
| leaflet.markercluster | 1.5.3 | Agrupación de puntos |
| georaster-layer-for-leaflet | 4.1.2 | Dibuja GeoTIFF en el mapa |
| GeoBlaze | 2.8.0 | Valor en un punto y estadísticas de un área |
| proj4 | 2.22.0 | Reproyecta el clic al sistema del ráster |
| Leaflet-Geoman | 2.20.2 | Dibujo de áreas. Compatibilidad con Leaflet 1.9.4 por confirmar |

## Cómo leer la columna "Estado"

- **Cerrado:** decidido por el responsable del proyecto.
- **Verificado:** comprobado en un archivo o en la documentación de la fuente.
- **Propuesto:** propuesta del equipo docente; puede cambiar antes del taller.
- **Pendiente:** falta medir o decidir. Una tarea no puede darse por cumplida contra un parámetro pendiente.
