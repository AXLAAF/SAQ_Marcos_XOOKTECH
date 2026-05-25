# Plan de Mejora — Codificación de Software

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Codificación de funcionalidades del sistema |
| Documento base | [00-04-Documentacion_Codificacion.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/06-Codigo/00-04-Documentacion_Codificacion.md) |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de codificación disciplinado y repetible en XookTech. Se busca erradicar la informalidad de las asignaciones verbales, implantar un control estricto de estándares de código, garantizar la revisión independiente de calidad mediante revisiones por pares y asegurar la trazabilidad bidireccional entre los requisitos y la línea base de código.

## Tipo de intervención
☒ Mejora de proceso existente  
☐ Implantación de proceso inexistente

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | La comunicación de asignación de tareas es verbal y no deja evidencia. | **M-01** Establecer la validación obligatoria de requerimientos por escrito antes de codificar. |
| **H-02** | Se inicia la codificación sin contar con insumos estables. | **M-02** Ciclo formal de validación de insumos de entrada. |
| **H-03** | La creación y uso de repositorios de control de versiones no es obligatorio ni unificado. | **M-03** Infraestructura de control de versiones unificada y ramas aisladas. |
| **H-04** | Se integra código sin un análisis previo de impacto arquitectónico. | **M-04** Revisión técnica paso a paso obligatoria antes del acoplamiento. |
| **H-05** | Mensajes de confirmación de cambios (commits) en Git incomprensibles y vagos. | **M-05** Estándar de mensajes de confirmación de cambios descriptivos vinculados a tareas. |
| **H-06** | Estilo de codificación, nomenclatura e idioma inconsistentes en el código. | **M-06** Implantación del Estándar de Codificación de XookTech. |
| **H-07** | Ausencia de verificación independiente o revisión por pares. | **M-07** Inspección formal previa a la integración mediante revisión por pares con ciclo de rechazo. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Validación obligatoria de requerimientos por escrito antes de codificar | H-01 | Desarrollador / Líder técnico | Alta |
| **M-02** | Ciclo formal de validación de insumos de entrada | H-02 | Líder de Desarrollo | Alta |
| **M-03** | Infraestructura de control de versiones unificada y ramas aisladas | H-03 | Líder de Desarrollo | Alta |
| **M-04** | Revisión técnica paso a paso obligatoria antes del acoplamiento | H-04 | Líder de Desarrollo | Media |
| **M-05** | Estándar de mensajes de confirmación de cambios descriptivos vinculados a tareas | H-05 | Líder de Desarrollo | Alta |
| **M-06** | Implantación del Estándar de Codificación de XookTech | H-06 | Líder de Desarrollo | Alta |
| **M-07** | Inspección formal previa a la integración mediante revisión por pares con ciclo de rechazo | H-07 | Revisor independiente | Alta |

---

### M-01 — Validación obligatoria de requerimientos por escrito antes de codificar
*   **Situación actual:** Las tareas se asignan verbalmente sin dejar evidencia técnica de lo que se solicitó (H-01).
*   **Situación propuesta:** Se establece como condición obligatoria para iniciar cualquier desarrollo que la tarea esté registrada por escrito en el Registro de Tareas del proceso de Gestión de Proyectos. El programador actuará como filtro, negándose a codificar requerimientos puramente verbales.
*   **Justificación:** CMMI-DEV v2.0 (Planificación y Control del Trabajo) e ISO/IEC 12207 establecen que el trabajo debe iniciarse únicamente sobre especificaciones de entrada autorizadas y registradas por escrito.
*   **Artefacto asociado:** N/A (se consume el registro de Gestión de Proyectos)
*   **Evidencia de cumplimiento:** Registro de Tareas de Gestión de Proyectos completo con folios `TAR-YYYY-NNN` y requisitos `REQ-XXX` asociados para cada tarea activa en desarrollo.

---

### M-02 — Ciclo formal de validación de insumos de entrada
*   **Situación actual:** El programador inicia la escritura de código sin contar con especificaciones estables o claras (H-02).
*   **Situación propuesta:** Antes de escribir código, el desarrollador debe verificar la suficiencia de los insumos (requisitos y diseños). Si no existen o son deficientes, se notifica al líder técnico y se suspende la actividad de codificación.
*   **Justificación:** ISO/IEC 12207 §6.4.1.2 establece que toda actividad del ciclo de vida debe validar que sus insumos sean conformes y suficientes antes de su utilización.
*   **Artefacto asociado:** N/A (validación procedimental inline)
*   **Evidencia de cumplimiento:** Bitácora de incidencias o registro de tareas que documente la suspensión o confirmación de suficiencia de insumos antes de la fecha de inicio del desarrollo, verificado en la lista general de codificación.

---

