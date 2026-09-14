# Día 4 · Actividad 2 — Proyecto Integrador: Pasos 7 y 8 (Repositorio privado, Issue y PR revisado)
**Sesión:** 4 — Trabajo Remoto con GitHub
**Proyecto Integrador:** Pasos 7 y 8 de 10
**Hilo conductor:** Ciberseguridad para Personal de Soporte
**Valor:** 3 de los 8 puntos del entregable del día
## Contexto
`guia-seguridad-soporte` documenta procedimientos internos de seguridad: por eso, a diferencia de `curso-git-github`, este repositorio se sube a GitHub como **privado**. Hoy también se simula el hallazgo de una vulnerabilidad de proceso y su corrección revisada por un tercero, tal como ocurriría en un equipo de seguridad real.
## Instrucciones paso a paso
```bash
cd guia-seguridad-soporte
# Crear el repositorio en GitHub como PRIVADO (vía interfaz web): guia-seguridad-soporte
git remote add origin git@github.com:tu-usuario/guia-seguridad-soporte.git
git push -u origin main
```
En GitHub:
1. Invita a un compañero del curso como colaborador (rol: puede escribir/revisar).
2. Abre un **Issue**: *"El checklist de incidentes no contempla el aviso al área legal"*.
3. Crea la rama `mejora-checklist-legal`, actualiza `checklist-respuesta-incidentes.md` agregando ese paso, y sube la rama.
4. Abre un Pull Request que referencie el Issue; espera al menos un comentario de tu compañero antes de fusionar.
## Entregable esperado
- Repositorio `guia-seguridad-soporte` visible en GitHub, marcado como **privado**.
- Un colaborador agregado.
- Un Issue y un Pull Request revisados y fusionados.
## Ejemplo de entregable
Ejemplo de la actualización del checklist (diff conceptual):
```diff
  - [ ] Contener el incidente.
  - [ ] Notificar al responsable de seguridad.
+ - [ ] Notificar al área legal si hubo datos personales involucrados.
  - [ ] Documentar la línea de tiempo.
  - [ ] Aplicar la corrección.
  - [ ] Revisar lecciones aprendidas.
```
Ejemplo de justificación de por qué el repositorio es privado (para incluir en el README o en la descripción del repo en GitHub):
```markdown
> Este repositorio es privado porque documenta procedimientos internos de
> respuesta a incidentes y contacto con áreas sensibles (legal, seguridad).
> Su versión pública y depurada se publicará hasta el Día 5, mediante
> GitHub Pages, sin datos ni procedimientos internos.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Configuración de privacidad adecuada | El repositorio `guia-seguridad-soporte` está correctamente marcado como privado, justificando por qué. | 2 |
| Entrega en tiempo y forma | Los enlaces se comparten al cierre de la sesión y son accesibles. | 1 |
**Siguiente paso:** Día 5, Actividad 2 — simular un incidente de exposición de credenciales y publicar la guía final con GitHub Pages.

> **Criterios completos:** la escala de puntos de este entregable, la evidencia que se considera válida y el checklist de autoevaluación están en la [Guía de Evaluación del Proyecto Integrador Final](../GUIA-EVALUACION-PROYECTO-INTEGRADOR.md).
