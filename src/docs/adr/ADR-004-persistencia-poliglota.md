# ADR-004: Usar persistencia especializada por patrón de acceso

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

No todos los datos tienen las mismas necesidades: suscripciones requieren transacciones; búsqueda requiere full-text; audio requiere almacenamiento de objetos; recomendaciones requieren features y eventos.

## Decisión

Usar persistencia políglota de forma controlada:

- BD relacional: cuentas, suscripciones y datos transaccionales.
- Índice de búsqueda: artistas, álbumes, tracks y autocomplete.
- Object Storage: archivos de audio.
- Caché distribuida: sesiones, metadatos frecuentes.
- Event/Analytics Store: comportamiento y señales de recomendación.

## Consecuencia

Mejor ajuste técnico por caso de uso, a cambio de mayor complejidad y gobernanza de datos.
