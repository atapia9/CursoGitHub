# Día 5 · Actividad 1 — Deshacer cambios y `git stash`
**Sesión:** 5 — Flujos de Trabajo y Buenas Prácticas (viernes 11 de septiembre de 2026)
**Valor:** 4 de los 8 puntos del entregable del día
## Objetivo
Practicar, de forma diferenciada, `git restore`, `git reset` y `git revert`, y el uso de `git stash` para pausar trabajo en curso.
## Instrucciones paso a paso
```bash
cd mi-primer-repo
# git restore: descartar un cambio no confirmado
echo "línea de prueba" >> README.md
git restore README.md   # el archivo vuelve a su estado confirmado
# git reset --soft: deshacer el último commit conservando el cambio en staging
echo "cambio de prueba" >> script.js
git commit -am "Commit intencionalmente erróneo"
git reset --soft HEAD~1
git status   # el cambio sigue en staging, listo para corregirse
# git revert: deshacer un commit ya compartido, sin reescribir el historial
git commit -am "Confirmar cambio de prueba (para revertir después)"
git revert HEAD --no-edit
# git stash
echo "trabajo en progreso" >> index.html
git stash
git switch -c hotfix-urgente
# ... atender algo urgente ...
git switch main
git stash pop   # recuperar el trabajo pausado
```
## Entregable esperado
- Evidencia (capturas o `git log`) de haber usado `restore`, `reset --soft` y `revert` en escenarios distintos.
- Evidencia de `git stash` guardando y recuperando cambios al cambiar de rama.
## Ejemplo de entregable
Ejemplo de `git log --oneline` después del `revert`:
```
c3d4e5f Revert "Confirmar cambio de prueba (para revertir después)"
a1b2c3d Confirmar cambio de prueba (para revertir después)
```
Nótese que el commit original **sigue existiendo** en el historial: `revert` no lo borra, agrega uno nuevo que deshace su efecto. Ese es justamente el punto que se retoma en la Actividad 2 de hoy.
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Manejo de deshacer cambios | Uso correcto y diferenciado de `restore`, `reset` y `revert`, según el escenario que corresponde a cada uno. | 2 |
| Publicación del sitio | El sitio está publicado, es accesible públicamente y no contiene datos sensibles. *(evaluado junto con la Actividad 2)* | 2 |
*(Los 4 puntos restantes del entregable del día están en la Actividad 2 — Proyecto Integrador, Pasos 9 y 10.)*
