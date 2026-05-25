# STD-03: Estándar de Matriz de Responsabilidades y Asignación de Roles ETVX
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

---

## 1. Introducción y Justificación Académica

Para garantizar la independencia de criterio, el control de la calidad y el cumplimiento riguroso de los hitos del prototipo **Visualizador de Marcos**, el equipo se organiza bajo una estructura despersonalizada de **cinco (5) roles institucionales**. 

Esta distribución balanceada de responsabilidades se fundamenta rigurosamente en la literatura clásica y contemporánea de ingeniería de software y aseguramiento de la calidad:
1. **Separación de Funciones e Independencia (Galin / Regan):** Conforme a Daniel Galin y a la perspectiva práctica de **Regan (2002)**, una estructura organizativa robusta del SGC exige la clara división de responsabilidades. Regan (2002) sostiene que formalizar los roles y responsabilidades de aseguramiento de calidad de forma sistemática reduce los errores de comunicación y evita conflictos de interés, permitiendo que las actividades de verificación y validación (V&V) se ejecuten sin sesgos de codificación.
2. **Mejora Continua de la Calidad y Pruebas (SWEBOK / Lewis):** Basado en el SWEBOK v4 y en los principios de **Lewis (2009)**, la calidad de software es un proceso continuo que integra las pruebas (Testing) no solo como un evento final, sino como un engrane para la mejora continua del proceso (Continuous Quality Improvement). Lewis (2009) promueve que las actividades de control de calidad retroalimenten dinámicamente la gobernanza (Ciclo PDCA) para depurar y certificar las configuraciones y estándares mediante métricas tangibles.

---

## 2. Perfil y Ámbito de los 5 Roles Institucionales

### 2.1. Analista de Gobernanza y Diseño
- **Ámbito de Acción:** Fase 00 (Gobernanza), Fase 03 (Diseño) y Fase 06 (Mantenimiento).
- **Competencias Técnicas:** Gestión documental, diseño de arquitectura de software, modelado de bases de datos y soporte técnico post-entrega.
- **Entregables Clave:** PROC-01 (Gobernanza del Vault), PROC-03 (Proceso de Diseño), Diagrama de Componentes (STD-04), Flujo del Sistema (STD-05), Modelo de Datos (STD-06), Arquitectura Python (STD-07) y PROC-06 (Mantenimiento).

### 2.2. Analista de Requerimientos
- **Ámbito de Acción:** Fase 01 (Línea Base) y Fase 02 (Requisitos).
- **Competencias Técnicas:** Elicitación de requisitos, análisis de viabilidad, matriz de trazabilidad de requisitos y comunicación con Product Owners.
- **Entregables Clave:** PROC-01 (Línea Base), Acta de Inicio, Propuesta Recuperada, Acuerdos Contractuales, Minuta de Entrevista (Guía y Completada), PROC-02 (Requisitos) y Matriz de Trazabilidad RTM (STD-03).

### 2.3. Líder de Desarrollo e Implementación
- **Ámbito de Acción:** Fase 04 (Codificación) y Fase 08 (Despliegue).
- **Competencias Técnicas:** Programación en Python, procesamiento de imágenes con OpenCV/Pillow, desarrollo web Flask, control de versiones (Git) y configuración de servidores.
- **Entregables Clave:** PROC-04 (Codificación), Registro de Tareas de Desarrollo (REG-04-01), Estándar de Codificación (FOR-04-01), Código Fuente, PROC-08 (Despliegue) y Guía de Configuración (FOR-08-01).

### 2.4. Analista de Verificación y Pruebas
- **Ámbito de Acción:** Fase 05 (Pruebas).
- **Competencias Técnicas:** Diseño de casos de prueba (Happy Path, límites, fallos), ejecución de pruebas de caja negra, análisis de logs de servidor y registro de resultados de pruebas.
- **Entregables Clave:** PROC-05 (Pruebas), Plan Maestro de Pruebas (PLAN-02) y Casos de Prueba Módulos 1-4 (CP-01 a CP-15).

