# 01. Constitución del proyecto

Reglas que no se negocian dentro del taller. La IA debe leerlas completas antes de cada tarea. Si una regla impide cumplir un criterio, se consulta al docente; la IA no la modifica ni la omite.

## Reglas

**R-01. Tecnología fija.** Solo se usan las librerías de la tabla P-19 de `00-parametros.md`, en sus versiones exactas. No se agregan librerías sin aprobación del docente.

**R-02. Sitio estático.** El sitio no tiene servidor propio ni compilación. Se abre con un servidor local simple de archivos. No hay llamadas a interfaces propias ni a servicios que exijan clave.

**R-03. Versiones fijas.** Las librerías se cargan con versión exacta o se copian al repositorio. Nunca "latest".

**R-04. Datos solo desde el repositorio.** Ninguna capa se descarga en tiempo de ejecución desde otra fuente. La única excepción son los mapas base (P-05).

**R-05. Seguridad.** Ningún archivo contiene claves, contraseñas, direcciones IP, usuarios ni rutas de servidores. Todo texto que provenga de los datos se escapa antes de mostrarse en un popup, para evitar la inyección de HTML.

**R-06. Atribución y licencia.** Cada mapa base muestra su atribución. Cada capa de datos declara fuente, fecha y licencia en `06-contrato-datos.md`. Si la fuente no declara licencia, la capa se rotula como "licencia no declarada".

**R-07. Tamaño de archivos.** Ningún archivo supera P-11 (25 MiB).

**R-08. Alcance de edición.** Cada participante edita solo su carpeta (P-14). El núcleo común y los datos los modifica el docente.

**R-09. Verificación primero.** Una tarea no está terminada hasta que su criterio se cumple y queda evidencia registrada en `07-registro-verificacion.md`.

**R-10. La referencia manda.** Cuando el visor y la referencia (P-03) difieren sobre el mismo dato, se investiga hasta explicar la diferencia. No se ajusta el visor para "calzar" con un caso aislado.

**R-11. La IA no cambia los criterios.** Si un criterio parece incorrecto, se plantea al docente. No se reescribe para que el resultado lo cumpla.

**R-12. Una tarea a la vez.** Se implementa una tarea, se verifica y recién entonces se pasa a la siguiente.

## Por qué existe una constitución

En el flujo de Spec Kit, la constitución es la etapa que fija los principios del proyecto, una vez por proyecto (GitHub, Spec Kit). Aquí cumple ese papel: es lo primero que la IA lee, y es el docente, no la IA, quien puede modificarla.
