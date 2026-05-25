# Plan de Mejora — Requisitos de Software

**Responsable:** Analista de Requerimientos  
**Entradas:** Diagnóstico As-Is de brechas del proceso, estándares internacionales ISO/IEC 12207 y CMMI-DEV v2.0.  
**Salidas:** Acciones de mejora planificadas, proceso To-Be estructurado bajo ETVX, Matriz de Trazabilidad RTM integrada y Registro de Verificación SQA.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Especificación y Gestión de Requisitos de Software |
| Documento base | [00-REQ-Documentacion_Requisitos.md](file:///home/axelmc/Obsidian/OBS26/02-Estudios/Universidad/Aseguramiento%20de%20la%20Calidad%20de%20Software%201.0/Assignments_V2/01-Proyecto/02-Requisitos/00-REQ-Documentacion_Requisitos.md) |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de requisitos disciplinado, maduro y controlado en XookTech. Se busca erradicar la informalidad de los acuerdos verbales mediante asignaciones escritas y Reportes de Junta formales, inyectar el estándar de especificación en lenguaje estructurado BDD para eliminar ambigüedades, garantizar la trazabilidad bidireccional entre requerimientos, diseño y pruebas, e implantar auditorías independientes de Aseguramiento de Calidad (SQA) que certifiquen el 100.00% de la conformidad del SGC.

## Tipo de intervención
☒ Mejora de proceso existente  
☐ Implantación de proceso inexistente

---

## 3. Resumen de Hallazgos

| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | Captura y asignación informal de requerimientos vía WhatsApp sin evidencia técnica. | **M-01** Agendamiento formal y uso obligatorio de Reportes de Junta. |
| **H-02** | Ausencia de folios de entrada y registro único de la necesidad de negocio. | **M-02** Inicialización y registro estructurado de requerimientos técnicos. |
| **H-03** | Redacción técnica ambigua en lenguaje natural libre sin límites ni cotas numéricas. | **M-03** Especificación técnica estructurada en formato unificado BDD. |
| **H-04** | Inicio de la codificación de software sin contar con la validación formal escrita del PO. | **M-04** Sesión de validación técnica y evidencia de aprobación digital explícita. |
| **H-05** | Mezcla física de archivos pendientes y aprobados en carpetas desorganizadas. | **M-05** Segregación física obligatoria de Línea Base en Obsidian. |
| **H-06** | Inexistencia de trazabilidad bidireccional entre requerimientos, diseño y pruebas. | **M-06** Matriz de Trazabilidad RTM bidireccional unificada. |
| **H-07** | Ausencia de auditorías de SQA independientes y de registros de calidad formales. | **M-07** Auditorías de SQA independientes y dictamen formal unificado. |

---

## 4. Acciones de Mejora

Esta sección define el conjunto de acciones correctivas y de optimización estructuradas como **pasos secuenciales que cubren la totalidad del ciclo de vida de ingeniería y gestión de requisitos** (Elicitación, Análisis, Especificación, Validación, Gestión de Configuración/Línea Base, Trazabilidad y Verificación/SQA) bajo el estándar **XookTech v2.0**:

| Paso del Ciclo de Vida | ID | Acción de Mejora / Actividad | Hallazgo que atiende | Responsable | Artefacto Asociado | Prioridad |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1. Elicitación (Captura)** | **M-01** | Agendamiento formal y uso obligatorio de Reportes de Junta | H-01 | Analista de Requerimientos | `PLT-Reporte_Junta.md` (General) | Alta |
| **2. Análisis de Requisitos** | **M-02** | Inicialización y registro estructurado de requerimientos técnicos | H-02 | Analista de Requerimientos | N/A (Registro procedimental) | Alta |
| **3. Especificación** | **M-03** | Especificación técnica estructurada en formato unificado BDD | H-03 | Analista de Requerimientos | [[PLT-SRS]] / [[PLT-Historia-Usuario]] | Alta |
| **4. Validación** | **M-04** | Validación técnica conjunta y evidencia de aprobación digital | H-04 | Analista de Requerimientos | Ficha de Requerimiento (Sección Evidencia) | Alta |
| **5. Gestión de Línea Base** | **M-05** | Segregación física obligatoria de estados en Obsidian | H-05 | Analista de Requerimientos | Carpetas `/00-Pendientes/` y `/01-Aprobados/` | Alta |
| **6. Trazabilidad** | **M-06** | Integración y mantenimiento de Matriz RTM bidireccional | H-06 | Analista de Requerimientos | Matriz de Trazabilidad RTM (Sección 6) | Alta |
| **7. Verificación / SQA** | **M-07** | Auditorías independientes y Registro de Verificación SQA | H-07 | Analista de Control y Cambios | Registro de Verificación SQA (Sección 7) | Alta |

---

### Paso 1: Elicitación y Captura
#### M-01 — Agendamiento formal y uso obligatorio de Reportes de Junta
*   **Situación actual:** Captura y asignación informal de requerimientos vía WhatsApp sin evidencia técnica ni validación previa (H-01).
*   **Situación propuesta:** Todo levantamiento inicial o solicitud de cambio debe ser agendado formalmente con el Product Owner (PO) vía Meet/Teams con un mínimo de 24 horas de anticipación. El equipo de desarrollo debe preparar previamente una agenda de trabajo y guía de preguntas utilizando la plantilla institucional de Reporte de Junta de XookTech.
*   **Justificación teórica:** CMMI-DEV v2.0 (Planificación y Control del Trabajo) e ISO/IEC 12207 establecen que el trabajo de ingeniería debe iniciarse de forma planificada y documentada para evitar discrepancias lógicas y desvíos de alcance.
*   **Artefacto asociado:** Plantilla institucional de Reporte de Junta (`PLT-Reporte_Junta.md` en biblioteca de procesos).
*   **Evidencia de cumplimiento:** Minuta de Reporte de Junta técnica firmado digitalmente por los participantes y guardado en Obsidian.

---

### Paso 2: Análisis de Requisitos
#### M-02 — Inicialización y registro estructurado de requerimientos técnicos
*   **Situación actual:** Ausencia de folios de entrada y registro único de la necesidad de negocio identificada (H-02).
*   **Situación propuesta:** Se asigna un identificador estructurado único (`REQ-XX`) a cada necesidad de negocio identificada en la junta y se documenta de forma controlada en Obsidian. Si la necesidad proviene de una Solicitud de Cambio formal, esta se asocia de forma unívoca con su respectivo folio de control de cambios (`CR-XXX`).
*   **Justificación teórica:** SWEBOK v4 Cap. 2 (Ingeniería de Requisitos) y la gestión de configuración del software exigen la identificación unívoca y el registro controlado de requerimientos para ejercer control ante cambios de alcance.
*   **Artefacto asociado:** N/A (Registro procedimental de configuración inline en el Vault).
*   **Evidencia de cumplimiento:** Catálogo de requerimientos (`REQ-01` al `REQ-10`) registrados y descritos de manera centralizada en la Línea Base de Obsidian.

---

### Paso 3: Especificación de Requisitos
#### M-03 — Especificación técnica estructurada en formato unificado BDD
*   **Situación actual:** Redacción técnica ambigua en lenguaje natural libre sin límites claros ni cotas numéricas (H-03).
*   **Situación propuesta:** Uso mandatorio de la plantilla oficial de especificación de requisitos (`PLT-SRS.md` para especificaciones del sistema o `PLT-Historia-Usuario.md` para historias de usuario). Se exige inyectar escenarios bajo la notación estructurada `Dado / Cuando / Entonces` (Happy Path, flujos alternos y excepciones) y cotas numéricas exactas (formatos, pesos, dimensiones y restricciones del sistema).
*   **Justificación teórica:** Daniel Galin (2004) y SWEBOK v4 Cap. 2 postulan que el lenguaje estructurado BDD y las cotas numéricas eliminan la ambigüedad lógica, facilitando un diseño de pruebas unitarias robusto y automatizable.
*   **Artefacto asociado:** [[02-Requisitos/Plantillas/Formatos/PLT-SRS|PLT-SRS.md]] (Especificación de Requisitos) o [[02-Requisitos/Plantillas/Formatos/PLT-Historia-Usuario|PLT-Historia-Usuario.md]] (Historias de Usuario).
*   **Evidencia de cumplimiento:** Ficha técnica de Especificación de Requisitos (`REQ-XX.md`) completa y con escenarios BDD modelados, verificada contra el checklist de requisitos individuales.

---

### Paso 4: Validación de Requisitos
#### M-04 — Sesión de validación técnica y evidencia de aprobación digital explícita
*   **Situación actual:** Inicio de la codificación de software sin contar con la validación formal escrita del PO (H-04).
*   **Situación propuesta:** Sesión interactiva de revisión y validación de la lógica BDD y prototipos interactivos con el PO antes de escribir cualquier código funcional. Es mandatorio adjuntar la confirmación escrita por correo electrónico o captura de mensaje digital directo del PO, inyectándola en la sección "Evidencia de Aprobación" del archivo de requerimiento.
*   **Justificación teórica:** G. O. Regan (2002) en *A Practical Approach to Software Quality* destaca que la validación formal y la firma contractual de aceptación del cliente es la única defensa objetiva de aseguramiento de la calidad ante discrepancias lógicas posteriores.
*   **Artefacto asociado:** Ficha Técnica del Requisito (Sección "Evidencia de Aprobación PO").
*   **Evidencia de cumplimiento:** Captura de pantalla de la aprobación digital o correo del PO inyectado en el archivo `REQ-XX` correspondiente en estado aprobado.

---

### Paso 5: Gestión de la Configuración / Línea Base
#### M-05 — Segregación física obligatoria de estados en Obsidian
*   **Situación actual:** Mezcla física de archivos pendientes y aprobados en carpetas desorganizadas sin control de versión estable (H-05).
*   **Situación propuesta:** Establecer una segregación física estricta en el Vault de Obsidian. Los requerimientos en borrador o pendientes de validación se almacenan en `/00-Pendientes/` y, una vez firmados y autorizados digitalmente por el PO, se mueven físicamente a la carpeta de aprobados estables `/01-Aprobados/` en la Línea Base.
*   **Justificación teórica:** SWEBOK v4 Cap. 5 destaca la segregación de entornos físicos y la inmutabilidad de la Línea Base como principios críticos para evitar corrupciones o modificaciones accidentales de código durante el desarrollo.
*   **Artefacto asociado:** Estructura física del repositorio (carpetas `00-Pendientes` y `01-Aprobados`).
*   **Evidencia de cumplimiento:** Auditoría de estructura en Obsidian demostrando que la carpeta `01-Aprobados/` solo contiene archivos en estado `#estado/aprobado` con su respectiva evidencia digital de validación.

---

### Paso 6: Trazabilidad de Requisitos
#### M-06 — Matriz de Trazabilidad RTM bidireccional unificada
*   **Situación actual:** Inexistencia de trazabilidad bidireccional entre requerimientos, diseño y pruebas (H-06).
*   **Situación propuesta:** Mapeo y mantenimiento mandatorio de la Matriz de Trazabilidad RTM unificada dentro del Plan de Mejora (Sección 6). Vincula bidireccionalmente cada requisito (`REQ-XX`) con su fuente original, el diagrama de arquitectura y diseño, y sus casos de prueba asociados en Obsidian, evaluándose con el checklist de trazabilidad.
*   **Justificación teórica:** CMMI-DEV v2.0 REQM SP 1.4 destaca la trazabilidad bidireccional como el único mecanismo objetivo de cobertura que demuestra que cada componente de código responde exactamente a un requisito validado.
*   **Artefacto asociado:** Matriz de Trazabilidad RTM integrada (Sección 6 de este documento).
*   **Evidencia de cumplimiento:** Matriz RTM actualizada y verificada conforme contra el checklist [[02-Requisitos/Checklists/CHK-RTM]].

---

### Paso 7: Verificación de Requisitos / SQA
#### M-07 — Auditorías de SQA independientes y Registro de Verificación SQA
*   **Situación actual:** Ausencia de auditorías de SQA independientes y de registros de calidad formales (H-07).
*   **Situación propuesta:** Ejecución de auditorías de calidad independientes lideradas por el Analista de Control y Cambios. Cada requisito incorporado a la Línea Base debe ser revisado frente a las listas de verificación y el dictamen conforme registrado digitalmente en el Registro de Verificación SQA integrado (Sección 7).
*   **Justificación teórica:** CMMI-DEV v2.0 PPQA SP 1.1 e IEEE Std 830 conceptualizan el rol independiente del Aseguramiento de Calidad como el dictaminador de la conformidad objetiva del producto frente a los estándares organizacionales.
*   **Artefacto asociado:** Registro de Verificación SQA integrado (Sección 7) y checklists de verificación:
    *   Checklist de Requisitos Individuales: [[02-Requisitos/Checklists/CHK-REQ]]
    *   Checklist de Trazabilidad RTM: [[02-Requisitos/Checklists/CHK-RTM]]
    *   Checklist de Registro de Calidad: [[02-Requisitos/Checklists/CHK-REG]]
    *   Checklist del Documento SRS: [[02-Requisitos/Checklists/CHK-SRS]]
*   **Evidencia de cumplimiento:** Registro de Verificación SQA completo, firmado electrónicamente por el auditor y con 100.00% de conformidad en Obsidian.

---

## 5. Proceso To-Be (PROC-02) — Modelo de Especificación ETVX

Este proceso técnico rige la ingeniería y gestión de requerimientos bajo el ciclo de mejora continua PDCA y el modelo ETVX:

*   **Disparador:** Recepción y validación de la propuesta preliminar de la línea base aprobada por SQA o de una Solicitud de Cambio (`CR-XXX`).
*   **Criterio de Entrada (Entry Criteria):** Contar con el Contrato de Desarrollo formalizado e inyectado en la carpeta de revisiones y con el archivo `CR-XXX` en estado `#estado/aprobado`.

### Matriz de Tareas (Task) — Entradas, Actividades y Salidas

| Entrada (Input) | Actividad (Task) | Salida (Output) |
| :--- | :--- | :--- |
| `Solicitud del PO` / `CR` | Agendamiento de sesión formal vía Google Meet o Teams con el PO, enviando la invitación escrita con un mínimo de 24 horas de anticipación. | `Confirmación Escrita PO` |
| `Confirmación Escrita PO` | Preparación de preguntas guía y agenda formal de sesión utilizando la plantilla de Reporte de Junta de XookTech. | `Reporte de Junta Preliminar` |
| `Reporte de Junta Preliminar` | Creación de nota física de entrada en estado Pendiente bajo la nomenclatura `02-Requisitos/00-Pendientes/REQ-XXX.md` por cada necesidad de negocio identificada. | `REQ-XXX (Pendiente Inicial)` |
| `REQ-XXX (Pendiente Inicial)` | Aplicación e inyección formal de la estructura de plantilla `PLT-SRS` o `PLT-Historia-Usuario` en la ficha de pendientes. | `REQ-XXX (Estructurado)` |
| `REQ-XXX (Estructurado)` | Redacción de las reglas de negocio técnicas (`RN-XX-XX`) estableciendo cotas y límites exactos (formatos admitidos, peso <= 10 MB, restricciones del sistema). | `REQ-XXX (Reglas Acotadas)` |
| `REQ-XXX (Reglas Acotadas)` | Modelado detallado de los criterios de aceptación en la notación estructurada `Dado / Cuando / Entonces` (Happy Path, flujos alternos y excepciones). | `REQ-XXX (Modelado BDD)` |
| `REQ-XXX (Modelado BDD)` | Auto-evaluación del requerimiento bajo los criterios del checklist de calidad unificado [[02-Requisitos/Checklists/CHK-REQ]]. | `REQ-XXX (Auto-evaluado)` |
| `REQ-XXX (Auto-evaluado)` | Mapeo inicial de enlaces de trazabilidad vacíos y prototipado interactivo simplificado en el canvas de Obsidian. | `REQ-XXX (Prototipado)` |
| `REQ-XXX (Prototipado)` | Presentación y validación conjunta del requerimiento BDD y el prototipo interactivo en sesión técnica con el PO. | `Acta de Revisión` |
| `Acta de Revisión` | Obtención de la aprobación digital del PO por escrito e inyección del correo o de la confirmación digital en la sección "Evidencia de Aprobación" de la ficha. | `REQ-XXX (Firmado digitalmente)` |
| `REQ-XXX (Firmado digitalmente)` | Actualización de la metadata de la ficha técnica en Obsidian al estado oficial `#estado/aprobado`. | `REQ-XXX (Aprobado)` |
| `REQ-XXX (Aprobado)` | Segregación física de la ficha firmada, moviendo el archivo desde pendientes a la carpeta `02-Requisitos/01-Aprobados/`. | `REQ-XXX (Segregado)` |
| `REQ-XXX (Segregado)` | Sincronización y mapeo de trazabilidad bidireccional en la Matriz RTM integrada (Sección 6) vinculando el REQ con su diseño y caso de prueba. | `Matriz RTM (Actualizada)` |
| `Matriz RTM (Actualizada)` | Validación independiente de la consistencia e integridad de la Matriz RTM integrada utilizando el checklist de trazabilidad [[02-Requisitos/Checklists/CHK-RTM]]. | `Matriz RTM (Verificada)` |
| `REQ-XXX (Segregado)` | Ejecución de auditoría de SQA independiente por el Analista de Control y Cambios aplicando el checklist [[02-Requisitos/Checklists/CHK-REQ]]. | `Dictamen SQA` |
| `Dictamen SQA` | Firma del dictamen conforme en el Registro de Verificación integrado (Sección 7), congelando el requerimiento en la Línea Base. | `Registro SQA (Actualizado)` |
| `Registro SQA (Actualizado)` | Distribución del requerimiento congelado al Líder de Desarrollo e Implementación y al Analista de Verificación y Pruebas. | `Línea Base Congelada` |

---

## 6. Matriz de Trazabilidad RTM (STD-03) integrada

Esta matriz unificada vincula bidireccionalmente cada requisito con su fuente de origen, el diagrama de diseño lógico y sus casos de prueba:

| ID Requisito | Título del Requisito | Fuente de Origen | Diseño Relacionado | Casos de Prueba Relacionados | Estado |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `REQ-01` | Carga de Archivos de Entrada | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/01-CP-01_Archivo_valido]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/02-CP-02_Archivo_invalido]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-01_Carga/03-CP-03_Archivo_grande]] | Aprobado |
| `REQ-02` | Previsualización de Contenido | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/02-STD-05_Flujo_Sistema]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/01-CP-08_Elemento_simple]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/05-CP-12_Proporciones]] | Aprobado |
| `REQ-03` | Procesamiento 3D (obsoleto) | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/01-CP-08_Elemento_simple]] | Aprobado |
| `REQ-04` | Catálogo de Componentes | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Sistema]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo]] | Aprobado |
| `REQ-05` | Filtrado del Catálogo de Componentes | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/04-STD-07_Arquitectura_Sistema]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/02-CP-05_Filtro_modelo]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/03-CP-06_Filtro_color]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/04-CP-07_Filtro_ancho]] | Aprobado |
| `REQ-06` | Datos del Catálogo | [[09-Notes/01-Linea_Base-Original/06-Contrato_Desarrollo]] | [[03-Diseño/01-Ingenieria_Diseño/03-STD-06_Modelo_Datos]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-02_Catalogo/01-CP-04_Carga_catalogo]] | Aprobado |
| `REQ-07` | Visualización Avanzada de Componentes | [[05-Revisiones e inspecciones/01-Ingenieria_Control/08-CR-01_Componentes_Dobles]] | [[03-Diseño/01-Ingenieria_Diseño/01-STD-04_Diagrama_Componentes]] | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/02-CP-09_Elemento_doble]] | Aprobado |
| `REQ-08` | Selección de Parámetros de Visualización | [[05-Revisiones e inspecciones/01-Ingenieria_Control/09-CR-02_Parametros_Visualizacion]] | TBD | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/03-CP-10_Parametros_Visualizacion]] | Pendiente |
| `REQ-09` | Simulación de Capas y Contornos | [[05-Revisiones e inspecciones/01-Ingenieria_Control/10-CR-03_Capas_Contornos]] | TBD | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-03_Visualizacion/04-CP-11_Capas_Contornos]] | Pendiente |
| `REQ-10` | Proyección en Interfaz Secundaria | [[05-Revisiones e inspecciones/01-Ingenieria_Control/11-CR-04_Interfaz_Secundaria]] | TBD | [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Interfaz_Secundaria/01-CP-13_Proyeccion]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Interfaz_Secundaria/02-CP-14_Sync_tiempo_real]], [[04-Pruebas/01-Ingenieria_Pruebas/Modulo-04_Interfaz_Secundaria/03-CP-15_Fallback_sin_interfaz]] | Pendiente |

