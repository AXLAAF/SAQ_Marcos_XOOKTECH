---
id: ARQ-03
titulo: Modelo de Datos - Base de Datos PostgreSQL
version: "1.0"
estado: Activo
tipo: Arquitectura
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Axel Adolfo Morales Caro
referencias:
  - "01-Baseline/01-Propuesta_Recuperada.md"
  - PROC-04_Arquitectura_Sistema
  - REQ-06_Datos_Catalogo
tags:
  - arquitectura
  - base-de-datos
  - modelo-datos
---

# ARQ-03: Modelo de Datos

## 1. Esquema de Base de Datos

El sistema utiliza PostgreSQL como base de datos principal para almacenar el catalogo de marcos y las configuraciones de ordenes.

## 2. Tablas Principales

### 2.1 Tabla: marcos

Almacena la informacion de todos los marcos disponibles en el catalogo.

```sql
CREATE TABLE marcos (
    id SERIAL PRIMARY KEY,
    clave VARCHAR(50) UNIQUE NOT NULL,
    nombre VARCHAR(200),
    categoria VARCHAR(100),
    color VARCHAR(100),
    ancho DECIMAL(6,2) NOT NULL,
    alto DECIMAL(6,2) NOT NULL,
    precio DECIMAL(10,2),
    textura_path VARCHAR(500),
    modelo_3d_path VARCHAR(500),
    foto_perfil_path VARCHAR(500),
    es_doble BOOLEAN DEFAULT FALSE,
    activo BOOLEAN DEFAULT TRUE,
    fecha_creacion TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    fecha_actualizacion TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

| Campo | Tipo | Descripcion | Restricciones |
|-------|------|--------------|---------------|
| id | SERIAL | Identificador unico | PK, auto-increment |
| clave | VARCHAR(50) | Codigo unico del marco | UNIQUE, NOT NULL |
| nombre | VARCHAR(200) | Nombre comercial | - |
| categoria | VARCHAR(100) | Categoria (clasico, moderno, etc.) | - |
| color | VARCHAR(100) | Color predominante | - |
| ancho | DECIMAL(6,2) | Ancho en centimetros | NOT NULL |
| alto | DECIMAL(6,2) | Alto en centimetros | NOT NULL |
| precio | DECIMAL(10,2) | Precio en MXN | - |
| textura_path | VARCHAR(500) | Ruta a la imagen de textura | - |
| modelo_3d_path | VARCHAR(500) | Ruta al modelo 3D (GLTF/OBJ) | - |
| foto_perfil_path | VARCHAR(500) | Ruta a foto lateral del marco | - |
| es_doble | BOOLEAN | Indica si es marco doble | DEFAULT FALSE |
| activo | BOOLEAN | Marco disponible en catalogo | DEFAULT TRUE |

### 2.2 Tabla: maria_luisas

Almacena las Maria Luisas (marcos decorativos internos) disponibles.

```sql
CREATE TABLE maria_luisas (
    id SERIAL PRIMARY KEY,
    clave VARCHAR(50) UNIQUE NOT NULL,
    nombre VARCHAR(200),
    tipo VARCHAR(100),
    precio_adicional DECIMAL(10,2),
    textura_path VARCHAR(500),
    activo BOOLEAN DEFAULT TRUE
);
```

### 2.3 Tabla: tipos_vidrio

Almacena los tipos de vidrio disponibles para los marcos.

```sql
CREATE TABLE tipos_vidrio (
    id SERIAL PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    descripcion TEXT,
    precio_adicional DECIMAL(10,2),
    activo BOOLEAN DEFAULT TRUE
);
```

**Datos iniciales:**

| nombre | descripcion | precio_adicional |
|--------|-------------|------------------|
| Normal | Vidrio standard | $0 |
| Antirreflejo | Reduce reflejos y mejora visibilidad | $150 |
| Templado | Mas resistencia a impactos | $250 |

### 2.4 Tabla: ordenes

Almacena las ordenes generadas por los empleados.

```sql
CREATE TABLE ordenes (
    id SERIAL PRIMARY KEY,
    fecha_creacion TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    marco_id INTEGER REFERENCES marcos(id),
    maria_luisa_id INTEGER REFERENCES maria_luisas(id),
    tipo_vidrio_id INTEGER REFERENCES tipos_vidrio(id),
    ruta_imagen_cliente VARCHAR(500),
    precio_total DECIMAL(10,2),
    estado VARCHAR(50) DEFAULT 'pendiente',
    observaciones TEXT
);
```

### 2.5 Tabla: configuraciones

Almacena configuraciones del sistema.

```sql
CREATE TABLE configuraciones (
    clave VARCHAR(100) PRIMARY KEY,
    valor TEXT,
    descripcion VARCHAR(500),
    fecha_actualizacion TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## 3. Diagrama Entidad-Relacion (ER)

```
+-------------+       +----------------+       +-------------+
|   marcos    |<---->|    ordenes     |----> | tipos_vidrio|
+-------------+       +----------------+       +-------------+
| PK: id      |       | PK: id         |      | PK: id      |
| clave       |       | marco_id (FK)  |      | nombre      |
| nombre      |       | maria_luisa_id |      | precio      |
| categoria   |       | vidrio_id (FK) |      +-------------+
| color       |       | precio_total   |
| ancho       |       | estado         |
| alto        |       +----------------+
| precio      |              ^
| textura     |              |
| modelo_3d   |       +-------------------+
+-------------+       |  maria_luisas    |
                     +-------------------+
                     | PK: id            |
                     | clave             |
                     | nombre            |
                     | precio_adicional  |
                     +-------------------+
```

## 4. Indices

```sql
-- Indices para busqueda rapida en catalogo
CREATE INDEX idx_marcos_categoria ON marcos(categoria);
CREATE INDEX idx_marcos_color ON marcos(color);
CREATE INDEX idx_marcos_ancho ON marcos(ancho);
CREATE INDEX idx_marcos_clave ON marcos(clave);
CREATE INDEX idx_marcos_activo ON marcos(activo);

-- Indices para ordenes
CREATE INDEX idx_ordenes_fecha ON ordenes(fecha_creacion);
CREATE INDEX idx_ordenes_estado ON ordenes(estado);
```

## 5. Vistas

### 5.1 Vista: catalogo_marcos_activos

```sql
CREATE VIEW catalogo_marcos_activos AS
SELECT id, clave, nombre, categoria, color, ancho, alto, precio, es_doble
FROM marcos
WHERE activo = TRUE
ORDER BY categoria, nombre;
```

## 6. Procedimientos Almacenados

### 6.1 Obtener catalogo filtrado

```sql
CREATE OR REPLACE FUNCTION fn_catalogo_filtrado(
    p_categoria VARCHAR,
    p_color VARCHAR,
    p_ancho_min DECIMAL,
    p_ancho_max DECIMAL,
    p_es_doble BOOLEAN
)
RETURNS SETOF marcos AS $$
BEGIN
    RETURN QUERY
    SELECT m.*
    FROM marcos m
    WHERE m.activo = TRUE
      AND (p_categoria IS NULL OR m.categoria = p_categoria)
      AND (p_color IS NULL OR m.color = p_color)
      AND (p_ancho_min IS NULL OR m.ancho >= p_ancho_min)
      AND (p_ancho_max IS NULL OR m.ancho <= p_ancho_max)
      AND (p_es_doble IS NULL OR m.es_doble = p_es_doble)
    ORDER BY m.nombre;
END;
$$ LANGUAGE plpgsql;
```

## 7. Resumen de Entidades

| Entidad | Registros Estimados | Tamano Aproximado |
|---------|---------------------|-------------------|
| marcos | ~1,079 | 10-20 MB |
| maria_luisas | ~50 | 1-2 MB |
| tipos_vidrio | 3 | <1 MB |
| ordenes | Variable | 1-5 MB/año |

## 8. Referencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/01-Diagrama_Componentes]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/02-Flujo_Sistema]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-06_Datos_Catalogo]]
- [[PROC-04_Arquitectura_Sistema]]

---

*Documento creado: 2026-03-23 | Ultima actualizacion: 2026-03-23*
*Referencia: [[01-Baseline/Entrevista_Completada_Proyecto]] - Aproximadamente 1079 marcos en catalogo*