### M-03 — Infraestructura de control de versiones unificada y ramas aisladas
*   **Situación actual:** El uso de repositorios es opcional e individual, arriesgando pérdida de código y desorganización de versiones (H-03).
*   **Situación propuesta:** Es obligatorio inicializar un repositorio Git desde el inicio del proyecto, manteniendo la rama principal en un estado funcional estable y desarrollando cada tarea en una rama aislada (`feature/`).
*   **Justificación:** SWEBOK v4 Cap. 5 (Gestión de la Configuración del Software) establece el control estricto de la línea base de código como un requisito crítico de calidad.
*   **Artefacto asociado:** N/A (política de infraestructura)
*   **Evidencia de cumplimiento:** Repositorio Git centralizado activo con ramas activas de características `feature/TAR-YYYY-NNN` y protección de integración directa sobre `main`, verificado mediante el checklist general del proceso.

---

### M-04 — Revisión técnica paso a paso obligatoria antes del acoplamiento
*   **Situación actual:** Se añade código sin evaluar las dependencias o el impacto sobre los componentes arquitectónicos existentes (H-04).
*   **Situación propuesta:** Antes de escribir el código de acoplamiento, el programador debe analizar la lógica preexistente y realizar una revisión técnica de dependencias con el responsable de diseño para asegurar la consistencia.
*   **Justificación:** SWEBOK v4 Cap. 3 (Construcción de Software) establece que el análisis de dependencias de interfaces de componentes disminuye fallos de integración.
*   **Artefacto asociado:** N/A (práctica procedimental)
*   **Evidencia de cumplimiento:** Campo de comentarios técnicos completo en el Registro de Tareas indicando el análisis de dependencias de interfaces verificado en el checklist de codificación.

---

### M-05 — Estándar de mensajes de confirmación de cambios descriptivos vinculados a tareas
*   **Situación actual:** Los mensajes de envío en el repositorio son ambiguos (ej. "avance", "fix") eliminando la trazabilidad de la línea base (H-05).
*   **Situación propuesta:** Todo mensaje de envío en Git debe citar obligatoriamente el folio de la tarea (ej: `TAR-2025-001: Se agrega validación de correo...`).
*   **Justificación:** ISO/IEC 12207 requiere que los registros de cambio de configuración sean legibles, comprensibles y trazables a sus fuentes de origen.
*   **Artefacto asociado:** N/A (convención operativa)
*   **Evidencia de cumplimiento:** Historial de commits de Git que implementa de forma unívoca el prefijo `TAR-YYYY-NNN` en el repositorio, verificado a través del checklist de revisión por pares.

---

### M-06 — Implantación del Estándar de Codificación de XookTech
*   **Situación actual:** El código se escribe con estilos personales, mezclando idiomas y nomenclaturas inconsistentes (H-06).
*   **Situación propuesta:** Uso mandatorio del Estándar de Codificación que define el uso estricto de `camelCase` para variables/funciones, nombres en español y explicitación completa de símbolos lógicos.
*   **Justificación:** ISO/IEC 25010 (Mantenibilidad de Software) y SWEBOK v4 Cap. 3 señalan que los estándares de codificación mejoran drásticamente la capacidad de análisis y modificación del código fuente.
*   **Artefacto asociado:** [PLT-FOR_Estandar_Codificacion.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/06-Codigo/Plantillas/Formatos/PLT-FOR_Estandar_Codificacion.md)
*   **Evidencia de cumplimiento:** Archivos de código fuente que inician con el encabezado de metadatos obligatorio y respetan las directrices del formato, verificado bajo el checklist de calidad.

---

### M-07 — Inspección formal previa a la integración mediante revisión por pares con ciclo de rechazo
*   **Situación actual:** El código se integra directamente sin ninguna revisión independiente ni filtro de calidad objetivo (H-07).
*   **Situación propuesta:** Integración de ramas sujeta a la aprobación de la lista de verificación completada por otro programador del equipo.
*   **Ciclo de rechazo y reproceso:** Si el revisor califica cualquier ítem obligatorio como `No cumple`, la integración de la rama se rechaza formalmente. El programador original recibe la lista de observaciones y dispone de un plazo máximo de 24 horas para corregir las no conformidades y volver a someter el código a revisión técnica.
*   **Justificación:** CMMI-DEV v2.0 PPQA (Procesos de Aseguramiento de Calidad) e IEEE 1028-2008 establecen la inspección por pares como la práctica más de costo-eficiente de control de defectos.
*   **Artefacto asociado:** [CHK-Verificacion_Codificacion.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/06-Codigo/Checklists/CHK-Verificacion_Codificacion.md)
*   **Evidencia de cumplimiento:** Archivos de listas de verificación completadas y firmadas digitalmente por el Revisor y el Programador asociadas a cada solicitud de merge de la rama.

---

## 5. Limitaciones del Plan
*   **Factores externos no controlables:** La resistencia al cambio por parte de programadores externos que no estén acostumbrados a procesos disciplinados de calidad.
*   **Alcance tecnológico:** Este plan no corrige de forma automática errores de lógica o violaciones arquitectónicas preexistentes en los módulos heredados que no sean modificados durante la ejecución de las nuevas tareas.
