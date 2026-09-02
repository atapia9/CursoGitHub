# Día 3 · Actividad 1 — Fusiones y resolución de conflictos
**Sesión:** 3 — Ramas (Branching) y Fusión (Merging) (miércoles 9 de septiembre de 2026)
**Valor:** 6 de los 8 puntos del entregable del día
## Objetivo
Practicar, en `mi-primer-repo`, una fusión fast-forward, una fusión recursiva (three-way) y un conflicto real provocado y resuelto.
## Instrucciones paso a paso
```bash
cd mi-primer-repo
# Fusión fast-forward
git switch -c feature-saludo
echo "console.log('Hola, curso de Git');" >> script.js
git add script.js
git commit -m "Agregar saludo de bienvenida en script.js"
git switch main
git merge feature-saludo
git log --oneline --graph   # debe verse un avance simple, sin commit de fusión
# Fusión NO fast-forward
git switch -c feature-despedida
echo "console.log('Gracias por participar');" >> script.js
git commit -am "Agregar despedida en script.js"
git switch main
echo "<!-- comentario en main -->" >> index.html
git commit -am "Agregar comentario en index.html directamente en main"
git merge feature-despedida
git log --oneline --graph   # ahora debe aparecer un commit de fusión
# Conflicto provocado intencionalmente
git switch -c feature-a
echo "Versión A de la línea de bienvenida" > bienvenida.txt
git add bienvenida.txt && git commit -m "Proponer versión A de bienvenida"
git switch main
git switch -c feature-b
echo "Versión B de la línea de bienvenida" > bienvenida.txt
git add bienvenida.txt && git commit -m "Proponer versión B de bienvenida"
git switch main
git merge feature-a
git merge feature-b   # aquí Git reportará el conflicto
# Editar bienvenida.txt a mano, eliminar los delimitadores <<<<<<<, ======= y >>>>>>>
git add bienvenida.txt
git commit -m "Resolver conflicto: se conserva la versión B por ser más reciente"
```
## Entregable esperado
- `git log --graph` mostrando claramente los tres escenarios (fast-forward, recursiva, con conflicto resuelto).
- Explicación por escrito de la diferencia entre `git branch -d` y `git branch -D`.
## Ejemplo de entregable
Ejemplo de cómo debe verse `bienvenida.txt` con el conflicto sin resolver:
```
<<<<<<< HEAD
Versión A de la línea de bienvenida
=======
Versión B de la línea de bienvenida
>>>>>>> feature-b
```
Y ya resuelto:
```
Versión B de la línea de bienvenida
```
Ejemplo de explicación esperada sobre `-d` vs `-D`:
```markdown
`git branch -d rama` elimina la rama solo si ya fue fusionada (protección
contra pérdida de trabajo). `git branch -D rama` la elimina de forma
forzada, incluso si tiene commits que no se fusionaron en ningún lado —
útil para descartar un experimento, pero arriesgado si no se está seguro.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Manejo de ramas y fusiones | Existen ambos tipos de fusión (fast-forward y recursiva), correctamente identificados en el historial. | 3 |
| Resolución de conflictos | El conflicto fue provocado y resuelto de forma correcta, sin pérdida accidental de información, y documentado en el commit de fusión. | 3 |
*(Los 2 puntos restantes del entregable del día están en la Actividad 2 — Proyecto Integrador, Pasos 5 y 6.)*
