# Entrega — Actividad de Aplicación

## Empresa
**Deezer**

## Equipo
- Jeymi Johan Gomez Coaquira
- Frank Antoni Magallan Rojas
- Anderson Huamani Alarcon
- Jhon Antony Rios Ccarapa

## Evidencias solicitadas

### 1. Repositorio con estructura base
Cumplido:

- `/docs/adr`
- `/docs/c4`
- `/src`
- `README.md` con integrantes y roles

### 2. Análisis arquitectónico
Cumplido en `/docs/empresa`.

### 3. Modelo C4
Cumplido:

- Nivel 1: Contexto.
- Nivel 2: Contenedores.
- Nivel 3: Componentes del Playback Service.

### 4. Decisiones arquitectónicas
Se incluyen seis ADR:

1. Servicios por dominio.
2. Arquitectura dirigida por eventos.
3. CDN + Object Storage.
4. Persistencia políglota.
5. Observabilidad.
6. Clasificación de contenido generado por IA.

### 5. Atributos de calidad
Se incluyen disponibilidad, rendimiento, escalabilidad, seguridad, resiliencia, observabilidad y mantenibilidad, con escenarios medibles.

## Conclusión

La arquitectura propuesta separa los dominios principales de una plataforma de streaming musical, usa eventos para desacoplar tareas de alto volumen y CDN para el camino de distribución de audio. La propuesta prioriza que reproducción y navegación continúen disponibles aunque servicios secundarios se degraden.

El caso usa a Deezer como empresa de referencia por sus funcionalidades públicas, pero no pretende describir sistemas internos confidenciales o no publicados.
