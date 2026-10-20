# G200-X — Experimentación reversible y reconstrucción funcional DTU

**Vigencia:** 20 de octubre de 2026. **Tipo:** extensión operativa de G200, C200 y L200, no metodología sustituta. **Modo recomendado:** laboratorio autónomo autorizado.

## Principio
**Ser audaz al experimentar, riguroso al validar.** Convertir la incertidumbre técnica en experimentos ejecutables, no en bloqueos hipotéticos. Si una ruta falla, preservar lo útil, aprender y probar otra sin repetir ciegamente.

## Protocolo de diez nodos
1. **Alcance y permisos:** identificar software, titularidad, superficie y autorizaciones. No inferir permiso de tener un ZIP.
2. **Inventario breve:** plataforma, versión, paquete, manifiesto, arquitectura, dependencias, funciones conocidas. Tiempo orientativo 15–30 minutos para primer experimento si la complejidad lo permite.
3. **Función vertical:** escoger una función significativa para observar → entrada → proceso → resultado → prueba. No esperar a documentar toda la app.
4. **Protección:** registrar baseline, rama/commit, respaldo de estado externo (almacenamiento, base de datos, configuración), plan de restauración y límites del entorno.
5. **C200:** escoger navegador, inspección de JavaScript/extensiones, REA MCP si está disponible y aporta evidencia, scripts, tests y agentes. No exigir Hopper/REA para una extensión JS analizable sin ellos.
6. **Experimento:** formular hipótesis y criterio observable, implementar una versión propia separada y ejecutar en perfil Chrome aislado con datos ficticios.
7. **L200:** comparar contra el comportamiento permitido de referencia; clasificar OBSERVADO / INFERIDO / HIPÓTESIS / NO VERIFICADO / BLOQUEADO; registrar prueba, resultado y defectos.
8. **Decisión:** ÉXITO conservar; PARCIAL conservar funcional y reparar; FALLO entendido corregir; FALLO no entendido recabar evidencia y probar ruta diferente; BLOQUEO REAL explicar dependencia.
9. **Alternativas:** 3 rutas por bloqueo como presupuesto orientativo, sin repetir intentos idénticos. Si falla, revertir solo cambios propios del experimento; no perder mejoras verificadas.
10. **Documentación:** registrar evidencia, hashes/versión cuando corresponda, commit, decisiones y estado para traspaso entre sesiones. El código de producto va en repositorio propio autorizado.

## Autonomía graduada
- **Conservador:** requiere aprobación antes de cambios relevantes.
- **Laboratorio autónomo (predeterminado en proyectos aislados y autorizados):** puede editar código experimental, ejecutar tests, crear ramas y checkpoints y restaurar sus cambios sin nuevas confirmaciones.
- **Acelerado:** varios prototipos/ramas aisladas y comparación paralela cuando recursos y permisos lo permiten.

**Límites invariantes:** no instalar software, modificar cuentas reales, interactuar con terceros, exponer datos, generar costos no aprobados, elevar permisos, publicar o desplegar sin autorización específica. Nunca eludir DRM, autenticación o licencias; no copiar código/activos propietarios ajenos. Distinguir el acceso a un paquete del derecho de analizarlo.

## Matriz de valor por función
Clasificar cada función objetivo como **REPRODUCIR, MEJORAR, CREAR o DESCARTAR**. El primer piloto debe buscar una función útil reproducida, una deficiencia mejorada y una capacidad nueva; son objetivos, no resultados garantizados. Se permite abandonar una función si no aporta valor.

## Entregables
- Inventario/alcance (incluye permisos y lo no accesible).
- Tabla de funciones con hipótesis y prioridad.
- Primer prototipo vertical y tests reproducibles.
- Comparativa contra referencia con evidencia observable.
- Registro de intentos fallidos, correcciones y rutas descartadas.
- Estado estable recuperable y siguiente experimento.
- Métricas: capacidades demostradas, pruebas superadas, defectos abiertos, hipótesis resueltas; porcentaje solo con denominador explícito.

## Laboratorio Chrome — paquete ZIP
Aceptar ZIP con carpeta descomprimible de extensión, típicamente `manifest.json`, scripts, assets; distinguir de ZIP de Chrome Web Store u otros contenedores. Diagnóstico estático primero: validar MV2/MV3, permissions/host_permissions, background service worker, content_scripts, popup, options, web_accessible_resources, CSP, almacenamiento, endpoints, scripts remotos, código ofuscado y licencias. Inspeccionar sin ejecutarlo por defecto. No abrir perfiles personales ni enviar credenciales. Si el código está minificado, incompleto o depende de backend, complementar con versión instalada en entorno aislado, capturas, flujos de prueba, URLs de demostración o credenciales ficticias de prueba **solo cuando sea imprescindible y autorizado**. Un ZIP es suficiente para comenzar inspección estática, no prueba toda la conducta en ejecución.

## Interpretación operativa
La antigua pauta 'no avances cuando algo falle' se interpreta ahora como 'no continuar por la misma ruta sin diagnóstico; escoger alternativa autorizada y recuperable'. La seguridad se resuelve con aislamiento y backups verificables, no con inmovilidad.
