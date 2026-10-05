# Plantillas DTU — cupón y remarketing, octubre 2026

Creación: 5 de octubre de 2026. Diseño con el logo, fotografía y colores DTU: azul `#0158a5`, menta `#6bc9b2` y azul oscuro `#102d49`. Voz de Miguel: español mexicano, clara, cálida y práctica. Asuntos con 💡 según la identidad de correo vigente.

## Archivos y asuntos

| Archivo | Asunto | Uso |
| --- | --- | --- |
| [01-nuevo.html](01-nuevo.html) | 💡 Tu acceso a DTU por $20: disponible hasta el 14 de octubre | Registro nuevo antes del cierre |
| [02-remarketing.html](02-remarketing.html) | 💡 Pediste el cupón de DTU. Quiero avisarte antes del cambio de precio | Primer aviso a quien solicitó el cupón |
| [03-beneficio.html](03-beneficio.html) | 💡 Una oportunidad sin seguimiento se enfría | Seguimiento después de 48 horas |
| [04-recordatorio.html](04-recordatorio.html) | 💡 El 14 de octubre cierra el precio de $20 al mes | Recordatorio después de otras 72 horas |
| [05-ultimo-dia.html](05-ultimo-dia.html) | 💡 Hoy, 14 de octubre, termina el acceso por $20 al mes | Exclusivamente 14 de octubre, antes del cierre |
| [06-vigente.html](06-vigente.html) | 💡 Tu siguiente paso para ordenar el seguimiento de tu negocio | Nuevas contrataciones desde el 15 de octubre |
| [07-permiso.html](07-permiso.html) | 💡 ¿Todavía te interesa ordenar tu negocio con DTU? | Confirmar interés antes de pausar la secuencia |

## Condiciones de uso

- Precio de la ventana: $20 USD mensuales hasta el miércoles 14 de octubre de 2026 a las 11:59 p. m., hora de Ciudad de México. Se conserva mientras la suscripción permanezca activa.
- Desde el 15 de octubre: $39 USD al mes para nuevas contrataciones. No aplicar el aumento retroactivamente a las suscripciones activas de la ventana.
- La información de precio fue confirmada por Miguel para esta campaña; guardar HTML no confirma que el checkout futuro ya cobre $39.
- Las primeras cinco piezas ofrecen $20: comprobar la fecha justo antes de enviar. No reutilizarlas para promociones futuras sin actualizar contenido y checkout.
- `05-ultimo-dia.html` requiere fecha local 14/10/2026 y un envío anterior al cierre. Una espera relativa de días no garantiza esa fecha.
- `06-vigente.html` se usa desde el 15/10/2026. Su CTA informativo va al sitio; no representa un checkout de $39 probado.
- `07-permiso.html` requiere ausencia de respuesta/interés en el ciclo. No enviar a quien compró, respondió, se dio de baja o tiene una suspensión de correo.
- Los exclientes pueden recibir la campaña si cancelaron la membresía, conservan consentimiento de correo y no tienen otra suscripción vigente. La baja de membresía y la baja de email son cosas distintas.

## Edición y formato

HTML con tablas, estilos en línea y CSS responsive. No contiene JavaScript. El saludo utiliza `{{contact.first_name}}` y la baja `{{email.unsubscribe_link}}`; comprobar su resolución en un contacto interno antes del envío real. Configurar el asunto en la acción de correo: el `<title>` del HTML no sustituye el asunto del envío.

Las piezas comerciales incluyen un botón principal y la pieza de permiso invita a responder. No se incluyeron descuentos contra $97, pruebas gratis, cupos o testimonios sin evidencia.

## Validación del ciclo

Las siete piezas fueron guardadas como plantillas HTML en GHL. Se revisaron precios, fechas, asunto, CTA y baja. Se renderizó la pieza de remarketing a 900 y 375 px con WeasyPrint; el botón recibió fondo CSS explícito además de `bgcolor`. El render no acredita compatibilidad real en todas las bandejas. GHL añade sus ajustes para Outlook al HTML guardado; por eso el archivo remoto puede diferir del fuente sin perder el contenido.

La activación de automatizaciones y el envío de pruebas siguen el proceso operativo privado de DTU. Este directorio público contiene únicamente diseño y copy, sin exportaciones de clientes ni URLs firmadas.
