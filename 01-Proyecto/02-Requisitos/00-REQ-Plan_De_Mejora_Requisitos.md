# Plan de Mejora — Requisitos de Software

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Especificación y Gestión de Requisitos de Software |
| Documento base | [[00-REQ-Documentacion_Requisitos.md]] |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de requisitos disciplinado y repetible en XookTech. El plan busca eliminar los acuerdos verbales mediante Reportes de Junta, especificar con escenarios BDD en formatos estándar, organizar físicamente la línea base en Obsidian, asegurar la trazabilidad bidireccional mediante una Matriz RTM y realizar auditorías independientes de calidad con registros formales.

## Tipo de intervención
[X] Mejora de proceso existente  
[ ] Implantación de proceso inexistente  

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | Captura informal de requerimientos vía WhatsApp sin evidencia técnica. | **M-01** Agendamiento formal y uso obligatorio de Reportes de Junta. |
| **H-02** | Ausencia de folios de entrada y registro único de la necesidad de negocio. | **M-02** Inicialización y registro estructurado de requerimientos técnicos. |
| **H-03** | Redacción técnica ambigua en lenguaje natural libre sin límites ni cotas numéricas. | **M-03** Especificación técnica estructurada en formato unificado BDD. |
| **H-04** | Inicio de la programación de Flask/OpenCV sin contar con la validación formal escrita del PO. | **M-04** Sesión de validación técnica y evidencia de aprobación digital explícita. |
| **H-05** | Mezcla física de archivos pendientes y aprobados en carpetas desorganizadas. | **M-05** Segregación física obligatoria de estados en Obsidian. |
| **H-06** | Inexistencia de trazabilidad bidireccional entre requerimientos, diseño y pruebas. | **M-06** Integración y mantenimiento de Matriz RTM bidireccional unificada. |
| **H-07** | Ausencia de auditorías de SQA independientes y de registros de calidad formales. | **M-07** Auditorías de SQA independientes y Registro de Verificación SQA. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Agendamiento formal y uso obligatorio de Reportes de Junta | H-01 | Analista de Requisitos | Alta |
| **M-02** | Inicialización y registro estructurado de requerimientos técnicos | H-02 | Analista de Requisitos | Alta |
| **M-03** | Especificación técnica estructurada en formato unificado BDD | H-03 | Analista de Requisitos | Alta |
| **M-04** | Sesión de validación técnica y evidencia de aprobación digital explícita | H-04 | Analista de Requisitos | Alta |
| **M-05** | Segregación física obligatoria de estados en Obsidian | H-05 | Analista de Requisitos | Alta |
| **M-06** | Integración y mantenimiento de Matriz RTM bidireccional unificada | H-06 | Analista de Requisitos | Media |
| **M-07** | Auditorías de SQA independientes y Registro de Verificación SQA | H-07 | Analista de Control y Cambios | Alta |

---

### M-01 — Agendamiento formal y uso obligatorio de Reportes de Junta
* **Situación actual:** La captura y asignación de requerimientos es informal, por mensajes rápidos o llamadas que no dejan evidencia técnica (H-01).
* **Situación propuesta:** Las sesiones con el Product Owner se programan mediante Google Calendar o Teams con 24 horas de anticipación, adjuntando la agenda de temas. Durante la reunión, el Analista de Requisitos captura los temas, la asistencia, los acuerdos, sus responsables y fechas límite de entrega en la plantilla oficial [[PLT-FOR_Reporte_Junta.md]].
* **Justificación:** CMMI y el estándar ISO/IEC 12207 exigen iniciar los trabajos de ingeniería de software a partir de sesiones de levantamiento de requisitos planificadas y documentadas formalmente.
* **Artefacto asociado:** [[PLT-FOR_Reporte_Junta.md]]
* **Evidencia de cumplimiento:** Minuta de junta completada en Obsidian con la evidencia de aprobación digital del Product Owner o el enlace de la grabación en la nube de la sesión.

---

