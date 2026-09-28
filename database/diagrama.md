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

## Estructura general

```text
┌─────────────────┐
│     PLATOS      │
├─────────────────┤
│ _id             │
│ nombre          │
│ descripcion     │
│ precio          │
│ categoria       │
│ disponible      │
│ imagen_url      │
│ fecha_creacion  │
└────────┬────────┘
         │
         │ plato_id
         ▼
┌─────────────────────────┐
│        PEDIDOS          │
├─────────────────────────┤
│ _id                     │
│ items[]                 │
│   ├── plato_id          │
│   ├── nombre            │
│   ├── cantidad          │
│   ├── precio_unitario   │
│   └── observaciones     │
│ total                   │
│ tipo                    │
│ estado                  │
│ mesa                    │
│ mozo                    │
│ fecha_hora              │
│ delivery                │
└────────────┬────────────┘
             │
             │ pedido_id
             ▼
┌─────────────────────────┐
│         VENTAS          │
├─────────────────────────┤
│ _id                     │
│ pedido_id               │
│ fecha                   │
│ total                   │
│ metodo_pago              │
│ tipo                    │
└─────────────────────────┘
