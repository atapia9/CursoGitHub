# Día 5 · Actividad 2 — Proyecto Integrador: Pasos 9 y 10 (Incidente simulado y publicación final)
**Sesión:** 5 — Flujos de Trabajo y Buenas Prácticas
**Proyecto Integrador:** Pasos 9 y 10 de 10 (cierre del proyecto)
**Hilo conductor:** Ciberseguridad para Personal de Soporte
**Valor:** 4 de los 8 puntos del entregable del día
## Contexto
Este es el cierre del Proyecto Integrador. Se simula el error más común y más grave en el manejo de secretos con Git — subir una credencial por accidente — y se publica la versión final y depurada de la guía.
## Instrucciones paso a paso
```bash
cd guia-seguridad-soporte
# Paso 9 — Simular la exposición de una credencial
echo 'DB_PASSWORD="contraseña-de-prueba-123"' > credenciales-prueba.env
git add -f credenciales-prueba.env   # forzado, a propósito, para simular el error
git commit -m "Agregar credenciales-prueba.env (ERROR intencional para la práctica)"
git push origin main
# "Eliminarlo" con un nuevo commit (esto NO es suficiente, es justo el punto a documentar)
git rm credenciales-prueba.env
git commit -m "Eliminar credenciales-prueba.env"
git push origin main
```
Agrega a `politicas/checklist-respuesta-incidentes.md` una sección nueva documentando la lección:
```markdown
## Lección: exposición accidental de una credencial
Eliminar el archivo en un commit nuevo NO borra la credencial del historial:
sigue siendo recuperable en los commits anteriores del repositorio remoto.
Un `git revert` tiene el mismo problema. La única respuesta correcta ante
una fuga real es **rotar (invalidar y reemplazar) la credencial expuesta**,
tratándola como comprometida desde el momento en que se subió, sin importar
si después se "borró".
```
```bash
git add politicas/checklist-respuesta-incidentes.md
git commit -m "Documentar la lección del incidente simulado de credenciales"
# Paso 10 — Publicación final con GitHub Pages
mkdir sitio
cat <<'EOF' > sitio/index.html
<!DOCTYPE html>
<html lang="es">
<head><meta charset="UTF-8"><title>Guía de Seguridad para Personal de Soporte</title></head>
<body>
  <h1>Guía de Seguridad para Personal de Soporte</h1>
  <p>Políticas de contraseñas, phishing, MFA y respuesta a incidentes.</p>
</body>
</html>
EOF
git add sitio/index.html
git commit -m "Agregar sitio estático para publicación en GitHub Pages"
git push origin main
# Habilitar en GitHub: Settings > Pages > rama main > carpeta /sitio
```
## Entregable esperado
- Documentación por escrito del incidente simulado y de por qué `revert`/eliminar no basta.
- URL pública del sitio publicado con GitHub Pages (sin datos sensibles).
- Reflexión final de 5 a 8 líneas conectando este curso con el de Ciberseguridad para Personal de Soporte.
## Ejemplo de entregable
Ejemplo de reflexión final:
```markdown
## Reflexión de cierre
Este proyecto me hizo ver que "buenas prácticas de Git" y "buenas prácticas
de ciberseguridad" son, en el fondo, el mismo hábito: dejar todo trazable,
revisado por alguien más antes de publicarse, y asumir que un error visible
(como una credencial expuesta) no se arregla ocultándolo, sino corrigiendo
la causa — en este caso, rotando la credencial. El curso de ciberseguridad
me dio el checklist; este curso me dio la herramienta para que ese checklist
sea algo que el equipo realmente use y mantenga actualizado.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Comprensión del incidente de seguridad simulado | La explicación distingue correctamente entre "borrar del historial" y "la credencial ya fue expuesta y debe rotarse". | 3 |
| Reflexión de cierre | La reflexión conecta explícitamente contenidos de ambos cursos, no es genérica. | 1 |
**Este es el último paso.** Con el Día 5 completo, el Proyecto Integrador Final queda cerrado: `guia-seguridad-soporte` documenta, versiona, revisa y publica una guía real de ciberseguridad usando exactamente el flujo de trabajo enseñado en las cinco sesiones del curso.

> **Criterios completos:** la escala de puntos de este entregable, la evidencia que se considera válida y el checklist de autoevaluación están en la [Guía de Evaluación del Proyecto Integrador Final](../GUIA-EVALUACION-PROYECTO-INTEGRADOR.md).
