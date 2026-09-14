# Guía de Evaluación — Proyecto Integrador Final

**Curso Git y GitHub** · REDEC-UNAM Cuautitlán / Educación Continua FESC
7 al 11 de septiembre de 2026 · 09:00 a 11:00 y 11:15 a 13:00 hrs.
Repositorio del proyecto: `guia-seguridad-soporte`

> **Documento para el participante.** Reúne en un solo lugar todo lo que se evalúa del Proyecto Integrador Final: qué se entrega cada sesión, con qué criterios se califica, cuántos puntos vale cada criterio y qué evidencia se considera válida. Los criterios y los puntajes son exactamente los del manual del curso y los de las *Actividad 2* de este repositorio; aquí solo se resumen y se ordenan como guía de trabajo y de autoevaluación. **En caso de discrepancia, prevalece el manual.**

---

## 1. Qué es el Proyecto Integrador Final

Es la construcción incremental —sesión tras sesión— de un repositorio real llamado `guia-seguridad-soporte`: una guía de buenas prácticas de ciberseguridad para personal de soporte, documentada, versionada, revisada y publicada con Git y GitHub exactamente como se haría en un equipo de trabajo.

Se desarrolla en **10 pasos acumulativos** repartidos en las cinco sesiones. Cada paso corresponde a la **Actividad 2** del día en este repositorio. El hilo conductor es el curso de *Ciberseguridad para Personal de Soporte*, de modo que el proyecto integra ambas formaciones: el **qué** (las políticas de seguridad) y el **cómo** (el control de versiones que las mantiene vivas y trazables).

Dos consecuencias prácticas de que el proyecto sea acumulativo:

- No se puede "recuperar" una sesión sin el trabajo de la anterior: el paso de cada día parte del estado en que quedó el repositorio el día previo.
- Lo que se califica no es solo el resultado final, sino el **historial**: mensajes de commit, ramas, resolución de conflictos y decisiones documentadas son parte de la evidencia.

## 2. Dónde entra el Proyecto Integrador en la calificación

Escala 0 a 10, **mínima aprobatoria 8.00**.

| Rubro | Descripción | Puntos |
|---|---|---|
| Asistencia | Asistencia y permanencia en las cinco sesiones. | 40 |
| Actividades de aprendizaje | Un entregable por sesión, de 8 puntos: Actividad 1 (ejercicio del tema) + Actividad 2 (paso del Proyecto Integrador). | 40 |
| Evaluación final | Evaluación de cierre del curso. | 20 |
| **Total** | | **100** |

De los 40 puntos de actividades, **15 corresponden al Proyecto Integrador** (3 + 3 + 2 + 3 + 4) y 25 a las Actividades 1. El Proyecto Integrador vale el **15 % de la calificación final** y **no se entrega al final**, sino por partes, al cierre de cada sesión.

## 3. Mapa general: los 10 pasos y su valor

| Sesión | Pasos | Entregable del Proyecto Integrador | Pts. PI | Pts. del día |
|---|:---:|---|:---:|:---:|
| Día 1 | 1 | Identidad del repositorio: `guia-seguridad-soporte` inicializado con identidad local explícita y nota que justifica la trazabilidad de la autoría. | 3 | 8 |
| Día 2 | 2–4 | Estructura inicial: `README` con los cinco temas, `.gitignore` propio del proyecto y las tres políticas de seguridad, cada una en su propio commit. | 3 | 8 |
| Día 3 | 5–6 | Política de MFA fusionada en `main` y conflicto real provocado y resuelto en el protocolo de reporte de phishing, con la decisión documentada en el commit de fusión. | 2 | 8 |
| Día 4 | 7–8 | Repositorio publicado en GitHub como **privado**, con un colaborador invitado, y un Issue y un Pull Request reales, revisados y fusionados. | 3 | 8 |
| Día 5 | 9–10 | Incidente simulado de exposición de credenciales documentado, publicación final con GitHub Pages y reflexión de cierre que conecta ambos cursos. | 4 | 8 |
| **Totales** | **10** | | **15** | **40** |

---

## 4. Rúbrica detallada, sesión por sesión

En cada sesión el entregable del día vale 8 puntos: una parte es la Actividad 1 y otra el Proyecto Integrador. Abajo se detalla la parte del Proyecto Integrador y se indica cómo se completan los 8 puntos.

### Día 1 · Paso 1 — Identidad del repositorio (3 puntos)

**Qué se entrega**

