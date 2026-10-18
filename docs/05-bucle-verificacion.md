# 05. Bucle de verificación

Es el ciclo que se repite en cada tarea. Su objetivo es que ninguna tarea se dé por terminada porque la IA lo diga, sino porque su criterio se cumple y hay evidencia.

## El bucle

1. **Leer.** Lea la tarea (`04-tareas.md`), su criterio (`02-especificacion.md`) y la constitución (`01-constitucion.md`).
2. **Planificar.** Pida a la IA el plan de la tarea, no el código. Si la tarea trabaja con datos o con cálculos, el docente valida el plan antes de seguir.
3. **Implementar.** La IA construye solo esa tarea (R-12).
4. **Verificar.** Haga las tres verificaciones de la sección siguiente y anote el resultado en `07-registro-verificacion.md`.
5. **Decidir.**
   - Si el criterio se cumple: haga un commit que cite la tarea y pase a la siguiente.
   - Si no se cumple: pida la corrección citando textualmente el criterio que falló y los valores obtenidos, y vuelva al paso 3.
6. **Escalar.** Tras P-12 intentos (3) fallidos sobre el mismo criterio, consulte al docente. Insistir sin cambiar de enfoque rara vez funciona. El límite es una propuesta práctica, sin sustento bibliográfico.

## Tres niveles de verificación

| Nivel | Qué verifica | Quién |
|---|---|---|
| 1. Comprobaciones básicas | Consola sin errores; tamaño de los archivos (R-07); búsqueda de claves, IP y rutas (R-05); versiones fijas de las librerías (R-03) | El participante |
| 2. Contra la referencia | Clase, altura y pendiente en los puntos y polígonos de control, comparados con QGIS (P-03) | El participante |
| 3. Revisión del PR | Checklist, alcance de los cambios, contrato de datos y evidencia | El docente |

Una prueba automática con navegador sin interfaz puede cubrir CA-01 y parte de CA-02. Se agrega solo si el docente la valida.

## Reglas del bucle

- No pegue claves, contraseñas ni datos privados en una instrucción a la IA.
- La IA no cambia los criterios de éxito (R-11).
- Todo resultado numérico se compara con la referencia, nunca con la intuición ni con lo que la IA afirma.
- Si la IA propone agregar una librería, rechácela y consulte al docente (R-01).

## Plantillas de instrucciones

Reemplace lo que está entre corchetes.

**Para planificar (paso 2)**

> Lee los archivos `docs/00-parametros.md`, `docs/01-constitucion.md`, `docs/02-especificacion.md` y `docs/03-plan.md`. Mi tarea es [código y nombre de la tarea] y su criterio es [ID del criterio y texto]. No escribas código todavía. Entrégame un plan en pasos pequeños, indica qué archivos de mi carpeta tocarías y cómo comprobaría el criterio. No agregues librerías.

**Para implementar (paso 3)**

> Implementa solo el paso [número] del plan que aprobé. No modifiques archivos fuera de `participantes/[mi-carpeta]/`. Al terminar, resume qué cambiaste y cómo puedo comprobar el criterio [ID].

**Para corregir (paso 5)**

> El criterio [ID] dice: "[texto exacto]". Obtuve [valor del visor] y QGIS entrega [valor de QGIS] en [punto o polígono]. Explica por qué puede diferir y propón la corrección más pequeña. No cambies el criterio ni la tolerancia.

**Para cerrar la tarea**

> Revisa los archivos que cambié y dime si alguno contiene claves, direcciones IP, rutas de servidores o texto de los datos sin escapar en un popup.

## Por qué funciona

El bucle repite el ciclo de implementación y verificación hasta que el resultado converge con la especificación, que es el mismo principio del flujo de Spec Kit (GitHub, Spec Kit). La comparación con una referencia independiente es lo que hace objetiva la verificación; en pruebas de software, lo obtenido se compara con lo esperado (MDN, "Introduction to automated testing").

## Fuentes

- GitHub (2025). Spec Kit. https://github.com/github/spec-kit
- MDN Web Docs. Introduction to automated testing. https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Testing/Automated_testing
