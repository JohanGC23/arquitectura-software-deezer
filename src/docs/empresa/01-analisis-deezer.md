# Análisis de la empresa — Deezer

## 1. Descripción general

Deezer es una empresa tecnológica enfocada en experiencias musicales digitales. La compañía fue fundada en París en 2007 y, de acuerdo con publicaciones oficiales de 2026, está disponible en más de 180 países.

Entre las capacidades públicas de su producto se encuentran:

- Streaming de música.
- Audio de alta calidad / HiFi.
- Recomendaciones y personalización.
- Funcionalidad **Flow** como experiencia personalizada.
- Playlists, favoritos y descubrimiento.
- Servicios y alianzas B2B mediante **Deezer for Business**.
- Medidas de transparencia frente a contenido generado por IA.

## 2. Problema de negocio estudiado

Una plataforma de streaming musical debe entregar contenido de manera continua a usuarios distribuidos geográficamente, manteniendo:

1. Catálogo grande y consultable.
2. Inicio de reproducción rápido.
3. Alta disponibilidad.
4. Personalización en tiempo casi real.
5. Gestión de cuentas y suscripciones.
6. Protección de derechos y contenido.
7. Capacidad de absorber picos de tráfico.
8. Trazabilidad y observabilidad.

## 3. Stakeholders

| Stakeholder | Interés principal |
|---|---|
| Oyentes | Reproducción rápida, estable y personalizada. |
| Artistas / sellos / distribuidores | Correcta entrega, atribución y monetización del contenido. |
| Equipo de producto | Evolución rápida de funcionalidades. |
| Operaciones / SRE | Disponibilidad, observabilidad y recuperación ante fallos. |
| Seguridad | Protección de cuentas, datos y pagos. |
| Negocio / marketing | Conversión, retención, engagement y campañas. |
| Socios B2B | Integración confiable y escalable. |
| Soporte al cliente | Diagnóstico rápido de incidencias. |

## 4. Requerimientos funcionales de alto nivel

- RF-01: Registrar e iniciar sesión.
- RF-02: Buscar canciones, álbumes y artistas.
- RF-03: Reproducir, pausar, avanzar y retroceder audio.
- RF-04: Crear y administrar playlists.
- RF-05: Marcar canciones, álbumes y artistas como favoritos.
- RF-06: Obtener recomendaciones personalizadas.
- RF-07: Administrar una suscripción.
- RF-08: Registrar historial y eventos de escucha.
- RF-09: Ingerir y procesar nuevo contenido musical.
- RF-10: Moderar o etiquetar contenido según reglas de la plataforma.
- RF-11: Exponer integraciones seguras para socios B2B.
- RF-12: Obtener métricas operativas y de producto.

## 5. Requerimientos no funcionales

- RNF-01: Alta disponibilidad del servicio de reproducción.
- RNF-02: Escalabilidad horizontal para millones de solicitudes.
- RNF-03: Baja latencia en búsqueda y navegación.
- RNF-04: Distribución global eficiente mediante CDN.
- RNF-05: Cifrado de datos en tránsito y en reposo.
- RNF-06: Protección de tokens, sesiones y operaciones de pago.
- RNF-07: Observabilidad con métricas, logs y trazas.
- RNF-08: Despliegues graduales y reversibles.
- RNF-09: Aislamiento de fallos entre dominios.
- RNF-10: Evolución independiente de componentes.

## 6. Restricciones asumidas para el caso académico

- Usuarios distribuidos globalmente.
- Tráfico con picos por lanzamientos, campañas y eventos.
- Archivos de audio de gran tamaño.
- Recomendaciones dependientes del historial.
- Integración con proveedores de pago y socios.
- Necesidad de mantener continuidad de reproducción aun cuando servicios secundarios fallen.

## 7. Alcance arquitectónico

El trabajo no intenta reconstruir la implementación interna de Deezer. Se diseña una **arquitectura de referencia inspirada en las necesidades visibles de una plataforma de streaming musical de escala global**.
