# 08. Gestión del trabajo con Scrum

Este documento explica cómo se organiza el trabajo del taller con Scrum sobre GitHub. Sirve para que el docente lo aplique y para que cada participante sepa qué se espera de él. No reemplaza a la guía de Scrum; la adapta a un sprint muy corto con un agente de IA (Schwaber y Sutherland, 2020).

## Sprint

| Elemento | Valor |
|---|---|
| Duración | 3 días corridos como máximo |
| Sprint 1 | del 19-10-2026 al 21-10-2026 |
| Meta del sprint | Cada participante entrega su variante verificada contra QGIS y aprobada en un pull request |
| Tablero | GitHub Project privado "Ruta 5: Sprint de inducción" (solo para personas invitadas al repositorio) |

Un sprint tan corto exige backlog pequeño: cada tarea de [`04-tareas.md`](04-tareas.md) debe poder terminarse con el agente de IA en una sesión de trabajo.

## Roles

| Rol Scrum | Quién | Responsabilidad |
|---|---|---|
| Product Owner | Docente | Ordena el backlog, define los criterios de [`02-especificacion.md`](02-especificacion.md) y acepta el trabajo |
| Scrum Master | Docente | Cuida el método y quita bloqueos |
| Equipo de desarrollo | Participantes | Cada uno entrega su variante (A, B o C) |

## Artefactos y su lugar en GitHub

| Scrum | En GitHub |
|---|---|
| Product backlog | Issues del repositorio, agregados al Project |
| Historia de usuario | Issue con la plantilla "Historia de usuario" |
| Tarea | Issue con la plantilla "Tarea" (una por cada código de [`04-tareas.md`](04-tareas.md), por ejemplo A1 o B3) |
| Sprint backlog | Vista del Project filtrada por la iteración "Sprint 1" |
| Estimación | Campo `Estimate` (puntos de historia) |
| Estado | Campo `Status`: Todo, In progress, In review, Done |
| Variante | Campo `Variante`: A, B o C, y etiqueta `variante-a`, `variante-b` o `variante-c` |
| Incremento | Pull request integrado en `develop` |
| Release | Integración de `develop` en `master`; milestone `v0.1 Taller` |

## Definición de terminado

La definición de terminado es la de [`04-tareas.md`](04-tareas.md) y la checklist de [`.github/pull_request_template.md`](../.github/pull_request_template.md). Un issue pasa a Done cuando su pull request fue aprobado por el docente y se integró.

## Eventos del sprint

| Evento | Cuándo | Qué se hace |
|---|---|---|
| Planificación | Inicio del día 1 | El docente presenta la meta; cada participante toma las tareas de su variante y las mueve a In progress de a una (R-12) |
| Seguimiento diario | Inicio de cada día | Cada participante responde: qué terminó, qué hará hoy, qué lo bloquea. Máximo 5 minutos por persona |
| Revisión | Último día | Cada participante muestra su variante funcionando y su registro de verificación ([`07-registro-verificacion.md`](07-registro-verificacion.md)) |
| Retrospectiva | Cierre del último día | Qué funcionó, qué no y qué se cambia, en especial al trabajar con la IA |

## Flujo de un issue

1. El docente crea el issue con la plantilla correspondiente y lo deja en Todo.
2. La persona asignada crea su rama desde `develop` (P-13) y mueve el issue a In progress.
3. Trabaja la tarea con el bucle de [`05-bucle-verificacion.md`](05-bucle-verificacion.md) y anota la evidencia en el registro.
4. Abre el pull request hacia `develop`, escribe `Closes #<número>` en la descripción y el issue pasa a In review.
5. El docente revisa. Si aprueba y se integra, el issue pasa a Done.

## Etiquetas

| Etiqueta | Uso |
|---|---|
| `historia` | Historia de usuario |
| `tarea` | Tarea de [`04-tareas.md`](04-tareas.md) |
| `bug` | Defecto encontrado |
| `documentación` | Cambio en `docs/` |
| `variante-a`, `variante-b`, `variante-c` | Variante a la que pertenece el trabajo |

## Fuentes

- Schwaber, K. y Sutherland, J. (2020). The Scrum Guide. https://scrumguides.org/scrum-guide.html
- GitHub Docs. Planning and tracking with Projects. https://docs.github.com/en/issues/planning-and-tracking-with-projects
