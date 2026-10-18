# REA — configuración responsable

**Guardar una skill en GitHub no instala el MCP REA en ChatGPT ni en los equipos.**

## Requisitos y diagnóstico
1. Identificar cliente de IA (Codex, Claude Code, Cursor u otro) y equipo autorizado.
2. Verificar Node.js compatible: **22.19+, 24.11+ o 26+**, además de npm (según documentación upstream).
3. Si el MCP ya está disponible, usar sus nombres y esquemas reales; no ejecutar `setup` innecesariamente.
4. Si no está disponible, hacer diagnóstico de solo lectura con el cliente compatible, por ejemplo `npx -y rea-agents@latest doctor --client codex --json`. Atención: `npx` puede descargar un paquete a caché.
5. Antes de escribir configuración, mostrar el plan: `npx -y rea-agents@latest setup --client codex --dry-run --json`.
6. Solo tras aprobación de cambios concretos, aplicar el setup al cliente autorizado. Instalar Hopper, Ghidra, IDA, Java o JADX **no** forma parte del setup normal ni se hará por inferencia.
7. Reiniciar/reconectar cliente y verificar herramientas disponibles; un registro MCP no prueba conexión activa.

## Alternativa estática
Para árbol JS/Electron o ASAR proporcionado y autorizado, REA documenta:
```bash
npx -y rea-agents@latest analyze-javascript-application /ruta/absoluta/app --json
```
No implica MCP instalado. Leer y conservar el reporte de evidencia y limitaciones.

### Regla de actualización
Usar versiones fijadas y procedencia oficial en proyectos reproducibles. No ejecutar `latest` ni instalar paquetes en entornos de producción sin revisión de dependencias, cambios y autorización.

Fuentes: [REA instalación](https://github.com/morluto/rea/blob/main/docs/installation.md), [REA skill y recuperación](https://github.com/morluto/rea/blob/main/.agents/skills/reverse-engineer-anything/references/connection-and-recovery.md).