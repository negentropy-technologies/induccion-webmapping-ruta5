# 02. Especificación

La especificación dice qué se construye y por qué, y cómo se sabe que está bien. No dice cómo se programa: eso está en `03-plan.md`.

## Qué y por qué

Un visor web público de la Ruta 5 en la Región Metropolitana (P-01), construido por participantes en un taller. Sirve para aprender webmapping con datos reales y para que el repositorio quede como material educativo reutilizable.

Dentro del territorio de trabajo (P-02: comuna de Colina), el visor responde tres preguntas:

1. ¿Qué cobertura del suelo hay en un punto?
2. ¿Qué altura tiene ese punto?
3. ¿Qué pendiente tiene un área dibujada?

Además muestra la Ruta 5 y las capas de riesgo y contexto que se listan en `06-contrato-datos.md`.

## Historias de usuario

| ID | Como usuario quiero | Para |
|---|---|---|
| HU-01 | Ver la Ruta 5 y las capas de la región sobre un mapa base a elección | Ubicar el contexto |
| HU-02 | Activar, desactivar y cambiar la opacidad de cada capa | Combinar capas a mi criterio |
| HU-03 | Leer la leyenda de cobertura con el nombre de cada clase | Entender qué representa cada color |
| HU-04 | Hacer clic y conocer la clase de cobertura y la altura del punto | Caracterizar un lugar |
| HU-05 | Dibujar un área y conocer su pendiente media y máxima | Evaluar el relieve de un sector |
| HU-06 | Ver emergencias, puentes y remociones con su información | Reconocer elementos de riesgo cerca de la ruta |
| HU-07 | Saber de dónde vienen los datos y bajo qué condiciones | Usarlos con criterio |

## Criterios de aceptación

Cada criterio se comprueba de una forma concreta. Un criterio sin forma de comprobarlo no es un criterio.

| ID | Criterio | Cómo se comprueba | Aplica a |
|---|---|---|---|
| CA-01 | El visor carga sin errores, y tampoco aparecen errores al activar cada capa | Consola del navegador con cero errores | Todos |
| CA-02 | Hay tres mapas base (P-05) conmutables y la atribución visible cambia con cada uno | Inspección visual de los tres mapas base | Todos |
| CA-03 | El panel permite activar, desactivar y ajustar la opacidad de cada capa | Prueba manual capa por capa | Todos |
| CA-04 | Las capas vectoriales tienen estilos centralizados; cada popup muestra los campos definidos y escapa el texto | Revisar los popups con un texto de prueba que contenga etiquetas HTML | Todos |
| CA-05 | La leyenda de cobertura tiene las 16 clases (P-17) con nombre y color iguales a los del proyecto de QGIS, y el clic devuelve la clase correcta | P-09 puntos de control, con tolerancia P-06 (coincidencia exacta) | A |
| CA-06 | El clic sobre el DEM muestra la altura en metros | P-09 puntos de control, con tolerancia P-07 (1 m) | B |
| CA-07 | Un área dibujada muestra la pendiente media y la máxima, en grados | P-10 polígonos de control, con tolerancia P-08 (1 grado, provisional) frente a Estadísticas zonales de QGIS | B |
| CA-08 | Remociones, emergencias y puentes se agrupan y se filtran por un campo a elección | Prueba manual con al menos dos valores de filtro | C |
| CA-09 | Ningún archivo supera P-11 (25 MiB); el contrato de datos está completo; no hay claves, IP ni rutas; las librerías tienen versión fija | Revisar tamaños, buscar los textos prohibidos y leer `06-contrato-datos.md` | Todos |
| CA-10 | El pull request llega con el checklist marcado y solo modifica la carpeta del participante | Revisión del PR por el docente | Todos |

Nota sobre CA-06: el DEM almacena la altura en metros enteros, por lo que la tolerancia es de 1 m y no de decimales.

## Cómo se eligen los puntos y polígonos de control

El participante elige sus propios puntos y polígonos y obtiene el valor correcto en QGIS (P-03). La referencia no se entrega resuelta: obtenerla es parte de la verificación. Reglas de muestreo:

- **Puntos de cobertura (CA-05):** al menos 5 clases distintas entre los P-09 puntos. Evitar puntos sobre el límite entre dos clases, porque el resultado depende de la posición exacta del píxel.
- **Puntos de altura (CA-06):** repartidos en al menos 3 rangos de altura distintos (bajo, medio y alto dentro del territorio).
- **Polígonos de pendiente (CA-07):** P-10 polígonos, cada uno ubicado principalmente en una clase de pendiente distinta de las de P-20 (por ejemplo, plana, media y fuerte), y cada uno de al menos unas decenas de píxeles, porque en áreas muy pequeñas el valor es inestable. Estas reglas de muestreo son una propuesta del proyecto, sin cita.
- Cada punto y polígono se registra en `07-registro-verificacion.md`. El docente repite una muestra propia en la revisión del PR.

## Fuera de alcance

- MapLibre, vectores en teselas, 3D y cualquier servidor propio.
- Consultas a la base de datos PostGIS desde el visor.
- Cálculo de pendiente en el navegador como requisito (es ampliación, ver `03-plan.md`).

## Cómo comprobar que esta especificación está completa

Para cada historia de usuario debe existir al menos un criterio, y para cada criterio una forma de comprobarlo. HU-01 y HU-02 se cubren con CA-01 a CA-03; HU-03 y HU-04 con CA-05 y CA-06; HU-05 con CA-07; HU-06 con CA-04 y CA-08; HU-07 con CA-09.
