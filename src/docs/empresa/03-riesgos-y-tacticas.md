# Riesgos arquitectónicos y tácticas

| Riesgo | Impacto | Táctica propuesta |
|---|---|---|
| Sobrecarga en lanzamientos populares | Alto | CDN, caché, autoscaling, rate limiting. |
| Caída de un servicio secundario | Medio/Alto | Circuit breaker, timeouts, fallback. |
| Dependencia excesiva de una BD única | Alto | Separación por dominio, réplicas y persistencia especializada. |
| Inconsistencias por eventos asíncronos | Medio | Idempotencia, outbox, claves de correlación, DLQ. |
| Recomendaciones lentas | Medio | Features precalculadas, caché, procesamiento offline + online. |
| Fraude / abuso de streaming | Alto | Detección de anomalías, reglas, auditoría y rate limits. |
| Robo de sesiones/tokens | Alto | OAuth/OIDC, expiración corta, rotación y almacenamiento seguro. |
| Exposición de datos sensibles | Alto | Cifrado, least privilege, secretos gestionados. |
| Falla regional | Alto | Multi-AZ y estrategia de recuperación multi-región. |
| Costos altos de transferencia de audio | Alto | CDN, compresión, formatos adaptativos y políticas de caché. |
| Índice de búsqueda desactualizado | Medio | Sincronización basada en eventos y reconciliación periódica. |
| Contenido generado por IA/fraudulento | Medio/Alto | Pipeline de clasificación/etiquetado y reglas de elegibilidad para recomendaciones. |

## Degradación elegante

La arquitectura prioriza que una falla no crítica no detenga la reproducción:

- Si recomendaciones falla → mostrar favoritos, historial y tendencias.
- Si analítica falla → bufferizar eventos.
- Si notificaciones falla → reintentar asíncronamente.
- Si búsqueda falla → permitir acceso a biblioteca y playlists ya cargadas.
- Si facturación externa está degradada → no interrumpir una sesión válida de forma inmediata; procesar cambios mediante flujo controlado.

## Riesgos de la propia arquitectura

Los microservicios y eventos incrementan la complejidad operativa. Por eso se exige:

- Automatización de CI/CD.
- Observabilidad unificada.
- Contratos de API.
- Versionado de eventos.
- SLO por servicio.
- Runbooks de incidentes.
