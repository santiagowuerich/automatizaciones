# Caso 2 — Reactivación de Closed Lost por WhatsApp

**Cliente:** SaaS B2B (anónimo) · **Volumen:** miles de ex-oportunidades dormidas.

## Problema

Los Closed Lost quedaban muertos en el CRM. Nadie los recontactaba porque hacerlo a mano no escala
y hacerlo mal (spam) quema el número.

## Solución

Motor de reactivación en varios workflows:

- **Secuencia de mensajes** con plantillas aprobadas (apertura, seguimientos, cierre), espaciados en el tiempo.
- **Planilla de estados**: cada lead tiene estado (`llamar`, `sin_respuesta`, `agotado`...) y el sistema decide el siguiente paso.
- **Respuestas humanas reales:** si el lead responde o el caso escala, la conversación pasa a un SDR con contexto.
- **Recontacto programado** para los que no respondieron: nuevo ciclo automático, sin intervención.
- **Bajas respetadas:** quien pide no ser contactado sale del sistema y no vuelve a entrar.

## Salvaguardas

Dedupe por teléfono · opt-out persistente · límites de envío para cuidar la reputación del número ·
alertas ante fallas de entrega.

**Stack:** n8n · WhatsApp Business (Meta templates) · Chatwoot · Google Sheets · Slack (alertas)
