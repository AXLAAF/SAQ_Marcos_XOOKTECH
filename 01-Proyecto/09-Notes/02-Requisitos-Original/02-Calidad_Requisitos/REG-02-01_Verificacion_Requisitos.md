# REG-02-01: Registro de Verificación de Calidad de Requisitos — XookTech
**Responsable:** Analista de Control y Cambios
**Entradas:** Requisitos Aprobados y Checklist CL-02
**Salidas:** Registro de Conformidad de Calidad de Requisitos

---

## 1. Introducción y Propósito

Este registro documenta las actividades de control de calidad aplicadas por el **Analista de Control y Cambios** sobre la Línea Base de requisitos del **Visualizador de Marcos**. Cada requerimiento en estado "Aprobado" es sometido a una revisión formal e independiente utilizando los criterios establecidos en el [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02 Checklist de Verificación de Requerimientos]] antes de autorizar su pase a la fase de desarrollo y codificación.

---

## 2. Historial de Verificación de Requisitos (Línea Base)

A continuación se detalla el estado de conformidad de los requisitos que componen la Línea Base aprobada:

| ID Requisito | Título del Requerimiento | Evaluador (Rol) | Fecha de Evaluación | Checklist Aplicado | Estado de Conformidad |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01]] | Carga de Imagen del Cliente | Analista de Control y Cambios | 2026-05-10 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/05-REQ-02_Previsualizacion_Marco|REQ-02]] | Previsualización de Marco | Analista de Control y Cambios | 2026-05-11 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/06-REQ-03_Generacion_Marcos_3D|REQ-03]] | Generación de Marcos 3D | Analista de Control y Cambios | 2026-05-11 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/02-REQ-04_Catalogo_Marcos|REQ-04]] | Catálogo de Marcos | Analista de Control y Cambios | 2026-05-12 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/03-REQ-05_Filtrado_Catalogo|REQ-05]] | Filtrado de Catálogo | Analista de Control y Cambios | 2026-05-12 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |
| [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/04-REQ-06_Datos_Catalogo|REQ-06]] | Datos del Catálogo de Marcos | Analista de Control y Cambios | 2026-05-13 | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]] | **100.00% Conforme** |

---

## 3. Resumen de Hallazgos y Acciones Correctivas

- **Evaluación General:** El 100.00% de los requisitos aprobados cumple con todos los atributos de calidad del **SWEBOK** (son atómicos, verificables de forma objetiva, no ambiguos y completos).
- **BDD e Integridad:** Se confirmó que todos los requisitos aprobados cuentan con escenarios Dado/Cuando/Entonces y límites de datos cuantificados (tamaño de archivo <= 10 MB, resolución mínima 200x200px, etc.).
- **Trazabilidad:** Se verificó que la [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03 Matriz de Trazabilidad]] se encuentra completamente sincronizada con los casos de prueba y los diagramas de arquitectura de diseño antes del inicio de la codificación.

---

## 4. Referencias

[1] Checklist de Verificación de Requerimientos. [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02]]  
[2] Matriz de Trazabilidad de Requisitos (RTM). [[02-Requisitos/01-Ingenieria_Requisitos/01-STD-03_Matriz_Trazabilidad|STD-03]]  
[3] Reporte de Inspección Formal de Requisitos. [[05-Control de cambios/02-Calidad_Control/05-INS-01_Inspeccion_Requerimientos|05-INS-01]]