### 2.5. Analista de Control y Cambios
- **Ámbito de Acción:** Fase 07 (Control y Cambios).
- **Competencias Técnicas:** Software Configuration Management (SCM), auditorías documentales, control de cambios, inspecciones formales de código/requisitos y métricas de calidad.
- **Entregables Clave:** PROC-07 (Control), PROC-08 (Control Cambios), Dashboard de Calidad (STD-08), Registro de Defectos (REG-03), Reportes de Inspección (INS-01, INS-02) y Solicitudes de Cambio (CR-00 a CR-04).

---

## 3. Matriz de Asignación de Responsabilidades (Matriz RASCI)

La matriz **RASCI** define el nivel de participación de cada rol en los entregables del SGC:
*   **R - Responsable (Responsible):** El rol que realiza físicamente el trabajo del entregable.
*   **A - Aprobador (Accountable):** El rol con la autoridad final de aprobación del entregable (debe haber exactamente uno por fila).
*   **S - Soporte (Support):** Roles que asisten o apoyan en la elaboración del entregable.
*   **C - Consultado (Consulted):** Roles consultados que aportan información valiosa.
*   **I - Informado (Informed):** Roles informados de la finalización del entregable.

| Fase / Entregable | Analista Gobernanza | Analista Requisitos | Líder Desarrollo | Analista Pruebas | Analista Control |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **01-Gestion de la configuracion: PROC-01 Gobernanza SGC** | **A / R** | C | I | I | S |
| **01-Gestion de la configuracion: PLAN-01 Acción SQA** | **A / R** | S | S | S | S |
| **01-Línea Base: Acta de Constitución** | S | **A / R** | C | I | I |
| **01-Línea Base: Minuta de Entrevista** | C | **A / R** | S | I | I |
| **02-Requisitos: PROC-02 Requisitos** | I | **A / R** | C | S | S |
| **02-Requisitos: STD-03 Matriz RTM** | C | **A / R** | S | S | S |
| **03-Diseño: STD-04 Arquitectura** | **A / R** | C | S | I | I |
| **03-Diseño: STD-06 Modelo de Datos** | **A / R** | C | S | I | I |
| **04-Codificación: Código Fuente Flask** | I | I | **A / R** | C | S |
| **04-Codificación: REG-04-01 Tareas** | I | I | **A / R** | I | S |
| **04-Pruebas: PLAN-02 Plan de Pruebas** | I | C | S | **A / R** | S |
| **04-Pruebas: CP-01 a CP-15 Casos** | I | C | S | **A / R** | I |
| **08-Mantenimiento: PROC-06 Soporte** | **A / R** | I | S | I | I |
| **05-Revisiones e inspecciones: REG-03 Defectos** | I | I | S | S | **A / R** |
| **05-Revisiones e inspecciones: CR-01 a CR-04 Cambios** | C | C | S | I | **A / R** |
| **05-Revisiones e inspecciones: INS-01 / INS-02 Reportes** | I | S | S | S | **A / R** |
| **07-Despliegue: PROC-08 Guía** | I | I | **A / R** | I | S |

---

## 4. Criterios de Aceptación de Gobernanza (ETVX)

Para asegurar que las responsabilidades se operen con total disciplina, cada proceso o formato entregado debe certificar su conformidad mediante el script oficial `validate_sgc.py` de la skill `sqa-universidad`. La violación de la despersonalización o la ambigüedad en los roles asignados invalidará la conformidad de calidad del artefacto correspondiente.

---

## 5. Referencias Bibliográficas del SGC

*   **Galin, D.** (2004). *Software Quality Assurance: From theory to implementation*. Pearson / Addison-Wesley.
*   **Lewis, W. E.** (2009). *Software Testing and Continuous Quality Improvement*. USA: Auerbach Publications. (Rigor en V&V y Ciclos de Calidad).
*   **Regan, G. O.** (2002). *A Practical Approach to Software Quality*. USA: Springer. (Perspectiva Clásica de Gobernanza Organizativa de Calidad).
*   **IEEE Computer Society.** (2024). *Guide to the Software Engineering Body of Knowledge (SWEBOK Guide) v4.0*.