# 06. Contrato de datos

Qué datos usa el visor, de dónde vienen y cuáles se publican. Cada capa declara fuente, fecha y licencia (R-06). Las columnas "por completar" las llena el docente al preparar los datos.

## Reglas generales

- Los datos se leen solo desde `site/datos/` (R-04).
- Ningún archivo supera P-11 (25 MiB).
- GeoJSON en WGS 84, con la coordenada en orden longitud, latitud (IETF, RFC 7946).
- Ráster en GeoTIFF y en el sistema de coordenadas P-04.
- Las capas pesadas se recortan al territorio de trabajo (P-02).

## Capas de toda la región, publicadas completas

| Capa | Tipo | Tamaño aprox. | Fuente | Fecha | Licencia |
|---|---|---|---|---|---|
| eje_ruta5_rm | Línea | 0,4 MB | Por completar | Por completar | Por completar |
| corredor_2km_rm | Polígono | 0,5 MB | Por completar | Por completar | Por completar |
| dpa_region_rm, dpa_provincia_rm, dpa_comuna_rm | Polígono | 0,6; 1,1 y 2,0 MB | Por completar | Por completar | Por completar |
| puentes_vialidad_rm | Punto | 0,3 MB | Por completar | Por completar | Por completar |
| emergencias_mop_rm y emergencias_historicas_mop_rm | Punto | 0,2 y 0,03 MB | Por completar | Por completar | Por completar |
| estaciones_dga_dmc_agromet_rm | Punto | 0,3 MB | Por completar | Por completar | Por completar |
| remociones_lbp_rm y remociones_sernageomin_rm | Punto | 0,2 y 0,4 MB | Por completar | Por completar | Por completar |

## Capas recortadas al territorio de trabajo

| Capa | Tratamiento | Tamaño final |
|---|---|---|
| hidrografia_rm | Recorte al territorio (P-02) | Por medir |
| uso_urbano_conaf_rm | Recorte al territorio (P-02) | Por medir |
| Cobertura MapBiomas 2024 | Conversión a GeoTIFF y recorte | Por medir |
| DEM | Recorte | Por medir |
| Pendiente (derivada del DEM) | Calculada en QGIS sobre el recorte | Por medir |

## Cobertura del suelo: leyenda de 16 clases

Tomada de la capa categorizada del proyecto de QGIS. El ráster tiene dato en el 57 % de sus píxeles; el resto es sin dato (código 0). Los nombres y colores no se contrastaron con una tabla oficial de MapBiomas Chile.

| Código | Clase | Color | Código | Clase | Color |
|---|---|---|---|---|---|
| 9 | Silvicultura | #7A5900 | 34 | Hielo y nieve | #93DFE6 |
| 11 | Humedal | #519799 | 59 | Bosque Primario | #1F8D49 |
| 12 | Pastizal | #D6BC74 | 60 | Bosque Secundario | #5CB85D |
| 15 | Pastura | #EDDE8E | 61 | Salar | #F5D5D5 |
| 18 | Agricultura | #E974ED | 63 | Estepa | #C7E0AB |
| 23 | Arena, playa y duna | #FFA07A | 66 | Matorral | #A89358 |
| 24 | Infraestructura | #D4271E | 25 | Otra área sin vegetación | #DB4D4F |
| 29 | Afloramiento rocoso | #FFAA5F | 33 | Río, lago u océano | #2532E4 |

## Atribuciones de los mapas base

Cada mapa base muestra su atribución visible (R-06). El texto exacto lo fija el docente tras verificar los términos de cada proveedor.

## No se publica

- Reportes de descarga que contengan direcciones IP, usuarios o rutas de servidores.
- Carpetas de formatos duplicados (GeoPackage y Shapefile).
- Manifiestos de descarga con las URL de origen, hasta revisarlas.
- El GeoJSON completo de MapBiomas y las versiones completas de hidrografía y uso urbano.

## Si agrega una capa

Declare su fuente, fecha, licencia y tratamiento en este archivo, y verifique que cumple P-11.

## Fuentes

- IETF (2016). RFC 7946, The GeoJSON Format. https://datatracker.ietf.org/doc/html/rfc7946
- MapBiomas Chile. Metodología, Colección 2.0. https://chile.mapbiomas.org
