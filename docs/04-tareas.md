# 04. Tareas

Cada tarea es pequeña, se implementa de una vez y tiene un criterio y una evidencia. Se hacen en orden y una a la vez (R-12). Las tareas de preparación del docente no están aquí; el núcleo común (mapa, mapas base, panel de capas, estilos y popups base) ya viene construido en `site/`.

## Cómo es una tarea

Cada tarea indica: **objetivo**, **criterio** (de `02-especificacion.md`), **verificación** y **evidencia** que se anota en `07-registro-verificacion.md`.

## Tarea común: preparar el entorno (todos)

- **Objetivo:** tener el proyecto funcionando en su computador.
- **Pasos:** clonar el repositorio; crear su rama desde `develop` con su nombre (P-13); crear su carpeta (P-14); abrir el sitio con un servidor local simple.
- **Criterio:** CA-01 sobre el núcleo común sin modificar.
- **Evidencia:** captura de la consola sin errores.

## Mi variante

Cada participante trabaja una variante (P-15). Las tres usan el núcleo común y no se pisan entre sí.

### Variante A: cobertura

| Tarea | Objetivo | Criterio | Verificación | Evidencia |
|---|---|---|---|---|
| A1 | Mostrar el ráster de cobertura con la paleta de las 16 clases | CA-05 (parte visual) | Comparar los colores con el proyecto de QGIS | Captura del visor y de QGIS lado a lado |
| A2 | Construir la leyenda con nombre y color de cada clase | CA-05 (leyenda) | Comparar nombre y color de las 16 clases con la tabla de `06-contrato-datos.md` | Tabla de comparación |
| A3 | Al hacer clic, mostrar código y nombre de la clase | CA-05 (clic) | P-09 puntos de control contra Identificar de QGIS | Tabla de puntos en el registro |

### Variante B: relieve

| Tarea | Objetivo | Criterio | Verificación | Evidencia |
|---|---|---|---|---|
| B1 | Mostrar el DEM con una paleta continua | CA-01 | Consola sin errores y relieve reconocible | Captura |
| B2 | Al hacer clic, mostrar la altura (reproyectar el clic al sistema P-04) | CA-06 | P-09 puntos de control contra QGIS, tolerancia P-07 | Tabla de puntos en el registro |
| B3 | Dibujar un área y mostrar pendiente media y máxima | CA-07 | P-10 polígonos contra Estadísticas zonales de QGIS, tolerancia P-08 | Tabla de polígonos en el registro |
| B4 (ampliación) | Calcular la pendiente en el navegador (Camino B de `03-plan.md`) y compararla con QGIS | CA-07 | Mismos polígonos | Tabla comparativa |

### Variante C: riesgo

| Tarea | Objetivo | Criterio | Verificación | Evidencia |
|---|---|---|---|---|
| C1 | Mostrar remociones, emergencias y puentes con estilos propios | CA-04 | Inspección visual | Captura |
| C2 | Definir los campos de cada popup y escapar el texto | CA-04 | Probar con un texto que contenga etiquetas HTML | Captura del popup con el texto escapado |
| C3 | Agrupar los puntos y agregar un filtro por campo | CA-08 | Probar al menos dos valores de filtro | Captura antes y después del filtro |

## Tarea final común: cerrar el PR (todos)

- **Objetivo:** entregar el trabajo para revisión.
- **Criterio:** CA-09 y CA-10.
- **Evidencia:** checklist del PR marcado, registro de verificación completo y captura de la consola sin errores.

## Definición de terminado

Una variante está terminada cuando se cumplen los criterios comunes (CA-01 a CA-04, CA-09 y CA-10) y todos los de su variante, con la evidencia registrada. El docente aprueba el PR; sin esa aprobación no pasa a `develop`.