---

## 7. Registro de Verificación SQA (REG-02-01) integrado

Historial de conformidad de los requisitos que componen la Línea Base aprobada:

| Título del Requisito | ID Requisito | Función | Evaluador (Rol) | Fecha de Evaluación | Checklist Aplicado | Estado de Conformidad |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Carga de Archivos de Entrada | REQ-01 | Carga de Archivos | Analista de Control y Cambios | 2026-05-10 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Previsualización de Contenido | REQ-02 | Previsualización de Contenido | Analista de Control y Cambios | 2026-05-11 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Procesamiento 3D (obsoleto) | REQ-03 | Procesamiento 3D | Analista de Control y Cambios | 2026-05-11 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Catálogo de Componentes | REQ-04 | Catálogo de Componentes | Analista de Control y Cambios | 2026-05-12 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Filtrado del Catálogo de Componentes | REQ-05 | Filtrado de Catálogo | Analista de Control y Cambios | 2026-05-12 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Datos del Catálogo | REQ-06 | Datos de Catálogo | Analista de Control y Cambios | 2026-05-13 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |
| Visualización Avanzada de Componentes | REQ-07 | Visualización Avanzada | Analista de Control y Cambios | 2026-05-24 | [[02-Requisitos/Checklists/CHK-REQ]] | **100.00% Conforme** |

