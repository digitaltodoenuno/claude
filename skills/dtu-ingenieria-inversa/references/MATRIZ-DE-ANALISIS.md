# Matriz de análisis de aplicaciones — DTU / REA

| Objetivo disponible y pregunta | Punto de partida recomendado | Comprobación |
|---|---|---|
| Repositorio con código completo | Git, lectura de código, pruebas | No hace falta REA para arquitectura ordinaria |
| JavaScript o Electron extraído, ASAR | `analyze_javascript_application` | módulos, imports y separación main/renderer |
| APK y clases Android | `inspect_android_package` y herramientas focalizadas disponibles | permisos, componentes, métodos y límites de JADX |
| ZIP, APK, IPA, MSIX, AppX, DMG | `open_binary`; `inspect_artifact` cuando proceda | inventario y estructura, no ejecución inferida |
| Ensamblado .NET | `inspect_managed_artifact` | metadatos, tipos, métodos y referencias |
| Ejecutable nativo | `open_binary` + motor disponible (Ghidra/Hopper/IDA) | pseudocódigo, assembly, llamadas; análisis no es código original |
| Aplicación web propia abierta | `list_browser_targets`, luego observación autorizada | navegación, estado, eventos, accesibilidad, límites |
| Electron propio en ejecución | `list_electron_targets`, comprobar fuses | no asumir que inspector está habilitado |
| HAR/SAZ/qlog previamente capturado | `inspect_web_network_capture` | observar datos registrados; no afirmar tráfico actual |
| PCAP grabado | herramientas de paquetes según plataforma | inventario y alcance de captura |
| WASM local | `inspect_wasm_artifact` | WAT import/export y límites de recuperación |
| Go o Rust binario | `inspect_go_binary` / `inspect_rust_binary` | metadatos embebidos, no fuente completa |
| Base SQLite local | `inspect_sqlite_database` | esquema y muestras autorizadas, proteger datos |

*Los nombres de herramientas corresponden a la documentación original de REA; confirmar disponibilidad real antes de invocarlos.*

## Evidencia y calidad
- Registrar ruta y hash de la fuente (cuando esté permitido), versión, fecha y condiciones del entorno.
- Para cada afirmación: evidencia observada, inferencia y limitación.
- Describir el camino **pantalla → interacción → estado → proceso → respuesta**, sin adivinar llamadas internas.
- Distinguir interoperabilidad legítima de reproducción de activos o código protegido.
- Para DTU, proponer una implementación independiente por contratos de comportamiento, UX y pruebas; no copiar secretos ni esquivar controles.

Referencias upstream: [JS/Electron](https://github.com/morluto/rea/blob/main/.agents/skills/reverse-engineer-anything/references/javascript-applications.md), [Android](https://github.com/morluto/rea/blob/main/.agents/skills/reverse-engineer-anything/references/android-applications.md), [Runtime](https://github.com/morluto/rea/blob/main/.agents/skills/reverse-engineer-anything/references/runtime-observation.md), [Binarios](https://github.com/morluto/rea/blob/main/.agents/skills/reverse-engineer-anything/references/native-and-artifacts.md).