# Base de Datos — El Palacio del Morfi

## 1. Descripción

El sistema "El Palacio del Morfi" utilizará MongoDB como sistema de gestión de base de datos.

Se utilizará un modelo documental debido a que los pedidos contienen información anidada correspondiente a los platos solicitados y sus cantidades, observaciones y precios.

La base de datos será utilizada para almacenar la información correspondiente al menú, los pedidos y las ventas del restaurante.

## 2. Colecciones

La base de datos estará compuesta inicialmente por las siguientes colecciones:

- `platos`
- `pedidos`
- `ventas`

## 3. Colección `platos`

Almacena la información de los platos disponibles en el menú digital.

Campos principales:

- `_id`
- `nombre`
- `descripcion`
- `precio`
- `categoria`
- `disponible`
- `imagen_url`
- `fecha_creacion`

## 4. Colección `pedidos`

Almacena los pedidos realizados en el restaurante.

Cada pedido contiene una lista de productos solicitados y la información necesaria para gestionar su preparación, entrega y seguimiento.

Campos principales:

- `_id`
- `items`
- `total`
- `tipo`
- `estado`
- `mesa`
- `mozo`
- `fecha_hora`
- `delivery`

## 5. Colección `ventas`

Almacena la información de las ventas asociadas a los pedidos.

Campos principales:

- `_id`
- `pedido_id`
- `fecha`
- `total`
- `metodo_pago`
- `tipo`

## 6. Relaciones entre colecciones

MongoDB utiliza un modelo documental, por lo que no se utilizan claves foráneas de la misma manera que en una base de datos relacional.

Las principales referencias entre documentos serán:

- `pedidos.items.plato_id` referencia a un documento de la colección `platos`.
- `ventas.pedido_id` referencia a un documento de la colección `pedidos`.

## 7. Índices principales

Se prevén índices para facilitar las consultas más frecuentes del sistema:

- Índice sobre `platos.categoria`.
- Índice sobre `platos.disponible`.
- Índice sobre `pedidos.estado`.
- Índice sobre `pedidos.tipo`.
- Índice sobre `pedidos.fecha_hora`.
- Índice sobre `ventas.fecha`.

Los índices podrán ajustarse durante la etapa de implementación según las consultas reales del sistema.

## 8. Tecnología

- Sistema de base de datos: MongoDB
- ODM previsto: Mongoose
- Servicio de base de datos en la nube: MongoDB Atlas

## 9. Alcance

El presente diseño corresponde a la etapa de análisis y diseño del proyecto.

La implementación de la base de datos se realizará durante la etapa posterior, una vez aprobada la presente entrega por el tutor.
