# Caso 1 — Cola de llamados para SDRs (réplica viva del CRM)

**Cliente:** SaaS B2B (anónimo) · **Equipo:** 2 SDRs · **Fuente de verdad:** base de ventas en Notion.

## Problema

Los SDRs trabajaban sobre el CRM completo: miles de cards mezcladas, sin saber a quién llamar hoy.
Necesitaban una lista corta, fresca y ordenada — y que lo que ellos anotaran volviera solo al CRM.

## Solución

Workflow en n8n que mantiene una base espejo ("Llamados"):

- **Dos ritmos:** corrida completa (5× al día) + corrida rápida **cada 2 minutos** que solo procesa lo que cambió (cards, filas y planilla del bot). Un lead nuevo aparece en la cola en minutos.
- **6 grupos por fórmula:** Closed Lost para llamar, Closed Lost originales, Leads, Leads vencidos, No se presentó a Propuesta, En curso (bot) y Follow-up programado (vuelve solo el día del vencimiento).
- **Ida y vuelta real:** Status, motivo de pérdida, follow-ups y datos del contacto que el SDR edita viajan solos al CRM; lo demás se pisa desde el CRM. Nunca se crean opciones ni propiedades nuevas en el CRM.
- **Botón de WhatsApp** por fila (normalización de teléfonos AR/UY/CO/MX) y asignación automática de SDR por país.
- **Loop con el bot de WhatsApp:** "no respondió" etiqueta la conversación y el bot retoma solo a los 40 días.

## Salvaguardas

Tope de escrituras por corrida · freno ante más de 25 cambios en un campo (señal de error, no de trabajo) ·
la corrida falla sin escribir si falta una columna · memoria de lo último sincronizado por card.

## Resultado

3.600+ filas sincronizadas, memoria = filas reales con 0 huérfanas; corridas estables con 0 escrituras
cuando nada cambió; vista por SDR agrupada por estado, lista para llamar.

**Stack:** n8n · Notion API · Chatwoot · WhatsApp · Google Sheets
