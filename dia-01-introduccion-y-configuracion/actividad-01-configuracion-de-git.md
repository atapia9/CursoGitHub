# Día 1 · Actividad 1 — Configuración verificable de Git
**Sesión:** 1 — Introducción y Configuración (lunes 7 de septiembre de 2026)
**Valor:** 5 de los 8 puntos del entregable del día (los otros 3 corresponden a la Actividad 2)
## Objetivo
Demostrar que Git quedó correctamente instalado y configurado en el equipo del participante, y que comprende el modelo de los tres estados (Working Directory, Staging Area, Repositorio).
## Instrucciones paso a paso
1. Instala Git según tu sistema operativo y confirma la versión instalada.
2. Configura tu identidad de forma global (`user.name`, `user.email`).
3. Configura tu editor por defecto.
4. Crea un alias para un comando que uses con frecuencia.
5. Crea una carpeta de práctica, inicialízala como repositorio y describe, en un archivo de texto, cómo un archivo se mueve por los tres estados de Git.
```bash
# 1. Verificar instalación
git --version
# 2. Configurar identidad
git config --global user.name "Tu Nombre"
git config --global user.email "tu_correo@ejemplo.com"
# 3. Configurar editor por defecto
git config --global core.editor "code --wait"
# 4. Crear un alias
git config --global alias.st status
# 5. Repositorio de práctica
mkdir practica-dia1 && cd practica-dia1
git init
```
## Entregable esperado
- Captura de pantalla de `git --version` y de `git config --list`.
- Captura del alias funcionando (`git st` mostrando lo mismo que `git status`).
- Archivo `tres-estados.md` con la explicación en tus propias palabras, usando un ejemplo propio.
## Ejemplo de entregable
Salida esperada de `git config --list` (los valores cambian según cada participante):
```
user.name=Ana Torres
user.email=ana.torres@ejemplo.com
core.editor=code --wait
alias.st=status
```
Extracto de ejemplo para `tres-estados.md`:
```markdown
## Los tres estados de Git — mi ejemplo
1. Edito el archivo index.html en mi editor → está en el Working Directory.
2. Ejecuto `git add index.html` → el cambio pasa al Staging Area.
3. Ejecuto `git commit -m "Agregar estructura base de index.html"` →
   el cambio queda guardado de forma permanente en el Repositorio Local.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Instalación y configuración funcional | Git instalado, identidad global configurada correctamente y verificable con capturas. | 3 |
| Explicación de los tres estados | El documento entregado describe con claridad y con un ejemplo propio el recorrido Working Directory → Staging Area → Repositorio. | 2 |
*(Los 3 puntos restantes del entregable del día están en la Actividad 2 — Proyecto Integrador, Paso 1.)*
