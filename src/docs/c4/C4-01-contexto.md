# C4 — Nivel 1: Diagrama de Contexto

> Modelo académico de referencia; no describe la arquitectura interna oficial de Deezer.

## Propósito

Mostrar las personas y sistemas externos que interactúan con la plataforma.

```mermaid
flowchart LR
    LISTENER[Oyente]
    ADMIN[Operaciones / Soporte]
    PARTNER[Socio B2B]
    RIGHTS[Sellos / Distribuidores]
    PAY[Proveedor de pagos]
    NOTIF[Proveedor de notificaciones]

    SYS[Plataforma de streaming musical\nCaso Deezer]

    LISTENER -->|Escucha, busca, crea playlists| SYS
    ADMIN -->|Opera, modera y da soporte| SYS
    PARTNER -->|Integra servicios musicales| SYS
    RIGHTS -->|Entrega catálogo y metadatos| SYS
    SYS -->|Cobros y renovaciones| PAY
    SYS -->|Email / push| NOTIF
```

## Actores

### Oyente
Consume música, administra biblioteca, playlists, preferencias y suscripción.

### Operaciones / Soporte
Supervisa incidencias, catálogo, fraude, cuentas y operación.

### Socio B2B
Integra capacidades musicales mediante contratos/API.

### Sellos / Distribuidores
Entregan metadatos y contenido con licencias.

## Sistemas externos

### Proveedor de pagos
Procesa pagos, validaciones y renovaciones.

### Proveedor de notificaciones
Entrega mensajes push, email u otros canales.

## Responsabilidad del sistema

Ofrecer una experiencia musical personalizada, segura, escalable y disponible, asegurando búsqueda, catálogo, reproducción, biblioteca, recomendaciones y suscripciones.
