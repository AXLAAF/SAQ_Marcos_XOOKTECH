# Plan de Acción SQA — Gestión de la Configuración

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Gestión de la Configuración y SCM |
| Documento base | [[PROC-SGC.md]] |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-25 |

---

## 2. Objetivo de la Mejora
Establecer un control riguroso e independiente sobre la línea base del proyecto y el SGC. El plan busca erradicar la desorganización de archivos y la inconsistencia de versiones mediante auditorías físicas del vault de Obsidian, control de cambios formalizado e inyección mandatoria del estándar ETVX para garantizar la coherencia de toda la documentación técnica.

## Tipo de intervención
[X] Mejora de proceso existente  
[ ] Implantación de proceso inexistente  

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | Desorganización física de los entregables y carpetas de Obsidian. | **M-01** Reestructuración física del vault del SGC y carpetas unificadas. |
| **H-02** | Ausencia de un estándar unificado para describir el flujo de los procesos. | **M-02** Implantación obligatoria del Estándar ETVX. |
| **H-03** | Falta de control y trazabilidad de los cambios sobre documentos aprobados. | **M-03** Establecimiento de folios de control de cambios documentales. |
| **H-04** | Mezcla inconsistente de versiones y ramas directamente en Git sin revisiones. | **M-04** Políticas de ramas aisladas y formato de mensajes de commit. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Reestructuración física del vault del SGC y carpetas unificadas | H-01 | Analista de Gobernanza y Diseño | Alta |
| **M-02** | Implantación obligatoria del Estándar ETVX | H-02 | Analista de Gobernanza y Diseño | Alta |
| **M-03** | Establecimiento de folios de control de cambios documentales | H-03 | Analista de Control y Cambios | Alta |
| **M-04** | Políticas de ramas aisladas y formato de mensajes de commit | H-04 | Líder de Desarrollo | Alta |

---

### M-01 — Reestructuración física del vault del SGC y carpetas unificadas
* **Situación actual:** Los entregables técnicos y de aseguramiento se guardan de forma desorganizada, mezclando borradores con documentos oficiales (H-01).
* **Situación propuesta:** Se establece la estructura física estricta de 8 directorios del SGC en Obsidian. Todo documento de la línea base debe almacenarse exclusivamente en la subcarpeta del proceso correspondiente. Las carpetas `/00-Pendientes/` y `/01-Aprobados/` se utilizan para la segregación de estado del control de cambios.
* **Justificación:** CMMI-DEV v2.0 (Configuration Management - CM) establece que se debe identificar y categorizar cada elemento de configuración bajo una estructura lógica organizada y auditable.
* **Artefacto asociado:** Estructura física del Vault de Obsidian.
* **Evidencia de cumplimiento:** Directorios físicos creados y organizados de acuerdo al Índice de Procesos.

---

### M-02 — Implantación obligatoria del Estándar ETVX
* **Situación actual:** No existe un estándar claro para definir las entradas, tareas, salidas y verificaciones de los procesos del proyecto (H-02).
* **Situación propuesta:** Es obligatorio que todos los procesos definidos en XookTech sigan la estructura ETVX (Entry, Task, Verification, Exit). Cada actividad técnica y de SQA debe detallar sus criterios de entrada, tareas asociadas, criterios de verificación cuantitativos y criterios de salida.
* **Justificación:** SWEBOK v4 establece que la caracterización formal de los procesos de ingeniería garantiza la consistencia, repetibilidad y el control de calidad de los entregables del ciclo de vida.
* **Artefacto asociado:** [[02-STD-01_Estandar_ETVX.md]]
* **Evidencia de cumplimiento:** Documentos de proceso del SGC estructurados formalmente bajo el modelo ETVX.

---

### M-03 — Establecimiento de folios de control de cambios documentales
* **Situación actual:** Las modificaciones a los requerimientos o al diseño del sistema se realizan directamente sobre los archivos sin autorización formal del PO (H-03).
* **Situación propuesta:** Todo cambio o ajuste de alcance sobre un artefacto ya aprobado de la línea base debe ser solicitado formalmente mediante un folio de cambio `CR-XXX` utilizando la plantilla correspondiente. El cambio debe ser analizado técnicamente e inyectar su evidencia de aprobación escrita antes de aplicarse en el SGC.
* **Justificación:** ISO/IEC 12207 establece que toda alteración del alcance debe someterse a un proceso formal de control de cambios y análisis de impacto para evitar la corrupción de la configuración.
* **Artefacto asociado:** `99-Plantillas_y_Checklists/TEMPLATE-CR.md`
* **Evidencia de cumplimiento:** Registro de solicitudes de cambio `CR-XXX` autorizado e inyectado en el directorio `/08-Mantenimiento/`.

---

### M-04 — Políticas de ramas aisladas y formato de mensajes de commit
* **Situación actual:** Se realizan commits de forma directa a la rama principal de producción con mensajes ambiguos que eliminan la trazabilidad técnica (H-04).
* **Situación propuesta:** Uso mandatorio de un repositorio centralizado en Git. Todo desarrollo se realiza en ramas de características independientes con el formato `feature/TAR-YYYY-NNN` y cada commit debe incluir el prefijo del identificador de la tarea relacionada.
* **Justificación:** SWEBOK señala que el control de la línea base del código fuente requiere el aislamiento de versiones y la trazabilidad histórica unívoca de cada cambio.
* **Artefacto asociado:** [[03-STD-02_Convenciones_Tags.md]]
* **Evidencia de cumplimiento:** Historial de commits y estructura de ramas del repositorio activo en GitHub que implementan las políticas de SCM.

---

## 5. Limitaciones del Plan
* **Resistencia al Cambio:** Integrantes del equipo técnico acostumbrados a flujos informales de desarrollo que omitan de forma discrecional el registro de tareas y folios de control.
* **Limitaciones Administrativas:** Tiempos de aprobación prolongados por parte del Product Owner para validar las solicitudes de cambios comerciales.