- Carpeta `guia-seguridad-soporte` inicializada como repositorio Git.
- Configuración local declarada explícitamente, verificable con `git config --list --local`.
- Nota breve (puede ir al inicio del futuro README) explicando por qué, en un proyecto de ciberseguridad, la autoría de cada commit debe ser verificable.

| Criterio | Qué debe demostrar la evidencia | Puntos |
|---|---|:---:|
| Configuración local del proyecto integrador | El repositorio existe y declara una identidad local propia —igual o distinta a la global, pero explícita— y la nota justifica la trazabilidad en términos de seguridad (no repudio), no en términos genéricos. | 2 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con capturas legibles y completas. | 1 |
| **Total del Proyecto Integrador en esta sesión** | | **3** |

*Los 5 puntos restantes del día: instalación y configuración funcional de Git (3) y explicación de los tres estados con un ejemplo propio (2).*

### Día 2 · Pasos 2 a 4 — Estructura, `.gitignore` y políticas (3 puntos)

**Qué se entrega**

- `README.md` con los cinco temas de seguridad listados.
- `.gitignore` propio del proyecto, distinto al del repositorio de práctica del día.
- Los tres documentos de `/politicas` —política de contraseñas, protocolo de reporte de phishing y checklist de respuesta a incidentes—, **cada uno en su propio commit**.

| Criterio | Qué debe demostrar la evidencia | Puntos |
|---|---|:---:|
| Avance del Proyecto Integrador | Los tres documentos existen como commits separados —no en un solo commit— y su contenido es coherente con el curso de Ciberseguridad para Personal de Soporte. | 2 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con el historial visible y legible. | 1 |
| **Total del Proyecto Integrador en esta sesión** | | **3** |

*Los 5 puntos restantes del día: atomicidad y calidad de los commits (3) y `.gitignore` aplicado y justificado (2).*

### Día 3 · Pasos 5 y 6 — Política de MFA y conflicto resuelto (2 puntos)

**Qué se entrega**

- Política de MFA creada en su propia rama y fusionada en `main`.
- Conflicto real provocado y resuelto en `protocolo-reporte-phishing.md`, con el commit de fusión explicando la decisión tomada.

| Criterio | Qué debe demostrar la evidencia | Puntos |
|---|---|:---:|
| Avance del Proyecto Integrador | La política de MFA y el protocolo de phishing reflejan el conflicto resuelto de forma coherente con el resto de la guía; el mensaje del commit de resolución explica el **porqué** de la decisión, no solo qué se cambió. | 1 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con evidencia clara del antes y el después del conflicto. | 1 |
| **Total del Proyecto Integrador en esta sesión** | | **2** |

*Los 6 puntos restantes del día: manejo de ramas y fusiones con ambos tipos identificados en el historial (3) y resolución de conflictos sin pérdida de información (3).*

### Día 4 · Pasos 7 y 8 — Repositorio privado, Issue y Pull Request (3 puntos)

**Qué se entrega**

- Repositorio `guia-seguridad-soporte` en GitHub marcado como **privado**, con la justificación de por qué lo es.
- Un colaborador del curso agregado con permisos de escritura/revisión.
- Un Issue y un Pull Request reales, con al menos un comentario de revisión **antes** de fusionar.

| Criterio | Qué debe demostrar la evidencia | Puntos |
|---|---|:---:|
| Configuración de privacidad adecuada | El repositorio está correctamente marcado como privado y se justifica por qué: documenta procedimientos internos de respuesta a incidentes y contacto con áreas sensibles. | 2 |
| Entrega en tiempo y forma | Los enlaces se comparten al cierre de la sesión y son accesibles para quien debe revisarlos. | 1 |
| **Total del Proyecto Integrador en esta sesión** | | **3** |

*Los 5 puntos restantes del día: autenticación y conexión remota funcional (2) y ciclo de colaboración completo con Issue y PR revisados (3).*

### Día 5 · Pasos 9 y 10 — Incidente simulado y publicación final (4 puntos)

**Qué se entrega**

- Documentación por escrito del incidente simulado de exposición de credenciales y de por qué eliminar el archivo o hacer `revert` no resuelve la fuga.
- URL pública del sitio publicado con GitHub Pages, sin datos ni procedimientos internos sensibles.
- Reflexión final de 5 a 8 líneas que conecte este curso con el de Ciberseguridad para Personal de Soporte.

