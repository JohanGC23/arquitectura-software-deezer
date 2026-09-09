# ADR-001: Separar la solución por dominios en servicios independientes

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

La plataforma debe escalar funciones con perfiles muy distintos: reproducción, búsqueda, recomendaciones, catálogo, suscripciones e ingestión.

## Decisión

Adoptar servicios independientes alineados a dominios de negocio, evitando un microservicio por cada entidad.

Dominios iniciales:

- Identidad.
- Catálogo.
- Búsqueda.
- Biblioteca/playlists.
- Playback.
- Recomendaciones.
- Suscripciones.
- Ingestión.
- Analítica.

## Consecuencias positivas

- Escalamiento por dominio.
- Despliegue independiente.
- Aislamiento de fallos.
- Equipos con ownership claro.

## Consecuencias negativas

- Mayor complejidad de operación.
- Trazas distribuidas.
- Consistencia eventual.
- Necesidad de contratos y versionado.

## Alternativa descartada

Monolito único: más simple inicialmente, pero menos apropiado para el objetivo académico de gran escala y aislamiento.
