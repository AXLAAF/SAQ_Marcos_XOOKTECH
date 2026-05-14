---
id: ARQ-04
titulo: Modulos Python - Herramientas Auxiliares
version: "1.0"
estado: Activo
tipo: Arquitectura
fecha_creacion: 2026-03-23
ultima_revision: 2026-03-23
responsable: Axel Adolfo Morales Caro
referencias:
  - "01-Baseline/01-Propuesta_Recuperada.md"
  - PROC-04_Arquitectura_Sistema
  - REQ-03_Generacion_Marcos_3D
tags:
  - arquitectura
  - python
  - herramientas
---

# ARQ-04: Modulos Python

## 1. Descripcion General

El proyecto utiliza programas en Python como herramientas auxiliares para el procesamiento de imagenes y generacion de modelos 3D. Estos modulos se ejecutan de manera independiente al sistema principal y alimentan el catalogo de marcos.

## 2. Modulos Principales

### 2.1 Modulo: detector_ancho.py

**Proposito:** Detectar automaticamente el ancho de un marco a partir de una fotografia de perfil.

```python
# detector_ancho.py
# Dependencias: opencv-python, numpy, scipy
```

**Funcionalidad:**

- Recibe una imagen lateral del marco
- Detecta los bordes del marco usando procesamiento de imagen
- Calcula el ancho en centimetros usando referencia conocida
- Genera un reporte con las dimensiones detectadas

**Uso:**
```bash
python detector_ancho.py --input foto_perfil.jpg --output dimensiones.json
```

**Algoritmo:**
1. Cargar imagen y convertir a escala de grises
2. Aplicar desenfoque gaussiano para reducir ruido
3. Detectar bordes con algoritmo Canny
4. Encontrar contornos y filtrar por area
5. Calcular dimensiones usando regla de referencia

### 2.2 Modulo: generador_3d.py

**Proposito:** Generar modelos 3D a partir de texturas 2D escaneadas.

```python
# generador_3d.py
# Dependencias: trimesh, numpy, PIL, scipy
```

**Funcionalidad:**

- Recibe una imagen de textura del marco
- Recibe las dimensiones (ancho, alto) del marco
- Genera una malla 3D con la forma del marco
- Aplica la textura sobre la malla
- Exporta en formato GLTF/OBJ para Three.js

**Uso:**
```bash
python generador_3d.py --textura textura_marco.jpg --ancho 50 --alto 70 --output marco.glb
```

**Algoritmo:**
1. Cargar textura y dimensiones
2. Crear vertices para la forma del marco (rectangular con grosor)
3. Crear caras (triangulos) para la malla
4. Asignar coordenadas UV para el mapeo de textura
5. Exportar a formato GLTF

### 2.3 Modulo: procesador_catalogo.py

**Proposito:** Procesar batch de imagenes del catalogo para generar texturas optimizadas.

```python
# procesador_catalogo.py
# Dependencias: Pillow, opencv-python
```

**Funcionalidad:**

- Recibe un directorio con imagenes crudas de marcos
- Redimensiona a tamano estandar (1024x1024)
- Comprime y optimiza para web
- Renombra segun convencion de claves
- Genera thumbnails para preview

**Uso:**
```bash
python procesador_catalogo.py --input ./imagenes_raw --output ./imagenes_procesadas
```

### 2.4 Modulo: escaner_marcos.py

**Proposito:** Automatizar el escaneo de marcos en bodega.

```python
# escaner_marcos.py
# Dependencias: opencv-python, numpy
```

**Funcionalidad:**

- Recibe imagen de marco escaneado
- Detecta automaticamente el marco en la imagen
- Recorta y corrige perspective
- Prepara para procesamiento adicional

**Uso:**
```bash
python escaner_marcos.py --input marco_001.jpg --output marco_001_recortado.jpg
```

## 3. Estructura de Archivos

```
procesamiento/
├── detector_ancho.py
├── generador_3d.py
├── procesador_catalogo.py
├── escaner_marcos.py
├── requirements.txt
├── config.py
├── utils/
│   ├── __init__.py
│   ├── image_utils.py
│   ├── mesh_utils.py
│   └── io_utils.py
└── data/
    ├── raw/           # Imagenes sin procesar
    ├── processed/    # Imagenes procesadas
    └── models/       # Modelos 3D generados
```

## 4. Dependencias (requirements.txt)

```
opencv-python==4.8.1
numpy==1.24.3
Pillow==10.0.1
trimesh==3.23.5
scipy==1.11.2
```

## 5. Flujo de Trabajo

```
+----------+     +----------------+     +---------------+     +-------------+
| Escaneo  |     | Procesamiento  |     | Generacion    |     | Catalogo    |
| de fotos |---->| de imagenes    |---->| de modelos 3D |---->| PostgreSQL  |
+----------+     +----------------+     +---------------+     +-------------+
                        |                      |
                        v                      v
               detector_ancho.py       generador_3d.py
               procesador_catalogo.py
```

### 5.1 Proceso de Escaneo (~5 semanas)

1. Semanas 1-5: Escaneo de ~200 marcos/semana
2. Total: ~1,000 marcos aproximadamente

**Detalle:**
- Fotos de perfil: Laterales del marco para detector de ancho
- Fotos de textura: Frentes del marco para renderizado 3D

## 6. Configuracion (config.py)

```python
# config.py

# Rutas
RAW_DATA_PATH = "./data/raw"
PROCESSED_PATH = "./data/processed"
MODELS_PATH = "./data/models"

# Tamano de imagenes
TEXTURE_SIZE = (1024, 1024)
THUMBNAIL_SIZE = (256, 256)

# Formato de salida
MODEL_FORMAT = "glb"  # GLTF binary

# Parametros de deteccion
EDGE_LOW_THRESHOLD = 50
EDGE_HIGH_THRESHOLD = 150

# Parametros de modelo 3D
FRAME_THICKNESS = 3.0  # cm
```

## 7. Integracion con el Sistema Principal

Los modulos Python generan salida que es consumida por el sistema principal:

| Output Python | Consumido por |
|---------------|----------------|
| Texturas optimizadas | Frontend (Three.js) |
| Modelos 3D (.glb) | Frontend (Three.js) |
| Dimensiones (JSON) | Base de datos PostgreSQL |

## 8. Comandos de Ejecucion

```bash
# Procesar todo el catalogo
python -m pipeline.procesar_todo --input ./fotos --db postgres://user:pass@host/db

# Solo generar modelos 3D
python generador_3d.py --batch ./texturas --output ./modelos

# Solo detectar anchos
python detector_ancho.py --batch ./fotos_perfil --output ./dimensiones.json
```

## 9. Referencias

- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/01-Diagrama_Componentes]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/02-Flujo_Sistema]]
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-03_Generacion_Marcos_3D]]
- [[PROC-04_Arquitectura_Sistema]]

---

*Documento creado: 2026-03-23 | Ultima actualizacion: 2026-03-23*
*Referencia: [[01-Propuesta_Recuperada]] - Programa Python para procesamiento de imagenes*
*Referencia: [[01-Baseline/Entrevista_Completada_Proyecto]] - Seccion E.1 Stack tecnologico*