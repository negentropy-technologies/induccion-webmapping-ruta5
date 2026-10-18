# Paquete SDD: visor web de la Ruta 5 en la Región Metropolitana

Este directorio contiene el método de trabajo del proyecto bajo Spec-Driven Development (SDD): primero se especifica, luego se planifica, después se divide en tareas, y cada tarea se implementa y se verifica contra un criterio medible. Está escrito para dos usos:

1. **Aplicarlo en este taller.** Cada participante lo lee, lo sigue y lo cita a la IA.
2. **Reutilizarlo en otros proyectos del mismo tipo** (ver "Cuándo sirve este paquete").

## Qué es SDD, en una línea

La especificación es la fuente de verdad; el código es su resultado y se comprueba contra ella. El flujo de GitHub Spec Kit tiene las etapas constitución, especificación, plan, tareas e implementación, y una verificación que se repite hasta que el resultado converge con la especificación (GitHub, Spec Kit).

## Orden de lectura

| Orden | Archivo | Para qué sirve | Quién lo edita |
|---|---|---|---|
| 0 | `00-parametros.md` | Todos los valores propios del proyecto, con un identificador (P-01, P-02...) | Docente |
| 1 | `01-constitucion.md` | Reglas que no se negocian | Docente |
| 2 | `02-especificacion.md` | Qué se construye, para quién y cómo se sabe que está bien | Docente |
| 3 | `03-plan.md` | Cómo se construye: tecnología, estructura y decisiones | Docente |
| 4 | `04-tareas.md` | Tareas pequeñas, cada una con su criterio y su evidencia | Docente |
| 5 | `05-bucle-verificacion.md` | El ciclo de trabajo con la IA y las plantillas de instrucciones | Docente |
| 6 | `06-contrato-datos.md` | Qué datos hay, de dónde vienen y cuáles se publican | Docente |
| 7 | `07-registro-verificacion.md` | Plantilla donde cada participante anota sus comprobaciones | Participante |
| 8 | `08-gestion-scrum.md` | Cómo se organiza el sprint con Scrum en GitHub Projects | Docente |

## Cómo se usa en el taller

1. Lea `00` a `06` completos. Son cortos.
2. Busque su variante en `04-tareas.md` (sección "Mi variante").
3. Trabaje una tarea a la vez con el bucle de `05-bucle-verificacion.md`.
4. Anote cada comprobación en su copia de `07-registro-verificacion.md`, dentro de su carpeta.
5. Abra el pull request con la plantilla de `.github/pull_request_template.md`.

## Cuándo sirve este paquete

Sirve, cambiando solo los parámetros y el contrato de datos, para proyectos con estas características:

- Sitio web **estático**, sin servidor propio ni base de datos propia (por ejemplo, publicado en GitHub Pages).
- Datos geoespaciales **precargados** en el repositorio (GeoJSON y GeoTIFF).
- Una **referencia de verificación externa** que da el valor correcto (aquí, QGIS).
- Trabajo **individual por rama** y revisión por pull request.

Si el proyecto necesita servidor propio, base de datos, autenticación o servicios con clave, hay que ampliar la constitución (`01`) y el plan (`03`) antes de reutilizarlo.

## Cómo reutilizarlo en otro proyecto

1. Copie el directorio `docs/` y la plantilla de PR al repositorio nuevo.
2. Edite `00-parametros.md`: cambie los valores de cada parámetro.
3. Busque en todo el directorio cada identificador `P-xx` y actualice el valor entre paréntesis que lo acompaña.
4. Reescriba `06-contrato-datos.md` con las capas del proyecto nuevo.
5. Revise las historias de usuario y los criterios de `02-especificacion.md`; conserve su formato (cada criterio con su forma de comprobarlo).
6. Ajuste las variantes de `04-tareas.md` a los módulos del proyecto nuevo.
7. Pida a una persona que no conoce el proyecto que lea `00` a `06` y diga qué no entiende.

## Fuentes

- GitHub (2025). Spec Kit. https://github.com/github/spec-kit
- GitHub Blog (2 de septiembre de 2025). Spec-driven development with AI: Get started with a new open source toolkit. https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/
