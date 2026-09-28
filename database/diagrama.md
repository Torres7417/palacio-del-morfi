# Diagrama de Base de Datos — El Palacio del Morfi

## Modelo documental MongoDB

El siguiente diagrama representa las principales colecciones y referencias del modelo de datos.

```mermaid
flowchart LR

    P[platos]

    PED[pedidos]

    V[ventas]

    P -->|plato_id| PED

    PED -->|pedido_id| V
