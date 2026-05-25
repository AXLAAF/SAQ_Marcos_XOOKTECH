# Plan de Trabajo: Finalización del Plan de Aseguramiento Completo (V3)
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Entrada de Gobernanza SGC
**Salidas:** Salida de Gobernanza SGC

---

> **Objetivo**: Consolidar el SGC del proyecto "Visualizador de Marcos" bajo la estructura formal de 8 fases operadas con rigor ETVX, garantizando la independencia de criterio y el control de calidad mediante la distribución equitativa de responsabilidades en cinco (5) roles institucionales despersonalizados.

---

## 1. Justificación Organizativa y de Calidad (Galin / Regan / Lewis)

Conforme a las directrices de Daniel Galin y el estándar SWEBOK v4, un Sistema de Gestión de Calidad (SGC) no puede ser operado con ambigüedad en los límites de responsabilidad. La transición de una fuerza de tarea de 3 integrantes a una estructura formal de **5 roles institucionales despersonalizados** está fundamentada teóricamente en:
1. **Gobernanza y Estructura Práctica de SQA (Regan, 2002):** De acuerdo con **Regan (2002)** (*A Practical Approach to Software Quality*), un enfoque metodológico exitoso requiere la formalización clara de las responsabilidades dentro de la organización. La asignación despersonalizada de roles en nuestro SGC previene brechas de comunicación y asegura que cada entregable técnico posea un propietario de calidad único, reduciendo la variabilidad en los procesos de codificación y soporte.
2. **Independencia en V&V e Integridad de Pruebas (Galin / Lewis, 2009):** Conforme a Daniel Galin y a **Lewis (2009)** (*Software Testing and Continuous Quality Improvement*), las actividades de verificación y validación (V&V) deben ser guiadas de forma independiente para evitar conflictos de interés. El rol que construye el código (*Líder de Desarrollo e Implementación*) no audita sus propios entregables ni diseña el Plan de Pruebas. Esto permite que el *Analista de Verificación y Pruebas* evalúe el software de manera imparcial y que el *Analista de Control y Cambios* certifique de forma objetiva la configuración y los defectos, logrando una mejora continua y sistemática del prototipo.

---

## 2. Distribución de la Fuerza de Tarea (5 Roles Oficiales)

### 2.1. Analista de Gobernanza y Diseño
*   **Fases a su Cargo:** [[01-Gestion de la configuracion/01-PROC-01_Gobernanza_Vault|01-Gestion de la configuracion]] (Gobernanza y Estándares), [[03-Diseño/03-PROC-03_Diseño_Sistema|03-Diseño]] (Arquitectura del Sistema) y [[08-Mantenimiento/08-PROC-08_Mantenimiento|08-Mantenimiento]] (Soporte Evolutivo).
*   **Actividades Principales:**
    *   Definir el marco metodológico y de nomenclatura de tags del Vault SGC.
    *   Diseñar y mantener el Plan de Acción SQA (`PLAN-01`).
    *   Elaborar la arquitectura de componentes (`STD-04`), el modelo entidad-relación de datos (`STD-06`) y el estándar de diseño de componentes.
    *   Modelar el proceso de soporte y actualización post-despliegue (`PROC-06`).

### 2.2. Analista de Requerimientos
*   **Fases a su Cargo:** [[09-Notes/01-Linea_Base-Original/00-PROC-01_Recuperacion_Linea_Base|01-Línea Base]] (Acuerdos Iniciales) y [[02-Requisitos/02-PROC-02_Especificacion_Requerimientos|02-Requisitos]] (Especificación Formal).
*   **Actividades Principales:**
    *   Gestionar el contacto técnico inicial con el socio formador ("Enmarcame"), elaborando las Actas de Constitución y Propuesta Recuperada.
    *   Conducir entrevistas de ingeniería de requisitos y documentar minutas completas.
    *   Redactar los 10 requisitos funcionales y no funcionales (`REQ-01` a `REQ-10`) con criterios de aceptación explícitos.
    *   Construir e integrar la Matriz de Trazabilidad de Requisitos (`STD-03_RTM`) para evitar brechas de implementación.

### 2.3. Líder de Desarrollo e Implementación
*   **Fases a su Cargo:** [[04-Codificacion/04-PROC-04_Codificacion|04-Codificación]] (Construcción del Software) y [[07-Despliegue/07-PROC-07_Despliegue|07-Despliegue]] (Instalación e Implementación).
*   **Actividades Principales:**
    *   Programar el prototipo funcional en Python (Flask, OpenCV, Pillow) asegurando la carga de imágenes, procesamiento e interfaz web.
    *   Garantizar la adherencia del código fuente al Estándar de Codificación (`FOR-04-01`).
    *   Actualizar y documentar el Registro de Tareas de Desarrollo (`REG-04-01`).
    *   Preparar el paquete de software final y redactar la Guía de Configuración e Instalación del Entorno (`FOR-08-01`).

### 2.4. Analista de Verificación y Pruebas
*   **Fases a su Cargo:** [[06-Pruebas/06-PROC-06_Plan_Pruebas|06-Pruebas]] (Verificación y Validación).
*   **Actividades Principales:**
    *   Diseñar y estructurar el Plan Maestro de Pruebas (`PLAN-02`).
    *   Elaborar y documentar los casos de prueba detallados (`CP-01` a `CP-15`) para verificar las funcionalidades críticas.
    *   Ejecutar las pruebas en el entorno de desarrollo y recolectar evidencias empíricas (logs, capturas y reportes de ejecución).

