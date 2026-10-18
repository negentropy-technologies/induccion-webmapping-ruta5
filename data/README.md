# Datos

Capas de la Región Metropolitana de Santiago de Chile en sistema de coordenadas EPSG:32719 (ráster) y GeoJSON (vectores). La fuente, la fecha y la licencia de cada capa se declaran en [`../docs/06-contrato-datos.md`](../docs/06-contrato-datos.md).

| Carpeta | Contenido |
|---|---|
| `geojson/` | 17 capas vectoriales: Ruta 5 y corredor de 2 km, división político-administrativa, hidrografía, cuencas, puentes, emergencias, estaciones, remociones en masa y uso urbano |
| `raster/` | Modelo digital de elevación (`dem_metropolitana.tif`) y cobertura del suelo MapBiomas Chile 2024 (`mapbiomas_2024_rm_32719.jp2`), con sus archivos `.aux.xml` de estadísticas |

## No incluido

- `geojson/mapbiomas_2024_rm_32719.geojson` (105 MB) supera el límite de 100 MB por archivo de GitHub. La cobertura del suelo se entrega en el ráster `mapbiomas_2024_rm_32719.jp2`.
- El reporte de descarga del servidor de origen, porque contiene datos de acceso internos.