### M-02 — Inicialización y registro estructurado de requerimientos técnicos
* **Situación actual:** Falta de un registro único o folios que permitan dar seguimiento a las necesidades de negocio (H-02).
* **Situación propuesta:** Por cada necesidad identificada en la minuta de junta, se genera una ficha física independiente en Obsidian asignándole un código identificador incremental `REQ-XXX` (desde `REQ-001` en adelante). El archivo se crea con metadatos de control (Fecha de creación, autor, prioridad y versión 1.0) y la etiqueta `#estado/pendiente`.
* **Justificación:** SWEBOK v4 establece que la identificación unívoca de cada requisito es la base para el control de la configuración y la línea base del software.
* **Artefacto asociado:** N/A (procedimiento operativo)
* **Evidencia de cumplimiento:** Creación de la nota física en la carpeta `/02-Requisitos/00-Pendientes/` con el código secuencial y metadatos completos.

---

### M-03 — Especificación técnica estructurada en formato unificado BDD
* **Situación actual:** Los requisitos se redactan de manera ambigua y descriptiva en lenguaje natural sin cotas técnicas precisas (H-03).
* **Situación propuesta:** Especificar los requisitos funcionales mediante las plantillas oficiales [[PLT-FOR_Especificacion_SRS.md]] o [[PLT-FOR_Historia_Usuario.md]] incorporando cotas numéricas exactas en las reglas de negocio (ej. tamaño máximo de archivos 10 MB, formatos JPEG/PNG) y modelando los escenarios de aceptación detallados mediante el formato BDD (`Dado`, `Cuando`, `Entonces`, sin usar emojis), cubriendo el flujo principal, alternativos y flujos de error.
* **Justificación:** El uso de lenguaje BDD y parámetros cuantitativos elimina la subjetividad, garantizando que los programadores construyan interfaces y algoritmos sin ambigüedades y que los probadores diseñen casos de prueba objetivos.
* **Artefacto asociado:** [[PLT-FOR_Especificacion_SRS.md]] y [[PLT-FOR_Historia_Usuario.md]]
* **Evidencia de cumplimiento:** Ficha del requerimiento (`REQ-XXX.md`) redactada con las reglas técnicas acotadas y escenarios de aceptación BDD completos.

---

### M-04 — Sesión de validación técnica y evidencia de aprobación digital explícita
* **Situación actual:** Se inicia la codificación directa en Flask y OpenCV sin la validación y aceptación formal de los requisitos por parte del cliente (H-04).
* **Situación propuesta:** El Analista de Requisitos presenta los escenarios BDD detallados y los prototipos de interfaz en una sesión técnica conjunta con el PO. Al obtener su acuerdo de alcance, se captura su aprobación por escrito (ej. correo electrónico o confirmación digital) y se almacena en la sección "Evidencias de Aprobación" de la ficha del requerimiento.
* **Justificación:** La validación formal de requerimientos previa al desarrollo mitiga las desviaciones del alcance contratado y evita reprocesos de ingeniería.
* **Artefacto asociado:** N/A (validación técnica)
* **Evidencia de cumplimiento:** Sección "Evidencias de Aprobación" de la ficha `REQ-XXX.md` completa con el texto o captura del correo de aceptación del Product Owner.

---

### M-05 — Segregación física obligatoria de estados en Obsidian
* **Situación actual:** Los requerimientos se almacenan en un directorio desorganizado que mezcla de forma inconsistente fichas en borrador con requisitos aprobados (H-05).
* **Situación propuesta:** Los archivos en desarrollo se resguardan en `/02-Requisitos/00-Pendientes/`. Una vez que el requerimiento cuenta con la firma del PO, su metadato de Obsidian cambia a `#estado/aprobado` y el Analista de Requisitos traslada físicamente el archivo al directorio `/02-Requisitos/01-Aprobados/`.
* **Justificación:** La separación física de los estados resguarda la inmutabilidad de la Línea Base de la configuración de software contra cambios informales.
* **Artefacto asociado:** Directorios `/02-Requisitos/00-Pendientes/` y `/02-Requisitos/01-Aprobados/`
* **Evidencia de cumplimiento:** Estructura física del directorio de Requisitos organizada con los archivos firmados ubicados exclusivamente en la carpeta de aprobados.

