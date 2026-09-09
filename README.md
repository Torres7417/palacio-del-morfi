# 🍽️ Proyecto "El Palacio del Morfi"

**Sistema de Gestión para Restaurante "El Palacio del Morfi"**

---

## 📋 Descripción del Proyecto

**El Palacio del Morfi** es un restaurante familiar que ofrece servicio de salón, take-away y delivery. Actualmente, todos los procesos se gestionan de manera manual con papeles y lapicera, lo que genera pérdida de comandas, errores de comunicación y falta de control en los pedidos.

Este proyecto consiste en el desarrollo de un **sistema web integral** que digitaliza los procesos clave del restaurante, mejorando la eficiencia, reduciendo errores y proporcionando **trazabilidad en tiempo real**.

---

## 🔍 Identificación de la Problemática

### Contexto

El restaurante opera con **13 mesas** (8 interiores y 5 exteriores), atendiendo aproximadamente:

- 15 pedidos diarios en salón
- 15 delivery
- 4 take-away

Con picos que pueden llegar a **40 pedidos** en días de alta demanda.

### Actores Involucrados

| Actor       | Cantidad                      | Responsabilidad                                      |
|-------------|-------------------------------|------------------------------------------------------|
| Mozos       | 2 (semana) / 2 (fin de semana)| Atención al cliente, toma de pedidos, servicio en mesa y atención de pedidos por WhatsApp |
| Cocineros   | 1 chef + 1 ayudante           | Preparación de platos, recepción de comandas         |
| Repartidor  | 1                             | Entrega de pedidos a domicilio                       |
| Encargado   | 1 (el chef / dueño)           | Administración, gestión del menú, control general    |

### Problemas Identificados

| Problema                          | Impacto                                              | Frecuencia    |
|-----------------------------------|------------------------------------------------------|---------------|
| Pérdida de comandas en papel      | Pedidos no entregados, clientes insatisfechos, pérdida de ingresos | Muy frecuente |
| Comandas mezcladas (salón y delivery) | Dificultad para encontrar pedidos específicos, confusión en cocina | Diario        |
| Errores en la comprensión de comandas | Platos mal preparados, retrabajo, desperdicio de insumos | Frecuente     |
| Registro manual de delivery en hoja | Información desordenada, difícil de consultar, sin seguimiento en tiempo real | Diario        |
| Falta de trazabilidad y control   | No hay historial de pedidos, ni estadísticas de ventas | Constante     |

### Impacto Medible

- **Tiempo perdido**: Reescribiendo menús, buscando comandas perdidas, corrigiendo errores.
- **Ingresos perdidos**: Por pedidos que no se entregan o se entregan mal.
- **Insatisfacción del cliente**: Tiempos de espera prolongados, errores en los pedidos.

---

## 💡 Propuesta de Solución y Valor Agregado

No se trata simplemente de "digitalizar" los procesos actuales, sino de **transformarlos**:

| Proceso Actual                  | Solución Digital                                      | Valor Agregado                          |
|---------------------------------|-------------------------------------------------------|-----------------------------------------|
| Menú físico reescrito a diario  | Menú digital visible desde cualquier dispositivo      | Actualización instantánea, sin reescritura manual |
| Comanda en papel que se extravía| Comanda digital generada desde el celular del mozo    | Trazabilidad, sin pérdidas, histórico de pedidos |
| Pedidos de delivery en hoja con foto | Registro digital con estado, seguimiento y notificaciones | Control en tiempo real, historial de clientes |
| Control de caja manual          | Registro automático de ventas y métodos de pago       | Estadísticas y cierre de caja automático |

### Valor Agregado Real

1. **Reducción de errores**: La comanda digital elimina la mala interpretación de la letra manuscrita.
2. **Trazabilidad**: Cada pedido queda registrado con fecha, hora, mesa/mozo y estado.
3. **Control de delivery**: Seguimiento en tiempo real del estado de cada pedido.
4. **Estadísticas**: Ventas por día, plato más vendido, métodos de pago, ingresos totales.
5. **Control de caja**: Registro automático de ingresos para cierre diario.

---

## 🎯 Alcance del Proyecto

