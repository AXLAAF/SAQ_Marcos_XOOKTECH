# Plan Maestro de Pruebas -- XookTech

> **Antecedente**: Basado en la transición arquitectónica de Node.js a **Python/Flask**, este plan maestro define la estrategia de validación para asegurar la precisión de los algoritmos de **OpenCV** y la estabilidad de la API REST. La trazabilidad se garantiza mediante el mapeo directo con los requisitos de la fase 02.

**Área de proceso:** 05-Pruebas
**Nombre del proceso:** Plan Maestro de Verificación y Validación (V&V)
**Responsable:** Analista de Verificación y Pruebas
**Entradas:** Requerimientos validados (02) y Diseño de Arquitectura (03).
**Salidas:** Casos de Prueba ejecutados y Registro de Defectos.
**Notación:** CP: Caso de Prueba.

---

## 1. Alcance de las Pruebas por Módulo

### 1.1 Módulo 01: Carga de Imagen (REQ-01)
- [[05-Pruebas/Modulo-01_Carga/01-CP-01_JPG_valida|CP-01: Validación de formato JPG]]
- [[05-Pruebas/Modulo-01_Carga/02-CP-02_Archivo_invalido|CP-02: Manejo de archivos no permitidos]]
- [[05-Pruebas/Modulo-01_Carga/03-CP-03_Imagen_grande|CP-03: Control de límites de tamaño (Payload)]]

### 1.2 Módulo 02: Catálogo de Marcos (REQ-04, 05, 06)
- [[05-Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo|CP-04: Carga de catálogo desde SQLite/JSON]]
- [[05-Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo|CP-05: Filtrado por modelo (Lógica Flask)]]
- [[05-Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color|CP-06: Filtrado por color]]

### 1.3 Módulo 03: Previsualización 3D (REQ-02, 03, 07, 08, 09)
- [[05-Pruebas/Modulo-03_Previsualizacion/01-CP-08_Marco_simple|CP-08: Renderizado de Marco Simple (Pillow/Three.js)]]
- [[05-Pruebas/Modulo-03_Previsualizacion/05-CP-12_Proporciones|CP-12: Validación de proporciones reales]]

## 2. Matriz de Trazabilidad REQ -> CP

| Requerimiento (REQ) | Caso de Prueba (CP) | Tipo de Prueba |
| :--- | :--- | :--- |
| [[02-Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen\|REQ-01]] | CP-01, CP-02, CP-03 | Integración / API |
| [[02-Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos\|REQ-04]] | CP-04 | Sistema |
| [[02-Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco\|REQ-02]] | CP-08, CP-12 | Interfaz / Render |
| [[02-Requisitos/00-Pendientes/07-REQ-07_Marcos_Dobles\|REQ-07]] | CP-09 | Funcional |

## 3. Estrategia Técnica (Ciclo de Vida)

1.  **Pruebas de Unidad**: Validación de funciones OpenCV en `detector_ancho.py`.
2.  **Pruebas de Integración**: Pruebas de rutas Flask (`POST /upload`).
3.  **Pruebas de Interfaz**: Validación de renderizado Three.js en el Navegador.

---

## Referencias
- **SWEBOK v4**: Knowledge Area 4 - Software Testing.
- **IEEE 829**: Standard for Software Test Documentation.
- **Daniel Galin (2004)**: Software Quality Assurance - "Software Testing Strategies".
