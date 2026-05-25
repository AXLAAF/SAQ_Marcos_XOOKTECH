# Gobernanza, Gestión de la Configuración y Plan de Acción — SGC XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Directrices del proyecto, ciclo de vida de desarrollo e historial de hallazgos del SGC.  
**Salidas:** Estructura unificada del vault de Obsidian, control de versiones en Git y Plan de Acción To-Be.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 01 |
| Proceso | Gestión de la Configuración, Gobernanza y Mejora Continua |
| Estándar de referencia | ISO/IEC 12207:2017 §6.2.2 (SCM) / CMMI-DEV v2.0 CM / SWEBOK v4.0 Cap. 5 |
| Versión | 3.0 |
| Fecha | 2026-05-25 |
| Responsable del proceso | Analista de Gobernanza y Diseño |

---

## 2. Propósito y Alcance

### 2.1 Propósito
Definir y mantener la integridad de los entregables y la documentación técnica del proyecto a lo largo de su ciclo de vida, erradicando inconsistencias de versiones mediante auditorías físicas en Obsidian, control de cambios formalizado e inyección del estándar ETVX para garantizar la coherencia de todos los procesos de ingeniería de software.

### 2.2 Alcance
* **Qué cubre:** Estructura física del vault de Obsidian, estándares de nomenclatura de documentos, políticas de ramificación y commits de Git, control de cambios documentales, diagnóstico de brechas (As-Is) y plan de acción de mejora (To-Be) del proceso.
* **Qué NO cubre:** Diseño técnico de arquitectura (Fase 03), pruebas lógicas funcionales (Fase 04), codificación física (Fase 06) ni el despliegue del servidor en producción (Fase 07).

---

## 3. Roles y Responsabilidades

El proceso de SCM se gestiona bajo los siguientes roles despersonalizados:

| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Gobernanza y Diseño | Administra la estructura del vault en Obsidian, audita la consistencia de los wikilinks, resguarda el estándar de control de versiones y autoriza la integración en Git. |
| Líder de Desarrollo | Garantiza el cumplimiento de las políticas de ramificación y del formato de commits en el repositorio de codificación. |
| Equipo de Desarrollo y SQA | Aplican de forma obligatoria las plantillas y checklists del SGC en cada una de sus actividades operacionales. |

---

## 4. Directrices del Proceso (As-Is)

### 4.1 Estructura del Vault de Obsidian
El repositorio de documentación debe organizarse estrictamente en la siguiente estructura de carpetas físicas:
* `/01-Gestion de la configuracion/`: Documentos de gobernanza, estándares y plantillas de inicio.
* `/02-Requisitos/`: Documentación As-Is, plan de mejora de requisitos, plantillas de SRS y especificaciones del sistema.
* `/03-Diseño/`: Documentación de arquitectura As-Is, plan de mejora de diseño, diagramas técnicos y especificación SDD.
* `/04-Pruebas/`: Planes de pruebas, casos de prueba unificados y bitácoras de ejecución técnica.
* `/05-Revisiones_e_inspecciones/`: Informes de revisión por pares y bitácora técnica de inspecciones SQA.
* `/06-Codigo/`: Estándar de codificación de la organización y documentación de la fase de construcción.
* `/07-Despliegue/`: Guía de despliegue, planes de humo y bitácoras de servidores de producción.
* `/08-Mantenimiento/`: Bitácoras de incidentes y cotización de cambios del sistema.

### 4.2 Control de Cambios Documentales
Cualquier modificación o adición de requerimientos del sistema o arquitectura de software debe canalizarse formalmente a través de un folio de cambio `CR-XXX.md` utilizando la plantilla oficial de control de cambios. Un documento de la línea base aprobado no puede modificarse sin un folio `CR-XXX` autorizado por el Product Owner.

### 4.3 Políticas de Control de Versiones en Git
* **Rama Principal:** La rama `main` del repositorio se mantiene exclusivamente en un estado funcional estable y verificado.
* **Ramas de Características:** Todo desarrollo o corrección de tareas se realiza en ramas de desarrollo aisladas (`feature/TAR-YYYY-NNN` o `hotfix/incident-XXX`).
* **Mensajes de Commit:** Es obligatorio utilizar el prefijo del identificador de la tarea para cada confirmación de cambios (ej. `[TAR-2026-001]: descripción concisa en español e imperativo`), garantizando la trazabilidad histórica de la configuración.

---

## 5. Diagnóstico y Plan de Acción de Mejora (To-Be)

Para guiar la transición de los procesos de XookTech hacia el Nivel 2 de CMMI (Gestionado), se establece la siguiente matriz de trazabilidad de hallazgos y acciones de remediación:

### 5.1 Matriz de Trazabilidad de Hallazgos y Mejoras
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende | Prioridad |
|---|---|---|---|
| **H-01** | Desorganización física de los entregables y carpetas de Obsidian. | **M-01** Reestructuración física del vault del SGC y carpetas unificadas. | Alta |
| **H-02** | Ausencia de un estándar unificado para describir el flujo de los procesos. | **M-02** Implantación obligatoria del Estándar ETVX. | Alta |
| **H-03** | Falta de control y trazabilidad de los cambios sobre documentos aprobados. | **M-03** Establecimiento de folios de control de cambios documentales. | Alta |
| **H-04** | Mezcla inconsistente de versiones y ramas directamente en Git sin revisiones. | **M-04** Políticas de ramas aisladas y formato de mensajes de commit. | Alta |

---

### 5.2 Detalle de las Acciones de Mejora

#### M-01 — Reestructuración física del vault del SGC y carpetas unificadas
* **Situación actual:** Los entregables técnicos y de aseguramiento se guardan de forma desorganizada, mezclando borradores con documentos oficiales (H-01).
* **Situación propuesta:** Se establece la estructura física estricta de 8 directorios del SGC en Obsidian. Todo documento de la línea base debe almacenarse exclusivamente en la subcarpeta del proceso correspondiente. Las carpetas `/00-Pendientes/` y `/01-Aprobados/` se utilizan para la segregación de estado del control de cambios.
* **Justificación:** CMMI-DEV v2.0 (Configuration Management - CM) establece que se debe identificar y categorizar cada elemento de configuración bajo una estructura lógica organizada y auditable.
* **Evidencia de cumplimiento:** Directorios físicos creados y organizados de acuerdo al Índice de Procesos.

#### M-02 — Implantación obligatoria del Estándar ETVX
* **Situación actual:** No existe un estándar claro para definir las entradas, tareas, salidas y verificaciones de los procesos del proyecto (H-02).
* **Situación propuesta:** Es obligatorio que todos los procesos definidos en XookTech sigan la estructura ETVX (Entry, Task, Verification, Exit). Cada actividad técnica y de SQA debe detallar sus criterios de entrada, tareas asociadas, criterios de verificación cuantitativos y criterios de salida.
* **Justificación:** SWEBOK v4 establece que la caracterización formal de los procesos de ingeniería garantiza la consistencia, repetibilidad y el control de calidad de los entregables del ciclo de vida.
* **Artefacto asociado:** [[01-SCM-Estandar_ETVX.md]]
* **Evidencia de cumplimiento:** Documentos de proceso del SGC estructurados formalmente bajo el modelo ETVX.

#### M-03 — Establecimiento de folios de control de cambios documentales
* **Situación actual:** Las modificaciones a los requerimientos o al diseño del sistema se realizan directamente sobre los archivos sin autorización formal del PO (H-03).
* **Situación propuesta:** Todo cambio o ajuste de alcance sobre un artefacto ya aprobado de la línea base debe ser solicitado formalmente mediante un folio de cambio `CR-XXX` utilizando la plantilla correspondiente. El cambio debe ser analizado técnicamente e inyectar su evidencia de aprobación escrita antes de aplicarse en el SGC.
* **Justificación:** ISO/IEC 12207 establece que toda alteración del alcance debe someterse a un proceso formal de control de cambios y análisis de impacto para evitar la corrupción de la configuración.
* **Artefacto asociado:** `99-Plantillas_y_Checklists/TEMPLATE-CR.md`
* **Evidencia de cumplimiento:** Registro de solicitudes de cambio `CR-XXX` autorizado e inyectado en el SGC.

#### M-04 — Políticas de ramas aisladas y formato de mensajes de commit
* **Situación actual:** Se realizan commits de forma directa a la rama principal de producción con mensajes ambiguos que eliminan la trazabilidad técnica (H-04).
* **Situación propuesta:** Uso mandatorio de un repositorio centralizado en Git. Todo desarrollo se realiza en ramas de características independientes con el formato `feature/TAR-YYYY-NNN` y cada commit debe incluir el prefijo del identificador de la tarea relacionada.
* **Justificación:** SWEBOK señala que el control de la línea base del código fuente requiere el aislamiento de versiones y la trazabilidad histórica unívoca de cada cambio.
* **Artefacto asociado:** [[02-SCM-Convenciones_Tags.md]]
* **Evidencia de cumplimiento:** Historial de commits y estructura de ramas del repositorio activo en GitHub que implementan las políticas de SCM.

---

## 6. Limitaciones del Plan
* **Resistencia al Cambio:** Integrantes del equipo técnico acostumbrados a flujos informales de desarrollo que omitan de forma discrecional el registro de tareas y folios de control.
* **Limitaciones Administrativas:** Tiempos de aprobación prolongados por parte del Product Owner para validar las solicitudes de cambios comerciales.

---

## 7. Referencias
* [1] ISO/IEC 12207:2017 - Software Configuration Management Process.
* [2] SWEBOK v4.0 Capítulo 5 - Software Configuration Management.
* [3] CMMI-DEV v2.0 - Configuration Management (CM).