### MVP (Mínimo Producto Viable) - Funcionalidades Obligatorias

| Módulo              | Funcionalidad                                                                 | Prioridad |
|---------------------|-------------------------------------------------------------------------------|-----------|
| Menú Digital        | Visualización de platos del día (con imágenes, precios, descripción)          | ⭐⭐⭐     |
| Toma de Pedidos (Mozo) | Mozos toman pedido desde su celular, seleccionando platos y mesa           | ⭐⭐⭐     |
| Panel de Cocina     | Visualización de pedidos entrantes (salón y delivery) con estado              | ⭐⭐⭐     |
| Gestión de Delivery | Registro de pedidos con datos de envío, método de pago, seguimiento           | ⭐⭐⭐     |
| Registro de Ventas  | Registro automático de cada venta para control de caja                        | ⭐⭐       |

### Nice to Have (Funcionalidades Deseables)

| Módulo         | Funcionalidad                                              |
|----------------|------------------------------------------------------------|
| Autenticación  | Roles diferenciados (mozo, cocina, admin, delivery)        |
| Estadísticas   | Reportes de ventas por día, plato más vendido, ingresos totales |
| Cierre de Caja | Resumen automático de ventas del día                       |
| Notificaciones | Alertas cuando un pedido cambia de estado                  |

### Fuera de Alcance

- Aplicación móvil nativa (se usará web responsive)
- Sistema de facturación electrónica (no se emite comprobante actualmente)
- Integración con pasarelas de pago (los pagos son manuales)

---

## 🛠️ Stack Tecnológico

| Capa               | Tecnología                          | Justificación                                      |
|--------------------|-------------------------------------|----------------------------------------------------|
| Frontend           | HTML5 + CSS3 + JavaScript           | Tecnologías nativas del navegador, sin dependencias pesadas |
| Frontend Framework | React (opcional) o Vanilla JS       | Si se opta por React, se aprende el framework más demandado |
| Estilos            | Tailwind CSS o CSS puro             | Diseño responsivo y rápido de implementar          |
| Backend            | Node.js + Express                   | Unifica lenguaje con frontend, fácil de desplegar, amplio ecosistema |
| Base de Datos      | MongoDB                             | Datos anidados naturalmente (pedidos con items), flexible, fácil de escalar |
| ODM                | Mongoose                            | Abstracción sobre MongoDB, definición de esquemas y validaciones |
| Despliegue         | Render (Backend) + Vercel (Frontend) + MongoDB Atlas (BD) | Todos con capa gratuita, fácil integración con GitHub |

### Justificación del Stack

| Decisión        | Justificación                                                                 |
|----------------|-------------------------------------------------------------------------------|
| Node.js        | Permite usar JavaScript en backend, reduciendo el cambio de contexto. El ecosistema npm ofrece herramientas para todo tipo de necesidades. |
| MongoDB        | La estructura de un pedido con items anidados se representa naturalmente como un documento JSON. No se necesitan JOINs complejos. |
| Mongoose       | Simplifica la conexión y el modelado, ofreciendo validaciones y esquemas que garantizan la integridad de los datos. |
| Render + Vercel| Despliegue sencillo con integración a GitHub. Capas gratuitas suficientes para el MVP. |

---

## 🗄️ Modelo de Datos (Esquema MongoDB)

### Colección: `platos`

```js
{
  _id: ObjectId,
  nombre: String,
  descripcion: String,
  precio: Number,
  categoria: String,   // "principal", "entrada", "bebida", "postre"
  disponible: Boolean,
  imagen_url: String,
  fecha_creacion: Date
}
```

### Colección: `pedidos`

```js
{
  _id: ObjectId,
  items: [
    {
      plato_id: ObjectId,
      nombre: String,
      cantidad: Number,
      precio_unitario: Number,
      observaciones: String   // "sin cebolla", "bien cocido"
    }
  ],
  total: Number,
  tipo: String,   // "salon", "delivery", "para_llevar"
  estado: String,   // "pendiente", "en_cocina", "listo", "entregado"
  mesa: Number,   // solo para tipo "salon"
  mozo: String,   // nombre del mozo que tomó el pedido
  fecha_hora: Date,
  // Solo para delivery
  delivery: {
    cliente_nombre: String,
    telefono: String,
    direccion: String,
    referencias: String,
    metodo_pago: String,   // "efectivo", "transferencia"
    repartidor: String
  }
}
```

