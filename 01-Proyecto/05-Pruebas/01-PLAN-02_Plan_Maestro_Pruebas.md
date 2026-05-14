---
id: PLAN-02
titulo: Plan Maestro de Pruebas - Sistema Visualizador de Marcos
version: "1.1"
estado: Activo
tipo: Plan de Pruebas
fecha_creacion: 2026-03-23
ultima_revision: 2026-05-13
responsable: Samuel Blanco
referencias:
  - "SWEBOK v4 KA5 - Software Testing"
  - "Galin, D. (2004). Software Quality Assurance."
  - "[[00-PROC-05_Plan_Pruebas]]"
tags:
  - meta/prioridad/alta
  - fase/pruebas
  - tipo/plan
---

# Plan Maestro de Pruebas - Sistema Visualizador de Marcos

## 1. Introducción

Este documento constituye el Plan Maestro de Pruebas para el sistema "Visualizador de Marcos". El plan sigue las directrices del SWEBOK v4 y la infraestructura de Galin para asegurar la detección temprana de defectos y la trazabilidad total con los requerimientos especificados en la carpeta `02-Requisitos`.

## 2. Alcance de las Pruebas por Módulo

### 2.1 Módulo 1: Carga de Imagen (REQ-01)
- [[01-CP-01_JPG_valida]]
- [[02-CP-02_Archivo_invalido]]
- [[03-CP-03_Imagen_grande]]

### 2.2 Módulo 2: Catálogo de Marcos (REQ-04, 05, 06)
- [[01-CP-04_Carga_catalogo]]
- [[02-CP-05_Filtro_modelo]]
- [[03-CP-06_Filtro_color]]
- [[04-CP-07_Filtro_ancho]]

### 2.3 Módulo 3: Previsualización 3D (REQ-02, 03, 07, 08, 09)
- [[01-CP-08_Marco_simple]]
- [[02-CP-09_Marco_doble]]
- [[03-CP-10_Tipo_vidrio]]
- [[04-CP-11_Maria_Luisa]]
- [[05-CP-12_Proporciones]]

### 2.4 Módulo 4: Pantalla Secundaria (REQ-10)
- [[01-CP-13_Proyeccion]]
- [[02-CP-14_Sync_tiempo_real]]
- [[03-CP-15_Fallback_sin_pantalla]]

## 3. Matriz de Trazabilidad REQ -> CP

| REQ | Título del Requerimiento | Casos de Prueba Asociados |
| :--- | :--- | :--- |
| [[01-REQ-01_Carga_Imagen]] | Carga de Imagen | CP-01, CP-02, CP-03 |
| [[02-REQ-04_Catalogo_Marcos]] | Catálogo de Marcos | CP-04, CP-05 |
| [[03-REQ-05_Filtrado_Catalogo]] | Filtrado de Catálogo | CP-05, CP-06, CP-07 |
| [[05-REQ-02_Previsualizacion_Marco]] | Previsualización | CP-08, CP-12 |
| [[07-REQ-07_Marcos_Dobles]] | Marcos Dobles | CP-09 |
| [[10-REQ-10_Pantalla_Secundaria]] | Pantalla Secundaria | CP-13, CP-14, CP-15 |

## 4. Criterios de Aceptación y Salida
- **Criterio de Salida**: 100% de los CP de prioridad alta ejecutados con resultado "Exitoso".
- **Defectos**: Ningún defecto de severidad "Crítica" o "Alta" pendiente de resolución.

## 5. Referencias de Gobernanza
- [[00-PROC-00_Gobernanza_Vault]]
- [[03-STD-02_Convenciones_Tags]]
- [[00-PROC-05_Plan_Pruebas]]

---
*Actualización conforme al Estándar de Prioridad SQA: 2026-05-13*
