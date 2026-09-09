# ADR-003: Servir audio mediante Object Storage + CDN

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

El audio representa gran volumen de datos y no debe cruzar los servicios de aplicación.

## Decisión

Almacenar medios en Object Storage y distribuirlos mediante CDN. El Playback Service entrega autorización/token temporal, no el archivo completo.

## Beneficios

- Menor latencia global.
- Menor carga del backend.
- Mejor absorción de picos.
- Reducción de transferencia desde origen.
- Caché geográficamente cercana.

## Riesgos

- Costos de egress.
- Invalidación de caché.
- Protección de contenido.

## Mitigaciones

- URLs firmadas y expirables.
- Políticas de caché.
- Segmentación del audio.
- Monitoreo de hot objects.