### Colección: `ventas` (para control de caja)

```js
{
  _id: ObjectId,
  pedido_id: ObjectId,
  fecha: Date,
  total: Number,
  metodo_pago: String,
  tipo: String   // "salon", "delivery", "para_llevar"
}
```

---

## 📅 Plan de Trabajo

| Semana   | Tareas                                                      | Entregable                  |
|----------|-------------------------------------------------------------|-----------------------------|
| Semana 1 | Relevamiento de requisitos, entrevista con el dueño, definición de alcance | Documento de requisitos     |
| Semana 2 | Diseño de base de datos, creación de repositorio, definición de arquitectura | Esquema BD + Repositorio    |
| Semana 3 | **ENTREGA 1** - README completo, stack definido, plan de trabajo | README.md                   |
| Semana 4 | Desarrollo Frontend: Menú Digital (visualización de platos) | Código Frontend             |
| Semana 5 | Desarrollo Frontend: Panel de Mozo (toma de pedidos)        | Código Frontend             |
| Semana 6 | Desarrollo Backend: API de platos y pedidos                 | API REST                    |
| Semana 7 | **ENTREGA 2** - Esquema BD + Módulos funcionando            | Código + Documentación      |
| Semana 8 | Desarrollo: Panel de Cocina y Gestión de Delivery           | Código                      |
| Semana 9 | Integración Frontend-Backend, pruebas                       | Sistema integrado           |
| Semana 10| Pruebas con usuarios reales (el restaurante), ajustes       | Feedback                    |
| Semana 11| Despliegue en la nube (Render + Vercel + MongoDB Atlas)     | Sistema online              |
| Semana 12| Pruebas en producción, corrección de errores                | Sistema funcionando         |
| Semana 13| Redacción de informe final                                  | Informe PDF                 |
| Semana 14| **ENTREGA FINAL** - Video explicativo en inglés             | Repositorio completo + Video|

---

## ✅ Criterios de Éxito

| Indicador            | Métrica                          | Estado Actual     | Objetivo              |
|----------------------|----------------------------------|-------------------|-----------------------|
| Pérdida de comandas  | Cantidad por semana              | Muy frecuente     | Cero pérdidas         |
| Errores en pedidos   | Cantidad por día                 | Frecuente         | Reducir a 1 o menos   |
| Tiempo de atención   | Minutos desde pedido hasta entrega | Variable, sin control | Reducir un 20%     |
| Control de delivery  | Seguimiento de pedidos           | Manual (hoja)     | 100% digital          |
| Registro de ventas   | Cierre de caja                   | Manual            | Automatizado          |

---

## 🚀 Despliegue

| Servicio       | Propósito                      | Plan            |
|----------------|--------------------------------|-----------------|
| MongoDB Atlas  | Base de datos en la nube       | Capa gratuita M0|
| Render         | Backend (Node.js + Express)    | Capa gratuita   |
| Vercel         | Frontend (HTML/CSS/JS)         | Capa gratuita   |

---

## 👥 Equipo

| Integrante              | Rol |
|-------------------------|-----|
| Torres, Jorge David     |     |
| Iañez, Sol Ludmila      |     |
| Pighin, Bruno Joaquín   |     |

---

## 🧰 Tecnologías Utilizadas

- **Frontend**: HTML5, CSS3, JavaScript (React opcional)
- **Backend**: Node.js, Express
- **Base de Datos**: MongoDB, Mongoose
- **Despliegue**: MongoDB Atlas, Render, Vercel
- **Control de Versiones**: Git + GitHub

---

## 📝 Notas Adicionales

- El sistema está diseñado para ser **responsivo** y funcionar en dispositivos móviles (celulares de mozos y cocina).
- Se prioriza la **simplicidad y usabilidad** para facilitar la adopción por parte del personal.
- El proyecto es **100% aplicable** a un entorno real y tiene posibilidades de transferencia al medio.

---

## 📄 Licencia

Este proyecto es de carácter académico / educativo.