*   **Resumen de Hallazgos SQA (REQ-07):** La revisión inicial del requerimiento de Visualización Avanzada de Componentes arrojó ambigüedad en la regla `RN-07-04` (parámetro configurable no cuantificado). Se aplicó una acción correctiva que obligó al Analista de Requerimientos a acotar una tolerancia máxima de `50 unidades`, logrando la conformidad del 100.00% bajo el checklist `CHK-REQ` antes del congelamiento formal de la Línea Base.

---

## 8. Indicadores de Éxito
| Indicador | Métrica | Meta | Justificación de la Meta |
|---|---|---|---|
| Trazabilidad RTM | % de REQ Aprobados con trazabilidad bidireccional completa. | `100.00%` | Garantiza cobertura total de desarrollo y pruebas sin dejar brechas. |
| Densidad de Defectos | Defectos de ambigüedad detectados por SQA / Total de REQ Aprobados. | `< 0.05` | Mitiga desvíos de alcance y reprocesos costosos en el desarrollo de software. |
| Aprobación PO | % de REQ Aprobados con confirmación digital de aprobación escrita del PO. | `100.00%` | Puerta de control y deslinde de responsabilidad técnico-contractual de SQA. |
| Conformidad ETVX | % de tareas de la matriz ETVX ejecutadas al 100%. | `100.00%` | Certifica la disciplina operacional de la fase bajo CMMI Nivel 2. |

