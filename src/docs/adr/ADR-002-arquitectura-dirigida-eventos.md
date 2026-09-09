# ADR-002: Usar arquitectura dirigida por eventos para procesos asíncronos

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

Eventos de escucha, favoritos, cambios de playlist, ingestión y analítica producen alto volumen y no deben bloquear la experiencia.

## Decisión

Introducir un Event Bus para desacoplar productores y consumidores.

Eventos ejemplo:

- `track_started`
- `track_completed`
- `track_liked`
- `playlist_updated`
- `subscription_changed`
- `content_ingested`
- `content_classified`

## Reglas

- Eventos versionados.
- Consumidores idempotentes.
- Dead-letter queue.
- Reintentos con backoff.
- Correlation ID.
- Outbox para eventos vinculados a transacciones críticas.

## Consecuencias

Mejora escalabilidad y desacoplamiento, pero introduce consistencia eventual y necesidad de gobernanza.
