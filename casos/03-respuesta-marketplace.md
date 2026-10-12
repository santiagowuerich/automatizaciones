# Caso 3 — Auto-respuesta de avisos de Marketplace con IA

**Producto propio** en producción.

## Problema

Los avisos de Marketplace reciben las mismas preguntas una y otra vez (precio, ubicación, disponibilidad,
permuta). Responder tarde = perder la venta; responder todo a mano = un trabajo part-time no pago.

## Solución

Bot que lee cada consulta entrante y responde con IA usando el contexto del aviso: qué se vende,
a cuánto, condiciones. Las consultas que detecta como intención de compra seria las marca para
seguimiento humano; el resto se resuelve solo.

## Resultado

Tiempo de primera respuesta de horas a segundos, corriendo solo en producción sin intervención diaria.

**Stack:** n8n · Facebook · IA (modelos de chat) · WhatsApp
