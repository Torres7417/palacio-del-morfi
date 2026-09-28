# Esquema de Base de Datos — El Palacio del Morfi

## 1. Tipo de base de datos

El proyecto utilizará una base de datos documental:

**MongoDB**

El modelo documental permite representar los pedidos junto con sus diferentes ítems dentro de un mismo documento.

---

# 2. Colección `platos`

La colección `platos` almacena la información correspondiente a los productos disponibles en el menú.

| Campo | Tipo | Obligatorio | Descripción |
|---|---|---|---|
| `_id` | ObjectId | Sí | Identificador único del plato |
| `nombre` | String | Sí | Nombre del plato |
| `descripcion` | String | Sí | Descripción del plato |
| `precio` | Number | Sí | Precio del plato |
| `categoria` | String | Sí | Categoría del plato |
| `disponible` | Boolean | Sí | Indica si el plato está disponible |
| `imagen_url` | String | No | URL de la imagen del plato |
| `fecha_creacion` | Date | Sí | Fecha de creación del registro |

### Categorías previstas

- principal
- entrada
- bebida
- postre

### Ejemplo conceptual

```text
platos
│
├── _id
├── nombre
├── descripcion
├── precio
├── categoria
├── disponible
├── imagen_url
└── fecha_creacion
