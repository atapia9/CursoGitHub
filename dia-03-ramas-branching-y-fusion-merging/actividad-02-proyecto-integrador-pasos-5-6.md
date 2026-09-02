# Día 3 · Actividad 2 — Proyecto Integrador: Pasos 5 y 6 (Política de MFA y conflicto resuelto)
**Sesión:** 3 — Ramas (Branching) y Fusión (Merging)
**Proyecto Integrador:** Pasos 5 y 6 de 10
**Hilo conductor:** Ciberseguridad para Personal de Soporte
**Valor:** 2 de los 8 puntos del entregable del día
## Contexto
En un equipo real de soporte, dos personas pueden proponer redacciones distintas para el mismo procedimiento de seguridad. Hoy se simula exactamente eso sobre el protocolo de reporte de phishing, y se agrega una nueva política sobre autenticación multifactor (MFA).
## Instrucciones paso a paso
```bash
cd guia-seguridad-soporte
# Paso 5 — Política de MFA
git switch -c politica-mfa
cat <<'EOF' > politicas/politica-mfa.md
# Política de Autenticación Multifactor (MFA)
- MFA obligatorio en correo corporativo, VPN y accesos administrativos.
- Se prefieren aplicaciones autenticadoras sobre SMS.
- Los códigos de respaldo se almacenan únicamente en el gestor de contraseñas
  corporativo, nunca en texto plano.
EOF
git add politicas/politica-mfa.md
git commit -m "Agregar política de autenticación multifactor (MFA)"
git switch main
git merge politica-mfa
git log --oneline --graph   # confirmar si fue fast-forward o no
# Paso 6 — Conflicto simulado en el protocolo de phishing
git switch -c revision-soporte-1
sed -i '' 's/Reenviar el correo al área de seguridad sin responderlo./Reenviar el correo al buzón phishing@empresa.com sin responderlo./' politicas/protocolo-reporte-phishing.md 2>/dev/null || \
sed -i 's/Reenviar el correo al área de seguridad sin responderlo./Reenviar el correo al buzón phishing@empresa.com sin responderlo./' politicas/protocolo-reporte-phishing.md
git commit -am "Especificar el buzón de reporte de phishing"
git switch main
git switch -c revision-soporte-2
sed -i '' 's/Reenviar el correo al área de seguridad sin responderlo./Reenviar el correo usando el botón "Reportar phishing" de Outlook./' politicas/protocolo-reporte-phishing.md 2>/dev/null || \
sed -i 's/Reenviar el correo al área de seguridad sin responderlo./Reenviar el correo usando el botón "Reportar phishing" de Outlook./' politicas/protocolo-reporte-phishing.md
git commit -am "Usar el botón integrado de Outlook para reportar phishing"
git switch main
git merge revision-soporte-1
git merge revision-soporte-2   # conflicto esperado
# Resolver a mano combinando ambas ideas o eligiendo una, y documentar por qué
git add politicas/protocolo-reporte-phishing.md
git commit -m "Resolver conflicto: usar el botón de Outlook y, si no está disponible, el buzón phishing@empresa.com"
```
## Entregable esperado
- Política de MFA fusionada en `main`.
- Conflicto real resuelto en `protocolo-reporte-phishing.md`, con el commit de fusión explicando la decisión tomada.
## Ejemplo de entregable
Ejemplo del mensaje de commit de resolución (el que realmente se califica, no solo el código):
```
Resolver conflicto: usar el botón de Outlook y, si no está disponible,
el buzón phishing@empresa.com
Se combinaron ambas propuestas del equipo de soporte porque no son
excluyentes: el botón de Outlook es el método preferido, y el buzón
queda como respaldo para quien use un cliente de correo distinto.
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Avance del Proyecto Integrador | La política de MFA y el protocolo de phishing reflejan el conflicto resuelto de forma coherente con el resto de la guía. | 1 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con evidencia clara del antes y después del conflicto. | 1 |
**Siguiente paso:** Día 4, Actividad 2 — subir `guia-seguridad-soporte` a GitHub como repositorio privado y abrir el primer Pull Request revisado.