---

### M-06 — Integración y mantenimiento de Matriz RTM bidireccional unificada
* **Situación actual:** No hay trazabilidad entre el origen de los requerimientos, los componentes de diseño y los casos de prueba de calidad (H-06).
* **Situación propuesta:** Mantener actualizada la Matriz RTM general del proyecto. Al aprobarse un requerimiento, el Analista de Requisitos mapea su relación con la fuente (Contrato o Cambio `CR-XXX`) y reserva mediante wikilinks interactivos de Obsidian los enlaces hacia su componente en el SDD de la Fase 03 y a sus casos de prueba de la Fase 04.
* **Justificación:** CMMI REQM SP 1.4 establece que la trazabilidad bidireccional completa es fundamental para asegurar la cobertura total de desarrollo y simplificar el análisis de impacto.
* **Artefacto asociado:** Matriz de Trazabilidad RTM (Tabla indexada en el Índice de Procesos)
* **Evidencia de cumplimiento:** Columna de diseño y pruebas de la Matriz RTM en [[00-Indice_Procesos.md]] actualizada con el 100% de los wikilinks clickables activos.

---

### M-07 — Auditorías de SQA independientes y Registro de Verificación SQA
* **Situación actual:** Las revisiones de los requerimientos antes de programar son subjetivas y no dejan registros del aseguramiento de calidad (H-07).
* **Situación propuesta:** El Analista de Control y Cambios actúa de manera independiente auditando el paquete de requisitos con el checklist [[CHK-Verificacion_Requisitos.md]]. Si cumple con el 100.00% de conformidad, se firma el Registro de Verificación SQA del proyecto [[PLT-REG_Verificacion_Requisitos.md]] congelando el requerimiento en la Línea Base. Si detecta no conformidades, rechaza la liberación del paquete y otorga al equipo de requerimientos un plazo de 24 horas para corregir los hallazgos y re-evaluar.
* **Justificación:** CMMI PPQA e IEEE Std 830 conceptualizan el aseguramiento de calidad como un proceso de auditoría independiente que garantiza que los productos entregados cumplen con los estándares metodológicos de la organización.
* **Artefacto asociado:** [[CHK-Verificacion_Requisitos.md]] y [[PLT-REG_Verificacion_Requisitos.md]]
* **Evidencia de cumplimiento:** Registro de Verificación SQA del proyecto completado e inyectado con el resultado de la auditoría.

---

## 5. Indicadores de Éxito
| Indicador | Métrica | Meta | Justificación de la Meta |
|---|---|---|---|
| Cobertura de Trazabilidad | % de requisitos en la RTM con enlaces a diseño y pruebas. | `100.00%` | Garantiza cobertura total de desarrollo y pruebas sin dejar brechas. |
| Estabilidad de Requisitos | Defectos de ambigüedad detectados por SQA / Total de REQ Aprobados. | `< 0.05` | Mitiga desvíos de alcance y reprocesos costosos en Flask/OpenCV. |
| Aprobación del PO | % de requisitos aprobados con evidencia de confirmación escrita. | `100.00%` | Puerta de control y deslinde de responsabilidad técnico-contractual del equipo. |
| Auditoría de Calidad | % de requisitos aprobados liberados con checklist SQA aprobado. | `100.00%` | Certifica la disciplina operacional de la fase bajo CMMI Nivel 2. |

---

## 6. Limitaciones del Plan
* **Disponibilidad del Product Owner:** La velocidad del proceso depende directamente del tiempo de respuesta y la disponibilidad del PO para programar las sesiones de validación conjunta.
* **Inconsistencias Heredadas:** Este plan no subsana discrepancias o ambigüedades heredadas de contratos previos que no hayan sido procesados formalmente mediante una Solicitud de Cambio (`CR-XXX`).
* **Adaptación Metodológica:** La necesidad de capacitaciones iniciales sobre el lenguaje estructurado BDD y el uso formal de herramientas de Obsidian por parte de nuevos integrantes del equipo técnico.
