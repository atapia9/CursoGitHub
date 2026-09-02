# Día 4 · Actividad 1 — Repositorio remoto y colaboración (Issue + Pull Request)
**Sesión:** 4 — Trabajo Remoto con GitHub (jueves 10 de septiembre de 2026)
**Valor:** 5 de los 8 puntos del entregable del día
## Objetivo
Conectar un repositorio local a GitHub mediante SSH y completar un ciclo real de colaboración (Issue → rama → Pull Request → revisión → fusión).
## Instrucciones paso a paso
```bash
# Generar y registrar la llave SSH (una sola vez por equipo)
ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"
# Copiar ~/.ssh/id_ed25519.pub en GitHub > Settings > SSH and GPG keys
ssh -T git@github.com
# Crear el repositorio en GitHub (vía interfaz web): curso-git-github
cd mi-primer-repo
git remote add origin git@github.com:tu-usuario/curso-git-github.git
git push -u origin main
```
En GitHub:
1. Crea un **Issue**: *"El README no explica cómo ejecutar script.js"* (etiqueta: `documentation`).
2. Crea una rama `mejora-readme`, agrega la explicación al README y súbela.
3. Abre un **Pull Request** desde `mejora-readme` hacia `main`, referenciando el Issue (`Closes #1`).
4. Pide a un compañero que deje al menos un comentario de revisión.
5. Atiende el comentario con un nuevo commit en la misma rama y fusiona el PR.
## Entregable esperado
- Enlace al repositorio `curso-git-github` en GitHub.
- Enlace al Issue y al Pull Request ya fusionado, con al menos un comentario de revisión visible.
## Ejemplo de entregable
Ejemplo de cuerpo del Pull Request:
```markdown
## Qué cambia
Se agrega al README la instrucción para ejecutar script.js con Node.
## Por qué
Cierra el Issue #1: el README no explicaba cómo correr el script.
Closes #1
```
Ejemplo de comentario de revisión esperado (de un compañero):
```
Se ve bien. Sugerencia menor: aclara qué versión de Node se necesita.
```
Y el commit de respuesta:
```
Especificar versión mínima de Node requerida (v18+)
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Autenticación y conexión remota | SSH (o PAT) configurado y funcional; el repositorio remoto refleja el historial local completo. | 2 |
| Ciclo de colaboración completo | Existen un Issue y un Pull Request reales, con al menos un comentario de revisión de otra persona antes de la fusión. | 3 |
*(Los 3 puntos restantes del entregable del día están en la Actividad 2 — Proyecto Integrador, Pasos 7 y 8.)*
