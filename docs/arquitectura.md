# Arquitectura del proyecto — El Palacio del Morfi

## 1. Descripción

El sistema "El Palacio del Morfi" será desarrollado como una aplicación web para la gestión integral de un restaurante.

La solución estará compuesta por un frontend encargado de la interfaz de usuario, un backend encargado de la lógica de negocio y una base de datos documental para almacenar la información del sistema.

La arquitectura propuesta permite separar las responsabilidades de cada componente y facilitar el mantenimiento y la evolución del sistema.

---

## 2. Arquitectura seleccionada

Se propone una arquitectura de aplicación web en capas, separando principalmente:

- Capa de presentación (Frontend).
- Capa de lógica y servicios (Backend).
- Capa de persistencia de datos (Base de Datos).

El frontend se comunicará con el backend mediante una API HTTP. El backend procesará las solicitudes, aplicará las reglas de negocio y accederá a MongoDB mediante Mongoose.

### Esquema general

```text
                 USUARIOS
                    │
                    ▼
        ┌──────────────────────┐
        │       FRONTEND       │
        │     HTML / CSS / JS  │
        └──────────┬───────────┘
                   │
                HTTP / API
                   │
                   ▼
        ┌──────────────────────┐
        │       BACKEND        │
        │    Node.js/Express   │
        │                      │
        │  Lógica de negocio   │
        │  Rutas y servicios   │
        └──────────┬───────────┘
                   │
                Mongoose
                   │
                   ▼
        ┌──────────────────────┐
        │       MONGODB        │
        │     Base de datos    │
        └──────────────────────┘
