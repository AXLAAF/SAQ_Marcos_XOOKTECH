---
id: ARQ-01
titulo: Diagrama de Componentes del Sistema
version: "1.0"
estado: Activo
tipo: Arquitectura
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Axel Adolfo Morales Caro
referencias:
  - "01-Baseline/01-Propuesta_Recuperada.md"
  - PROC-04_Arquitectura_Sistema
tags:
  - arquitectura
  - componentes
  - sistema
---
# ARQ-01: Diagrama de Componentes del Sistema

## 1. Vista General de la Arquitectura

* EL modulo 3d esta del lado del cliente, el cliente hace el render 3d no el backend
* 

```
+--------------------------------------------------------------------------+
|                     SISTEMA VISUALIZADOR DE MARCOS                        |
+----------------------------+---------------------------------------------+
|       CLIENTE (FrontEnd)   |           SERVIDOR (BackEnd)                |
|                            |                                             |
|  +---------------------+  |  +-----------------+  +------------------+  |
|  | Interfaz de Usuario |  | |   API REST      |  |   Base de Datos  |  |
|  | (HTML/Bootstrap/JS) |  | |   (Node.js)     |  |   (PostgreSQL)   |  |
|  +----------+----------+  |  +--------+--------+  +--------+---------+  |
|             |               |         |               |        |          |
|  +----------v----------+    |    +----v-------+    +---v--------v---+     |
|  | Gestor de Carga    |    |    | Rutas API  |    |   Catalogo     |     |
|  | de Imagenes        |    |    +------------+    |   Marcos       |     |
|  +----------+----------+    |                      +-----------------+     |
|             |                    +------------------+                    |
|  +----------v----------+        | | Modulo 3D      |                    |
|  | Motor de            |        | | (Three.js)    |                    |
|  | Previsualizacion 3D |        | +---------------+                    |
|  +---------------------+        +-----------------------------------------+
|                                                                         |
+--------------------------------+----------------------------------------+
                                 |
                    +------------v-------------+
                    | HERRAMIENTAS AUXILIARES  |
                    +---------------------------+
                    | +----------------------+  |
                    | | Programa Python     |  |
                    | | - Deteccion ancho   |  |
                    | | - Gen. Modelos 3D   |  |
                    | +----------------------+  |
                    +---------------------------+
```

## 2. Componentes Principales

### 2.1 Capa de Presentacion (Frontend)

| Componente                             | Descripcion                                  | Tecnologia               |
| -------------------------------------- | -------------------------------------------- | ------------------------ |
| **Interfaz de Usuario**          | Pagina web responsive para uso en tienda     | HTML5, Bootstrap 5, CSS3 |
| **Gestor de Carga de Imagenes**  | Componente para subir fotos de clientes      | JavaScript, File API     |
| **Motor de Previsualizacion 3D** | Renderiza el marco sobre la foto del cliente | Three.js, WebGL          |
| **Catalogo de Marcos**           | Visualizacion grid de marcos con filtros     | JavaScript, CSS Grid     |

### 2.2 Capa de Logica de Negocio (Backend)

| Componente                       | Descripcion                            | Tecnologia       |
| -------------------------------- | -------------------------------------- | ---------------- |
| **API REST**               | Endpoints para operaciones del sistema | Node.js, Express |
| **Gestor de Sesiones**     | Manejo de estado del usuario           | express-session  |
| **Gestor de Catalogo**     | CRUD de marcos y propiedades           | Node.js, pg      |
| **Procesador de Imagenes** | Resize, compression de fotos           | sharp (Node.js)  |

### 2.3 Capa de Datos

| Componente                   | Descripcion                                  | Tecnologia        |
| ---------------------------- | -------------------------------------------- | ----------------- |
| **Base de Datos**      | Almacenamiento de catalogo y configuraciones | PostgreSQL        |
| **Catalogo de Marcos** | Tabla principal con especificaciones         | PostgreSQL        |
| **Imagenes/Texturas**  | Almacenamiento de fotos de marcos            | File system (VPS) |

### 2.4 Herramientas Auxiliares

| Componente                        | Descripcion                                      | Tecnologia      |
| --------------------------------- | ------------------------------------------------ | --------------- |
| **Detector de Ancho**       | Analiza fotos de marcos para obtener dimensiones | Python, OpenCV  |
| **Generador de Modelos 3D** | Crea modelos 3D a partir de texturas 2D          | Python, trimesh |

## 3. Comunicacion entre Componentes

### 3.1 Flujo de Datos

```
[Cliente] <--HTTP--> [API REST] <--SQL--> [PostgreSQL]
                            |
                            v
                     [Archivo System]
```

### 3.2 APIs y Puertos

| Servicio    | Puerto | Protocolo  | Descripcion       |
| ----------- | ------ | ---------- | ----------------- |
| Frontend    | 80/443 | HTTP/HTTPS | Servido por Nginx |
| Backend API | 3000   | HTTP       | Node.js Express   |
| PostgreSQL  | 5432   | TCP/IP     | Base de datos     |
| SSH         | 22     | SSH        | Administracion    |

## 4. Diagrama de Despliegue

```
+-------------------+       +-------------------+
|   Cliente (PC     |       |   Cliente (PC    |
|   de la tienda)  |       |   del empleado)  |
+--------+----------+       +--------+----------+
         | HTTP/HTTPS              |
         v                         v
    +-------------------------------+
    |      VPS (Servidor)           |
    |  +----------+  +----------+  |
    |  | Nginx    |  | Node.js  |  |
    |  | (Front)  |  | (API)    |  |
    |  +----------+  +----------+  |
    |        |            |        |
    |  +-----v----------+ |        |
    |  | PostgreSQL    | |        |
    |  | (Datos)       | |        |
    |  +---------------+ |        |
    +---------------------+--------+
```

## 5. Dependencias Externas

| Dependencia | Version | Uso                     |
| ----------- | ------- | ----------------------- |
| Node.js     | 18.x+   | Runtime del backend     |
| PostgreSQL  | 14.x    | Base de datos           |
| Three.js    | 0.160+  | Renderizado 3D          |
| Bootstrap   | 5.3     | Framework CSS           |
| Python      | 3.10+   | Herramientas auxiliares |

## 6. Referencias

- [[PROC-04_Arquitectura_Sistema]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/03-Modelo_Datos]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/04-Modulos_Python]]

---

*Documento creado: 2026-03-23 | Ultima actualizacion: 2026-03-23*
*Referencia: [[01-Propuesta_Recuperada]] - Seccion 3.1 Tecnologias Acordadas*
