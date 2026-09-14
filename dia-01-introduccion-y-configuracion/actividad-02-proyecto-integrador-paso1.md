# Día 1 · Actividad 2 — Proyecto Integrador: Paso 1 (Identidad del repositorio)
**Sesión:** 1 — Introducción y Configuración
**Proyecto Integrador:** Paso 1 de 10
**Hilo conductor:** Ciberseguridad para Personal de Soporte
**Valor:** 3 de los 8 puntos del entregable del día
## Contexto
A partir de hoy se construye, sesión tras sesión, el repositorio `guia-seguridad-soporte`: una guía de buenas prácticas de ciberseguridad para personal de soporte, documentada y versionada con Git exactamente como se haría en un equipo de trabajo real. El primer paso es de identidad: en seguridad de la información, que cada cambio quede asociado de forma verificable a quien lo hizo no es un detalle menor — es la base de la trazabilidad y la rendición de cuentas.
## Instrucciones paso a paso
```bash
# Crear la carpeta del proyecto integrador
mkdir guia-seguridad-soporte && cd guia-seguridad-soporte
git init
# Declarar una identidad LOCAL para este proyecto
# (puede ser la misma que tu identidad global, pero debe quedar explícita)
git config user.name "Tu Nombre"
git config user.email "tu_correo@ejemplo.com"
# Verificar que la configuración local es la que se usará
git config --list --local
```
## Entregable esperado
- Carpeta `guia-seguridad-soporte` inicializada como repositorio Git.
- Configuración local declarada explícitamente (visible con `git config --list --local`).
- Una breve nota (puede ir al inicio del futuro README) explicando por qué, en un proyecto de ciberseguridad, es importante que la autoría de cada commit sea verificable.
## Ejemplo de entregable
Salida esperada de `git config --list --local`:
```
user.name=Ana Torres
user.email=ana.torres@ejemplo.com
```
Ejemplo de nota de justificación:
```markdown
> Este repositorio declara una identidad local propia porque documenta
> procedimientos de seguridad internos. En caso de una auditoría o de un
> incidente, cada cambio a una política debe poder atribuirse sin ambigüedad
> a la persona que lo propuso o aprobó — el mismo principio de no repudio
> que se revisó en el curso de Ciberseguridad para Personal de Soporte.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Configuración local del proyecto integrador | El repositorio `guia-seguridad-soporte` existe y declara una identidad local propia, distinta o igual a la global pero explícita. | 2 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con las capturas legibles y completas. | 1 |
**Siguiente paso:** Día 2, Actividad 2 — construir la estructura inicial del repositorio (README, `.gitignore` y las tres políticas de seguridad).

> **Criterios completos:** la escala de puntos de este entregable, la evidencia que se considera válida y el checklist de autoevaluación están en la [Guía de Evaluación del Proyecto Integrador Final](../GUIA-EVALUACION-PROYECTO-INTEGRADOR.md).
