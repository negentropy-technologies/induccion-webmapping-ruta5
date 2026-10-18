# Guía de contribución

## Ramas

| Rama | Función |
|---|---|
| `master` | Rama por defecto. Publica el sitio en GitHub Pages |
| `develop` | Integración |
| `<nombre>` | Rama individual de cada participante, creada desde `develop` |

No se hace push directo a `master` ni a `develop`; los cambios entran por pull request.

## Pasos

1. Clonar el repositorio.
2. Crear su rama desde `develop` con su nombre.
3. Trabajar solo en `participantes/<nombre>/` (R-08, ver [`docs/01-constitucion.md`](docs/01-constitucion.md)).
4. Verificar cada resultado contra QGIS y registrarlo en [`docs/07-registro-verificacion.md`](docs/07-registro-verificacion.md).
5. Abrir un pull request hacia `develop` con el checklist de la plantilla completo.

## Commits

- Mensaje en español, en una línea clara y en modo imperativo (por ejemplo, "Agrega capa de puentes").
- Sin claves, direcciones IP ni rutas locales en ningún archivo (R-05).
- Archivos de menos de 25 MiB.

## Especificación

La especificación en [`docs/`](docs/) es la fuente de verdad. Si el código y la especificación difieren, se corrige primero la especificación.
