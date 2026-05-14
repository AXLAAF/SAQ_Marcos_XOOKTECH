---
id: ARQ-02
titulo: Flujo del Sistema - Visualizador de Marcos
version: "1.0"
estado: Activo
tipo: Arquitectura
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Samuel Blanco
referencias:
  - "01-Baseline/01-Propuesta_Recuperada.md"
  - PROC-04_Arquitectura_Sistema
tags:
  - arquitectura
  - flujo
  - procesos
---

# ARQ-02: Flujo del Sistema

## 1. Flujo Principal del Sistema

### 1.1 Flujo de Uso Normal (Happy Path)

```
+----------+     +----------+     +-------------+     +----------------+     +---------+
| Cliente  |     | Empleado |     |   Sistema   |     |   Previsual.   |     | Orden   |
| llega    |     | abre app |     | carga cat.  |     |  3D rendered   |     | gener.  |
+----------+     +----------+     +-------------+     +----------------+     +---------+
     |               |                |                    |                   |
     v               v                v                    v                   v
1. El cliente   2. Empleado    3. Sistema       4. Sistema        5. Empleado
llega a la      abre la app   carga el         renderiza el     genera la orden
tienda con      web en la     catalogo de     marco sobre       con la config.
su foto         computadora   marcos desde    la foto del       seleccionada
                               la BD           cliente
```

### 1.2 Descripcion Paso a Paso

| Paso | Actor | Accion | Sistema Responde |
|------|-------|--------|------------------|
| 1 | Cliente | Llega a la tienda con su foto | - |
| 2 | Empleado | Abre la aplicacion web en la computadora de la tienda | Muestra la interfaz principal |
| 3 | Cliente/Empleado | El cliente sube su foto (desde archivo o connectando el celular) | Sistema valida y muestra la foto en el canvas |
| 4 | Empleado | Consulta el catalogo de marcos y filtros disponibles | Sistema muestra grid de marcos |
| 5 | Cliente | Selecciona un marco del catalogo | Sistema carga la textura y modelo 3D del marco |
| 6 | Sistema | Renderiza la previsualizacion 3D | Muestra la foto con el marco seleccionado |
| 7 | Cliente | Repite pasos 4-6 hasta encontrar el marco deseado | - |
| 8 | Empleado | Genera la orden con la configuracion seleccionada | Sistema crea registro de orden |

## 2. Flujo de Carga de Imagen

```
+---------------------+      +------------------+      +-------------------+
| Input: Archivo      |      | Validacion       |      | Procesamiento     |
| (JPG, PNG, WebP)    |----->| (tipo, tamano)   |----->| (resize, compress)|
+---------------------+      +------------------+      +-------------------+
                                   |                              |
                                   v                              v
                            +-------------+              +-----------------+
                            | Error:      |              | Output: Imagen  |
                            | Formato     |              | lista para      |
                            | invalido    |              | previsualizacion|
                            +-------------+              +-----------------+
```

## 3. Flujo de Previsualizacion 3D

```
+-------------------+     +------------------+     +-------------------+
| Datos:            |     | Generacion       |     | Renderizado       |
| - Imagen cliente |----->| Modelo 3D        |----->| WebGL             |
| - Textura marco   |     | (Three.js)       |     | (Canvas HTML)     |
| - Modelo 3D marco |     +------------------+     +-------------------+
+-------------------+                                       |
    +--------------------------------------------------------+
    v
+----------------------------+
| Resultado:                 |
| Previsualizacion completa  |
| del marco sobre la foto    |
+----------------------------+
```

## 4. Flujo de Catalogo

```
+--------------------+      +--------------------+      +------------------+
| Solicitud          |      | Consulta           |      | Respuesta        |
| de marcos         |----->| a PostgreSQL       |----->| (JSON con datos) |
+--------------------+      +--------------------+      +------------------+
                                                           |
                                                           v
                                                    +----------------+
                                                    | Renderizado    |
                                                    | UI (Grid)      |
                                                    +----------------+
```

### 4.1 Flujo de Filtrado

```
Usuario selecciona --> Sistema ejecuta --> BD retorna --> Sistema filtra --> UI actualiza
filtros (color,     query con        marcos           resultados        grid de marcos
ancho, categoria)   parametros       matching          matching          filtrados
```

## 5. Flujo de Generacion de Modelos 3D (Herramienta Python)

```
+---------------------+      +------------------+      +-------------------+
| Input:              |      | Procesamiento    |      | Output:           |
| - Foto de perfil    |----->| (OpenCV,         |----->| Modelo 3D         |
| - Textura 2D        |     |  trimesh)        |     | (GLTF/OBJ)        |
+---------------------+      +------------------+      +-------------------+
                                    |
                                    v
                             +------------------+
                             | Deteccion de     |
                             | ancho (opcional) |
                             +------------------+
```

## 6. Diagramas de Secuencia

### 6.1 Secuencia: Seleccionar Marco

```
Actor          Sistema           Base de Datos
  |                |                    |
  | Solicita catalogo |                  |
  |---------------> |                    |
  |                 | SELECT * FROM...   |
  |                 |------------------> |
  |                 |<-------------------|
  |<- Muestra catalogo |                  |
  |                |                    |
  | Selecciona marco  |                  |
  |---------------> |                    |
  |                 | SELECT textura...  |
  |                 |------------------> |
  |                 |<-------------------|
  |<- Renderiza 3D   |                  |
```

### 6.2 Secuencia: Generar Orden

```
Actor          Sistema           Base de Datos
  |                |                    |
  | Confirma seleccion |                  |
  |---------------> |                    |
  |                 | INSERT orden...    |
  |                 |------------------> |
  |                 |<-------------------|
  |<- Confirmacion    |                  |
```

## 7. Estados del Sistema

| Estado | Descripcion | Transiciones |
|--------|-------------|--------------|
| **Inicializando** | Carga de recursos iniciales | -> Listo |
| **Listo** | Sistema preparado para usar | -> Procesando |
| **Procesando** | Ejecutando operacion (carga, render) | -> Listo, -> Error |
| **Error** | Ha ocurrido un problema | -> Listo (recuperable) |

## 8. Referencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/01-Diagrama_Componentes]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/03-Modelo_Datos]]
- [[PROC-04_Arquitectura_Sistema]]

---

*Documento creado: 2026-03-23 | Ultima actualizacion: 2026-03-23*
*Referencia: [[01-Baseline/Entrevista_Completada_Proyecto]] - Seccion F.1 Flujo tipico de un cliente*