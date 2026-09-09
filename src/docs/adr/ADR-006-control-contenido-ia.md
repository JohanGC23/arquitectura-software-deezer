# ADR-006: Integrar clasificación de contenido generado por IA fuera del camino crítico

- **Estado:** Aceptado
- **Fecha:** 2026-09-09

## Contexto

Deezer ha comunicado públicamente políticas de detección/etiquetado de contenido generado por IA y exclusión de ese contenido de recomendaciones algorítmicas. Para el caso académico, esta capacidad debe modelarse sin aumentar la latencia del usuario.

## Decisión

Procesar el contenido en un pipeline de ingestión:

1. Recibir audio y metadatos.
2. Validar formato y derechos/metadatos.
3. Ejecutar clasificación IA/fraude.
4. Persistir etiqueta y score.
5. Publicar `content_classified`.
6. Indexar el contenido.
7. Aplicar reglas del recomendador basadas en la etiqueta.

## Razón

La clasificación es intensiva y no pertenece al camino crítico de reproducción. Separarla permite escalar el pipeline de manera independiente.

## Consecuencias

- Puede existir retraso entre ingestión y publicación.
- Se requiere versionar modelos y conservar trazabilidad del resultado.
- Debe existir proceso de re-clasificación cuando el modelo cambie.
