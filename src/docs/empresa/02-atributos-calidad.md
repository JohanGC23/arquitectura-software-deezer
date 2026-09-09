# Atributos de calidad

Los valores numéricos siguientes son **objetivos académicos de diseño**, no métricas internas de Deezer.

## 1. Priorización

| Prioridad | Atributo | Razón |
|---:|---|---|
| 1 | Disponibilidad | La reproducción debe estar disponible casi todo el tiempo. |
| 2 | Rendimiento | El usuario espera respuesta inmediata y arranque rápido del audio. |
| 3 | Escalabilidad | El tráfico puede crecer por región, horario o lanzamientos. |
| 4 | Seguridad | Se gestionan cuentas, datos personales y suscripciones. |
| 5 | Resiliencia | Una falla parcial no debe detener toda la experiencia. |
| 6 | Observabilidad | Los fallos distribuidos requieren diagnóstico rápido. |
| 7 | Mantenibilidad | Equipos distintos deben poder evolucionar servicios. |
| 8 | Usabilidad | La experiencia debe ser simple y consistente. |

## 2. Escenarios de calidad

### AQ-01 — Disponibilidad de reproducción

- **Fuente:** usuario.
- **Estímulo:** solicita reproducir una canción.
- **Entorno:** operación normal o degradación parcial.
- **Artefacto:** servicio de playback.
- **Respuesta:** se autoriza y entrega una URL/segmento reproducible.
- **Métrica objetivo:** disponibilidad mensual >= 99.95%.

### AQ-02 — Tiempo de inicio

- **Fuente:** usuario.
- **Estímulo:** pulsa “reproducir”.
- **Respuesta:** comienza la reproducción usando contenido cercano por CDN.
- **Métrica objetivo:** p95 de inicio <= 2 s en red adecuada.

### AQ-03 — Búsqueda

- **Fuente:** usuario.
- **Estímulo:** busca artista, álbum o canción.
- **Respuesta:** el sistema devuelve resultados relevantes.
- **Métrica objetivo:** p95 <= 500 ms para consultas cacheables/comunes.

### AQ-04 — Escalabilidad

- **Fuente:** evento de alta demanda.
- **Estímulo:** el tráfico aumenta 5 veces.
- **Respuesta:** se escala horizontalmente sin caída general.
- **Métrica objetivo:** mantener errores < 1% durante el escalamiento.

### AQ-05 — Resiliencia de recomendaciones

- **Fuente:** falla del motor de recomendaciones.
- **Estímulo:** servicio de personalización no disponible.
- **Respuesta:** la app sigue permitiendo buscar y reproducir; usa fallback de tendencias/favoritos.
- **Métrica objetivo:** reproducción no afectada por la falla del recomendador.

### AQ-06 — Seguridad

- **Fuente:** actor malicioso.
- **Estímulo:** intenta reutilizar un token inválido/expirado.
- **Respuesta:** acceso denegado y evento registrado.
- **Métrica objetivo:** 100% de endpoints privados validan autenticación/autorización.

### AQ-07 — Recuperabilidad

- **Fuente:** fallo de una instancia.
- **Estímulo:** proceso/VM/contenedor deja de responder.
- **Respuesta:** balanceador retira la instancia y el orquestador la reemplaza.
- **Métrica objetivo:** recuperación automática <= 5 min.

### AQ-08 — Observabilidad

- **Fuente:** equipo SRE.
- **Estímulo:** sube la tasa de errores.
- **Respuesta:** alerta con trazas y correlación por request.
- **Métrica objetivo:** detección <= 5 min para incidentes críticos.

## 3. Tácticas asociadas

- Redundancia multi-zona.
- Autoscaling.
- CDN y cachés.
- Circuit breakers.
- Timeouts y retries con backoff.
- Colas/eventos.
- Bulkheads.
- Degradación elegante.
- Replicación de datos.
- Rate limiting.
- Health checks.
- Métricas, logs y trazas distribuidas.
- Despliegues canary/blue-green.
