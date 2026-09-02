# Día 2 · Actividad 2 — Proyecto Integrador: Pasos 2 a 4 (Estructura, `.gitignore` y políticas)
**Sesión:** 2 — Ciclo de Vida de los Archivos y Commits
**Proyecto Integrador:** Pasos 2, 3 y 4 de 10
**Hilo conductor:** Ciberseguridad para Personal de Soporte
**Valor:** 3 de los 8 puntos del entregable del día
## Contexto
Con la identidad ya declarada (Día 1), hoy se construye el esqueleto real de la guía: el README que describe el propósito del proyecto, un `.gitignore` pensado específicamente para un repositorio que documenta procedimientos de seguridad, y las tres primeras políticas retomadas del curso de Ciberseguridad para Personal de Soporte.
## Instrucciones paso a paso
```bash
cd guia-seguridad-soporte
# Paso 2 — README
cat <<'EOF' > README.md
# Guía de Seguridad para Personal de Soporte
Este repositorio documenta, versiona y publica las políticas y protocolos
de ciberseguridad que el personal de soporte debe seguir, retomando el
curso de Ciberseguridad para Personal de Soporte.
## Temas documentados
- Phishing e ingeniería social
- Gestión de contraseñas
- Manejo seguro de credenciales
- Clasificación de datos
- Respuesta a incidentes
EOF
git add README.md
git commit -m "Agregar README con el propósito y alcance de la guía"
# Paso 3 — .gitignore específico del proyecto
cat <<'EOF' > .gitignore
credenciales-prueba.env
capturas/
*.log
EOF
git add .gitignore
git commit -m "Agregar .gitignore para excluir posibles datos sensibles"
# Paso 4 — políticas, un commit por archivo
mkdir politicas
printf "# Política de Contraseñas\n\n- Longitud mínima de 12 caracteres.\n- Uso obligatorio de un gestor de contraseñas.\n- Prohibido reutilizar contraseñas entre sistemas.\n" > politicas/politica-contrasenas.md
git add politicas/politica-contrasenas.md
git commit -m "Agregar política de contraseñas"
printf "# Protocolo de Reporte de Phishing\n\n1. No hacer clic en enlaces sospechosos.\n2. Reenviar el correo al área de seguridad sin responderlo.\n3. Eliminar el correo una vez reportado.\n" > politicas/protocolo-reporte-phishing.md
git add politicas/protocolo-reporte-phishing.md
git commit -m "Agregar protocolo de reporte de phishing"
printf "# Checklist de Respuesta a Incidentes\n\n- [ ] Contener el incidente.\n- [ ] Notificar al responsable de seguridad.\n- [ ] Documentar la línea de tiempo.\n- [ ] Aplicar la corrección.\n- [ ] Revisar lecciones aprendidas.\n" > politicas/checklist-respuesta-incidentes.md
git add politicas/checklist-respuesta-incidentes.md
git commit -m "Agregar checklist de respuesta a incidentes"
```
## Entregable esperado
- `README.md` con los cinco temas de seguridad listados.
- `.gitignore` propio del proyecto (distinto al de `mi-primer-repo`).
- Los tres documentos de `/politicas`, cada uno en su propio commit.
## Ejemplo de entregable
Estructura final esperada del repositorio al cierre del Día 2:
```
guia-seguridad-soporte/
├── README.md
├── .gitignore
└── politicas/
    ├── politica-contrasenas.md
    ├── protocolo-reporte-phishing.md
    └── checklist-respuesta-incidentes.md
```
## Rúbrica aplicable
| Criterio | Descripción | Puntos |
|---|---|---|
| Avance del Proyecto Integrador | Los tres documentos de política existen como commits separados y con contenido coherente con el curso de ciberseguridad. | 2 |
| Entrega en tiempo y forma | Se presenta al cierre de la sesión, con el historial visible y legible. | 1 |
**Siguiente paso:** Día 3, Actividad 2 — fusionar la política de MFA y resolver un conflicto real en el protocolo de phishing.