---

## 9. Limitaciones del Plan
*   **Factores Externos:** El nivel de disponibilidad y retroalimentación oportuna por parte del Product Owner para las sesiones de validación técnica conjunta de la lógica BDD.
*   **Alcance Lógico:** Este plan no subsana de forma retroactiva discrepancias lógicas heredadas de las fases previas que no hayan sido formalmente autorizadas en una Solicitud de Cambio (`CR-XXX`).

---

## 10. Referencias

[1] SWEBOK v4.0. _Guía al Cuerpo de Conocimiento de la Ingeniería de Software_, IEEE Computer Society, 2024. Capítulo: Requisitos de Software.

[2] Regan, G. O. (2002). _A Practical Approach to Software Quality_. USA: Springer. (Estructuración de Requisitos e Independencia).

[3] Galin, D. (2004). _Software Quality Assurance: From theory to implementation_. Pearson / Addison-Wesley. (Calidad Contractual e Infraestructura).

[4] CMMI-DEV v2.0. _CMMI para Desarrollo_, Software Engineering Institute. Áreas de proceso: Requirements Management (REQM).

[5] Checklist de Calidad para Requisitos Individuales. [[02-Requisitos/Checklists/CHK-REQ]]  
[6] Checklist de Calidad para la Matriz de Trazabilidad. [[02-Requisitos/Checklists/CHK-RTM]]  
[7] Checklist del Registro de Verificación de Requisitos. [[02-Requisitos/Checklists/CHK-REG]]  

*Aprobación:* Autorizado y verificado digitalmente por el rol responsable bajo el Estándar XookTech v2.0.