| Criterio | Qué debe demostrar la evidencia | Puntos |
|---|---|:---:|
| Comprensión del incidente de seguridad simulado | La explicación distingue correctamente entre "borrar del historial" y "la credencial ya fue expuesta y debe rotarse": la única respuesta correcta ante una fuga real es invalidar y reemplazar la credencial, tratándola como comprometida desde el momento en que se subió. | 3 |
| Reflexión de cierre | La reflexión conecta explícitamente contenidos de ambos cursos; no es genérica ni intercambiable con la de cualquier otro participante. | 1 |
| **Total del Proyecto Integrador en esta sesión** | | **4** |

*Los 4 puntos restantes del día: uso correcto y diferenciado de `restore`, `reset` y `revert` (2) y publicación del sitio accesible y sin datos sensibles (2, evaluada junto con la Actividad 2).*

---

## 5. Criterios transversales: qué cuenta como evidencia válida

El criterio **"entrega en tiempo y forma"** aparece en cuatro de las cinco sesiones y vale 1 punto cada vez (4 de los 15 puntos del proyecto). Se cumple cuando:

- La entrega se presenta **al cierre de la sesión correspondiente**, no después.
- Las capturas son legibles y completas: se ve el comando ejecutado y su salida, no un recorte parcial. Cuando se pida el historial, debe mostrarse `git log --oneline --graph` o equivalente.
- Los enlaces compartidos (repositorio, Issue, Pull Request, sitio de GitHub Pages) abren correctamente para quien los revisa.
- Los textos solicitados —nota de justificación, mensaje del commit de resolución, documentación del incidente y reflexión— están escritos por el participante y son específicos de su proyecto.

> **Sobre el contenido del repositorio:** todas las credenciales usadas en el proyecto son de práctica. Nunca se sube al repositorio una contraseña, token o dato real de la organización, ni siquiera para simular el incidente del Día 5.

## 6. Checklist de autoevaluación antes de entregar

**Día 1**
- [ ] `git config --list --local` muestra `user.name` y `user.email` del proyecto.
- [ ] La nota explica la trazabilidad en términos de seguridad, no como un trámite.

**Día 2**
- [ ] El README lista los cinco temas de seguridad.
- [ ] El `.gitignore` es del proyecto y excluye lo que realmente no debe versionarse.
- [ ] `git log --oneline` muestra un commit por cada política, con mensajes descriptivos.

**Día 3**
- [ ] La rama de MFA quedó fusionada en `main` y el historial lo refleja.
- [ ] El conflicto existió de verdad y el commit de resolución explica la decisión.

**Día 4**
- [ ] El repositorio en GitHub dice *Private* y la descripción o el README dice por qué.
- [ ] Hay un colaborador agregado, un Issue abierto y un PR con comentario de revisión antes de fusionar.

**Día 5**
- [ ] La documentación del incidente menciona explícitamente la **rotación** de la credencial.
- [ ] El sitio de GitHub Pages abre y no contiene información interna.
- [ ] La reflexión menciona contenidos concretos de los dos cursos.

## 7. Errores frecuentes que restan puntos

- Agrupar en un solo commit lo que la instrucción pide en commits separados (Día 2).
- Mensajes de commit genéricos tipo "cambios" o "update": el mensaje es parte de la evidencia calificada.
- Resolver el conflicto borrando una de las dos versiones sin explicar el criterio.
- Dejar público el repositorio del Día 4: la privacidad es un criterio explícito de 2 puntos.
- Fusionar el Pull Request sin esperar el comentario de revisión de otra persona.
- Explicar el incidente del Día 5 diciendo que el archivo "ya se borró": eliminarlo en un commit nuevo no lo quita del historial, y ese es justamente el punto que se evalúa.
- Entregar una reflexión final genérica, que podría haber escrito cualquier persona sin haber tomado los dos cursos.
- Capturas cortadas, ilegibles o que no muestran el comando ejecutado.

## 8. Referencias

- **Repositorio de apoyo del curso:** <https://github.com/atapia9/CursoGitHub> — una carpeta por día, con la Actividad 1 (ejercicio del tema) y la Actividad 2 (paso del Proyecto Integrador), incluyendo instrucciones paso a paso, ejemplo de entregable y la rúbrica aplicable.
- **Manual del Curso Git y GitHub** (versión con Proyecto Integrador, Entregables y Rúbricas, Glosario y Referencias): teoría completa, ejercicios de cada sesión y rúbricas oficiales.
- **Curso de Ciberseguridad para Personal de Soporte:** fuente de los contenidos de seguridad que el proyecto documenta y versiona.
