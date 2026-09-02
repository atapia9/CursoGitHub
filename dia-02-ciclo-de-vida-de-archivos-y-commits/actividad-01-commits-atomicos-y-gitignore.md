# Día 2 · Actividad 1 — Commits atómicos y `.gitignore`
**Sesión:** 2 — Ciclo de Vida de los Archivos y Commits (martes 8 de septiembre de 2026)
**Valor:** 5 de los 8 puntos del entregable del día
## Objetivo
Practicar un historial de commits atómicos y bien documentados, y aplicar correctamente un archivo `.gitignore`.
## Instrucciones paso a paso
```bash
mkdir mi-primer-repo && cd mi-primer-repo
git init
echo "# Mi primer repositorio de práctica" > README.md
git add README.md
git commit -m "Agregar README inicial"
# Agregar archivos adicionales en commits separados
touch index.html style.css script.js
git add index.html
git commit -m "Agregar estructura base de index.html"
git add style.css
git commit -m "Agregar hoja de estilos vacía"
git add script.js
git commit -m "Agregar script principal vacío"
# Crear y aplicar .gitignore
cat <<'EOF' > .gitignore
node_modules/
*.log
.env
dist/
.DS_Store
EOF
git add .gitignore
git commit -m "Agregar .gitignore del proyecto"
# Ver el historial acumulado
git log --oneline --graph
```
## Entregable esperado
- Repositorio `mi-primer-repo` con `README.md` y al menos 4 commits distintos.
- `.gitignore` funcional, con evidencia de `git status` antes y después de aplicarlo sobre un archivo que debía excluirse.
- Captura de `git log --oneline --graph`.
## Ejemplo de entregable
Salida esperada de `git log --oneline --graph`:
```
* 4f2a1c9 Agregar .gitignore del proyecto
* 9b7e3d0 Agregar script principal vacío
* 1a6c5f2 Agregar hoja de estilos vacía
* 7d0e8b1 Agregar estructura base de index.html
* 3c9f0a4 Agregar README inicial
```
Ejemplo de evidencia de `.gitignore` funcionando (antes de crear el archivo `debug.log`, Git lo reportaría como no rastreado; después de agregarlo a `.gitignore`, deja de aparecer en `git status`):
```
$ touch debug.log
$ git status
Untracked files:
  debug.log
$ echo "*.log" >> .gitignore
$ git status
nothing to commit, working tree clean
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Atomicidad y calidad de los commits | Cada commit representa un cambio único, con mensaje claro; no hay commits genéricos tipo "cambios". | 3 |
| `.gitignore` aplicado correctamente | El archivo excluye lo pertinente y el participante explica por qué esos archivos no deben versionarse. | 2 |
*(Los 3 puntos restantes del entregable del día están en la Actividad 2 — Proyecto Integrador, Pasos 2 a 4.)*