### 2.5. Analista de Control y Cambios
*   **Fases a su Cargo:** [[05-Control de cambios/05-PROC-05_Control_Configuracion|05-Control de cambios]] (Gestión de Configuración y Aseguramiento de Calidad).
*   **Actividades Principales:**
    *   Implementar el proceso de Control de Cambios del SGC y procesar solicitudes de cambio (`CR-00` a `CR-04`).
    *   Monitorear e integrar el Registro de Defectos e Incidencias del prototipo (`REG-03`).
    *   Realizar inspecciones formales sobre la documentación y código, emitiendo reportes de inspección estructurados (`INS-01`, `INS-02`).
    *   Consolidar las métricas organizativas y de producto en el Dashboard de Calidad (`STD-08`).

---

## 3. Estructura del Ciclo de Vida del SGC (Modelo de 8 Fases)

El ciclo de vida de aseguramiento de la calidad está organizado en las siguientes fases operadas de forma secuencial y trazable:

1.  **[[01-Gestion de la configuracion/01-PROC-01_Gobernanza_Vault|01-Gestion de la configuracion]]:** Estándares de calidad, taxonomía de archivos y directrices organizativas.
2.  **[[09-Notes/01-Linea_Base-Original/00-PROC-01_Recuperacion_Linea_Base|01-Línea Base]]:** Formalización de compromisos con el socio formador y viabilidad de inicio.
3.  **[[02-Requisitos/02-PROC-02_Especificacion_Requerimientos|02-Requisitos]]:** Especificación rigurosa de necesidades funcionales y trazabilidad técnica.
4.  **[[03-Diseño/03-PROC-03_Diseño_Sistema|03-Diseño]]:** Arquitectura lógica del prototipo, bases de datos y flujos lógicos.
5.  **[[04-Codificacion/04-PROC-04_Codificacion|04-Codificación]]:** Construcción verificada bajo estándares del prototipo del Visualizador de Marcos.
6.  **[[06-Pruebas/06-PROC-06_Plan_Pruebas|06-Pruebas]]:** Pruebas de verificación de caja negra, casos extremos y evidencias empíricas.
7.  **[[08-Mantenimiento/08-PROC-08_Mantenimiento|08-Mantenimiento]]:** Estrategia de soporte preventivo, correctivo y control de incidentes.
8.  **[[05-Control de cambios/05-PROC-05_Control_Configuracion|05-Control de cambios]]:** Control de cambios de configuración, auditorías documentales e informes de inspección.
9.  **[[07-Despliegue/07-PROC-07_Despliegue|07-Despliegue]]:** Empaquetado del software, manuales técnicos de instalación y puesta en producción.

---

## 4. Acciones Inmediatas (Checklist del Sprint Final)

Para garantizar la entrega presencial con 100.00% de conformidad formal, el equipo ejecutará las siguientes tareas antes del cierre:

- [ ] **Acción 01 - Auditoría de Arquitectura (Analista de Gobernanza y Diseño):** Auditar que [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]] coincida exactamente con la implementación del prototipo.
- [ ] **Acción 02 - Trazabilidad de Requisitos (Analista de Requerimientos):** Completar e integrar la [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|Matriz de Trazabilidad RTM]] desde los requisitos hasta los casos de prueba ejecutados.
- [ ] **Acción 03 - Entrega de Código Fuente (Líder de Desarrollo e Implementación):** Subir la versión final de Flask/OpenCV y consolidar el [[04-Codificacion/04-PROC-04_Codificacion|Registro de Tareas de Desarrollo REG-04-01]].
- [ ] **Acción 04 - Evidencia de Ejecución (Analista de Verificación y Pruebas):** Recolectar la bitácora física de resultados de los casos `CP-01` a `CP-15` y guardarlos en [[06-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]].
- [ ] **Acción 05 - Auditoría Documental y de Cambios (Analista de Control y Cambios):** Verificar que cada solicitud de cambio (`CR-00` a `CR-04`) cuente con aprobación y esté consolidada en el [[05-Control de cambios/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]].

---

## 5. Cronograma de Aseguramiento de Calidad e Hitos de Auditoría

El plan de liberación final se rige bajo los siguientes hitos institucionales de calidad:

| Fecha | Hito de Aseguramiento | Responsable | Estado |
| :--- | :--- | :--- | :---: |
| 12-May | Restructuración Organizativa a 5 Roles e Integridad RASCI | Analista de Gobernanza y Diseño | 🟢 |
| 13-May | Cierre de Inspecciones de Código y Pruebas Funcionales | Analista de Control y Cambios | 🟡 |
| 14-May | Auditoría Final del Vault y Certificación Presencial SQA | Equipo de Calidad (5 Roles) | ⚪ |

**Aprobación:** Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.

---

## 6. Referencias Bibliográficas de Gobernanza

*   **Galin, D.** (2004). *Software Quality Assurance: From theory to implementation*. Pearson / Addison-Wesley.
*   **Lewis, W. E.** (2009). *Software Testing and Continuous Quality Improvement*. USA: Auerbach Publications. (Enfoque iterativo de V&V y SCM).
*   **Regan, G. O.** (2002). *A Practical Approach to Software Quality*. USA: Springer. (Gobernanza documental e institucional del SGC).
*   **IEEE Computer Society.** (2024). *Guide to the Software Engineering Body of Knowledge (SWEBOK Guide) v4.0*.