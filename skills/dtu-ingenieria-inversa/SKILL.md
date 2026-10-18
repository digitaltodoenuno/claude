---
name: dtu-ingenieria-inversa
description: Analizar aplicaciones, binarios, paquetes, interfaces y comportamiento observable de software propio o autorizado; usar REA cuando se requiera evidencia de artefactos distribuidos o ejecución, documentar hallazgos y guiar una implementación independiente para Digital Todo en Uno.
---

# DTU — Análisis de aplicaciones e ingeniería inversa (G200)

**Material operativo adaptado por Digital Todo en Uno a partir de [REA / Reverse Engineer Anything](https://github.com/morluto/rea), de morluto.** La tecnología y el proyecto originales no son propiedad de DTU. La adaptación en español es material interno de DTU. Conservar aviso MIT en [LICENCIA-Y-ORIGEN.md](LICENCIA-Y-ORIGEN.md).

## Activación
Invocar para comprender comportamientos, arquitecturas observables, empaquetados, dependencias, flujos funcionales, compatibilidad o implementación equivalente de funciones, especialmente cuando no se dispone de código fuente completo. Si hay código fuente suficiente, empezar por su lectura normal y no ejecutar ingeniería inversa sin necesidad.

## Regla G200 — decisiones coordinadas
N1. **Alcance/autorización.** Identificar software y titularidad; delimitar acceso permitido, entornos y objetivos. No inferir permiso de una URL pública o un binario descargable.
N2. **Inventario.** Detectar plataforma, arquitectura, paquete, versión, origen, huellas, dependencias, fuentes de evidencia.
N3. **Selección del método.** Usar análisis estático antes de instrumentación; escoger herramienta según el tipo de objetivo en [MATRIZ-DE-ANALISIS.md](references/MATRIZ-DE-ANALISIS.md).
N4. **Hipótesis.** Formular qué comportamiento se investiga y qué datos lo demostrarían; separar observaciones de conjeturas.
N5. **Observación.** Usar herramientas realmente conectadas, con salidas comprobables; no afirmar que REA MCP está instalado por el solo hecho de existir esta skill.
N6. **Reconstrucción funcional.** Describir entradas, estados, decisiones, errores, interfaz y contratos observados. Implementar funcionalidad equivalente sin reproducir código o activos protegidos ajenos.
N7. **Validación.** Repetir escenarios, pruebas de regresión y contrastar hipótesis con el producto observado, documentando casos no cubiertos.
N8. **Seguridad y privacidad.** No recopilar ni publicar tokens, claves, datos personales, sesiones o tráfico sin autorización. Aplicar mínimo privilegio y pruebas sobre entornos controlados.
N9. **Legalidad.** No evadir DRM, licencias, autenticación, controles de acceso, protecciones ni restricciones de terceros; no emplear el método para tomar activos propietarios.
N10. **Entrega.** Entregar a DTU un informe en español con evidencia, alcance, decisiones, incertidumbres, riesgos, prueba realizada y recomendaciones; conservar la atribución de REA. No presentar análisis de metadatos como prueba de funcionamiento.

## Procedimiento mínimo
1. Revisar [MATRIZ-DE-ANALISIS.md](references/MATRIZ-DE-ANALISIS.md) y seleccionar la ruta por tipo de objetivo.
2. Comprobar herramientas disponibles. La skill **no instala REA, no configura MCP y no instala desensambladores**.
3. Si se requiere REA, seguir [CONFIGURACION-REA.md](references/CONFIGURACION-REA.md): diagnóstico previo, propuesta de cambios y aprobación de instalación/configuración.
4. Documentar resultados con [PLANTILLA-G200.md](references/PLANTILLA-G200.md); distinguir `OBSERVADO`, `INFERIDO`, `NO VERIFICADO` y `BLOQUEADO`.
5. Antes de modificar un producto, separar investigación de implementación y comprobar permisos del entorno destino.

## Límites y compatibilidad
- REA trabaja con ejecutables nativos, JavaScript/Electron, ensamblados administrados, paquetes Android, archivos web y observación de runtime, con requisitos diferentes por herramienta.
- Las capacidades reales dependen de la versión de REA y del MCP activo. **No inventar nombres de acciones ni asumir que todas están presentes.**
- El análisis estático no demuestra por sí solo el comportamiento en producción. El código descompilado es aproximado.
- No almacenar capturas sensibles, binarios ajenos o secretos en el repositorio de skills.

**Fuentes:** [REA original](https://github.com/morluto/rea) · [Skill de REA](https://github.com/morluto/rea/tree/main/.agents/skills/reverse-engineer-anything) · [Documentación oficial en español](https://github.com/morluto/rea/blob/main/docs/readme/README_es.md).