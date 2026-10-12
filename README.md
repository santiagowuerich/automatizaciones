# Automatizaciones en producción (n8n + IA)

Casos reales corriendo hoy en producción. Sin demos: cada caso describe un sistema vivo, con sus
salvaguardas y sus números. Detalle técnico en `casos/`.

| # | Caso | Qué hace | Estado |
|---|------|----------|--------|
| 1 | [Cola de llamados para SDRs](casos/01-cola-sdr.md) | Réplica viva CRM → cola de llamados siempre fresca | Producción |
| 2 | [Reactivación de Closed Lost](casos/02-reactivacion-closed-lost.md) | Secuencias de WhatsApp + recontacto programado + escalado humano | Producción |
| 3 | [Auto-respuesta de Marketplace con IA](casos/03-respuesta-marketplace.md) | Responde consultas de avisos automáticamente | Producción |

## Cómo trabajo

- **DEV antes que PROD**: todo se valida en gemelo de desarrollo con datos mock; a producción solo entra con diff explícito y OK humano.
- **Guardas, no esperanza**: topes de escritura por corrida, frenos ante cambios masivos, detección de columnas renombradas, memoria de lo sincronizado.
- **Operable**: cada workflow avisa sus fallas a un manejador central con alertas.

## Contacto

- 🌐 [santiagowuerich.info](https://santiagowuerich.info)
