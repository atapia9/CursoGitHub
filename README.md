# Curso Git y GitHub — REDEC UNAM Cuautitlán / Educación Continua FESC

Repositorio de apoyo del curso presencial **Git y GitHub**, impartido del **7 al 11 de septiembre de 2026** (09:00 a 11:00 y 11:15 a 13:00 hrs.).

Este repositorio no sustituye al manual del curso: es el espacio donde se documentan, con ejemplos concretos, los **entregables de cada sesión** y el avance del **Proyecto Integrador Final** (hilo conductor: *Ciberseguridad para Personal de Soporte*), para que cada participante sepa exactamente qué entregar, cómo se ve un entregable correctamente resuelto y sobre qué criterios se le califica.

## Evaluación

- **[Guía de Evaluación del Proyecto Integrador Final](./GUIA-EVALUACION-PROYECTO-INTEGRADOR.md)** — documento único que resume, día por día, los entregables, los criterios, los puntos, la evidencia válida, el checklist de autoevaluación y los errores que restan puntos. **Empieza por aquí.**
- [Versión imprimible en Word](./Guia_Evaluacion_Proyecto_Integrador_Git_GitHub.docx) del mismo documento.

Peso de cada rubro en la calificación final (escala 0 a 10, **mínima aprobatoria 8.00**):

| Rubro | Puntos |
|---|:---:|
| Asistencia | 40 |
| Actividades de aprendizaje (8 por sesión: Actividad 1 + Actividad 2) | 40 |
| Evaluación final | 20 |
| **Total** | **100** |

De los 40 puntos de actividades, **15 corresponden al Proyecto Integrador** (3 + 3 + 2 + 3 + 4) y 25 a las Actividades 1.

## Estructura

| Carpeta | Sesión del manual | Actividad 1 | Actividad 2 |
|---|---|---|---|
| [`dia-01-introduccion-y-configuracion/`](./dia-01-introduccion-y-configuracion) | Sesión 1 — Introducción y Configuración | Configuración verificable de Git | Proyecto Integrador — Paso 1 |
| [`dia-02-ciclo-de-vida-de-archivos-y-commits/`](./dia-02-ciclo-de-vida-de-archivos-y-commits) | Sesión 2 — Ciclo de Vida de los Archivos y Commits | Commits atómicos y `.gitignore` | Proyecto Integrador — Pasos 2 a 4 |
| [`dia-03-ramas-branching-y-fusion-merging/`](./dia-03-ramas-branching-y-fusion-merging) | Sesión 3 — Ramas (Branching) y Fusión (Merging) | Fusiones y resolución de conflictos | Proyecto Integrador — Pasos 5 y 6 |
| [`dia-04-trabajo-remoto-con-github/`](./dia-04-trabajo-remoto-con-github) | Sesión 4 — Trabajo Remoto con GitHub | Repositorio remoto y colaboración (Issue + PR) | Proyecto Integrador — Pasos 7 y 8 |
| [`dia-05-flujos-de-trabajo-y-buenas-practicas/`](./dia-05-flujos-de-trabajo-y-buenas-practicas) | Sesión 5 — Flujos de Trabajo y Buenas Prácticas | Deshacer cambios, stash y GitHub Pages | Proyecto Integrador — Pasos 9 y 10 |

## Cómo usar cada actividad

Cada archivo `actividad-0X-*.md` incluye:

1. **Objetivo** — qué se busca demostrar con la actividad.
2. **Instrucciones paso a paso** — los comandos a ejecutar, en orden.
3. **Entregable esperado** — el formato exacto que se revisa en sesión.
4. **Ejemplo de entregable** — una muestra concreta (salida de comandos, contenido de archivos, mensajes de commit) que ilustra cómo debería verse un entregable correctamente resuelto.
5. **Rúbrica aplicable** — los mismos criterios y puntos del manual, para que el participante sepa exactamente sobre qué se le califica.

## Proyecto Integrador Final

Las "Actividad 2" de cada día son, en conjunto, los 10 pasos del Proyecto Integrador Final: la construcción incremental del repositorio `guia-seguridad-soporte`, una guía de buenas prácticas de ciberseguridad para personal de soporte, documentada, versionada, revisada y publicada exactamente como se haría en un equipo de trabajo real.

| Sesión | Pasos | Entregable |
|---|:---:|---|
| Día 1 | 1 | Identidad del repositorio: `guia-seguridad-soporte` inicializado con identidad local explícita. |
| Día 2 | 2–4 | `README`, `.gitignore` propio y las tres políticas de seguridad, cada una en su propio commit. |
| Día 3 | 5–6 | Política de MFA fusionada en `main` y conflicto real resuelto en el protocolo de phishing. |
| Día 4 | 7–8 | Repositorio privado en GitHub, con Issue y Pull Request revisados y fusionados. |
| Día 5 | 9–10 | Incidente simulado de credenciales documentado, publicación con GitHub Pages y reflexión de cierre. |

Como el proyecto es acumulativo, el paso de cada día parte del estado en que quedó el repositorio el día anterior: lo que se califica no es solo el resultado final, sino el historial.

## Referencia

Toda la teoría, los ejercicios completos de cada sesión y las rúbricas oficiales están en el **Manual del Curso Git y GitHub** (versión con Proyecto Integrador, Entregables y Rúbricas, Glosario y Referencias). En caso de discrepancia entre este repositorio y el manual, prevalece el manual.
