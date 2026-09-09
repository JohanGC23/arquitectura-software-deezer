# ADR-005: Implementar observabilidad unificada

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

En un sistema distribuido, revisar logs aislados no es suficiente para detectar y explicar fallos.

## Decisión

Implementar tres pilares:

1. Métricas.
2. Logs estructurados.
3. Trazas distribuidas.

Toda solicitud llevará `correlation_id` / `trace_id`.

## Métricas mínimas

- Request rate.
- Error rate.
- Latencia p50/p95/p99.
- Saturación.
- Cache hit ratio.
- Tiempo de inicio de reproducción.
- Errores por dependencia.
- Lag de consumidores de eventos.

## Operación

- Alertas basadas en SLO.
- Dashboards por dominio.
- Runbooks.
- Postmortems sin culpabilización personal.
