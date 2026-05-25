# Plan de Mejora — Soporte y Mantenimiento de Software

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Soporte técnico y mantenimiento del sistema |
| Documento base | [00-08-Documentacion_Mantenimiento.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/08-Mantenimiento/00-08-Documentacion_Mantenimiento.md) |
| Marco de mejora | CMMI-DEV v2.0 |
| Nivel objetivo | Nivel 2 - Gestionado |
| Versión | 3.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de soporte técnico y mantenimiento post-despliegue en XookTech disciplinado, robusto y estructurado bajo el ciclo Deming (Planear, Hacer, Verificar, Actuar). Este plan busca erradicar la informalidad de los parches directos en el servidor de producción y el soporte verbal, introduciendo bitácoras estructuradas de incidentes, estimaciones previas de impacto técnico, pruebas completas de regresión lógicas en entornos locales controlados y un control de configuración sistemático.

## Tipo de intervención
☒ Mejora de proceso existente  
☐ Implantación de proceso inexistente

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | Recepción verbal e informal de fallos y peticiones. | **M-01** Centralización y clasificación formal en bitácoras de soporte. |
| **H-02** | Modificación directa de código en el servidor sin análisis de impacto. | **M-02** Análisis obligatorio de viabilidad técnica y cotización de cambios. |
| **H-03** | Pase directo a producción sin re-ejecutar pruebas de regresión. | **M-03** Desarrollo aislado en ramas de corrección urgente y pruebas de regresión del Plan Maestro. |
| **H-04** | Cierre de soporte sin control de configuración ni métricas. | **M-04** Cierre de soporte con actualización de la línea base y el Tablero de Calidad. |

---

## 4. Acciones de Mejora

| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Centralización y clasificación en bitácoras de soporte (Planear) | H-01 | Analista de Control | Alta |
| **M-02** | Análisis formal de viabilidad y cotización técnica de cambios (Hacer) | H-02 | Analista de Control | Alta |
| **M-03** | Pruebas de regresión en ramas aisladas de corrección urgente (Verificar) | H-03 | Líder de Desarrollo | Alta |
| **M-04** | Cierre de soporte formal y actualización documental (Actuar) | H-04 | Analista de Control | Alta |

---

### M-01 — Centralización y clasificación en bitácoras de soporte (Planear)
*   **Situación actual:** Los reportes de error se transmiten verbalmente o por chats informales sin control ni priorización técnica (H-01).
*   **Situación propuesta:** Todo incidente se registra formalmente en la bitácora asignándole un folio estructurado (`SOL-YYYY-NNN` para solicitudes, `ERR-YYYY-NNN` para fallas lógicas), tipificándolo (Correctivo, Adaptativo, Evolutivo) y priorizándolo según su impacto operacional.
*   **Justificación:** ISO/IEC 14764 [5] y Regan (2002) [3] afirman que la categorización sistemática del soporte operativo post-entrega es obligatoria para planificar eficientemente los recursos técnicos de mantenimiento.
*   **Artefactos asociados:** [PLT-REG_Solicitudes_Mantenimiento.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/08-Mantenimiento/Plantillas/Registros/PLT-REG_Solicitudes_Mantenimiento.md) y [PLT-REG_Errores_Reportados.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/08-Mantenimiento/Plantillas/Registros/PLT-REG_Errores_Reportados.md)
*   **Evidencia de cumplimiento:** Folios creados en el registro de errores y solicitudes asociados a cada comunicación de soporte técnico del cliente.

---

### M-02 — Análisis formal de viabilidad y cotización técnica de cambios (Hacer)
*   **Situación actual:** Se realizan parches directos de código sin prever impactos en la arquitectura ni estimar plazos técnicos (H-02).
*   **Situación propuesta:** Antes de codificar, el Analista de Control y Cambios coordina la viabilidad y el desarrollador realiza el análisis de impacto técnico. El desarrollador elabora el formato de cotización de cambios estimando las horas requeridas de ingeniería, necesitando la autorización formal por escrito de parte del cliente.
*   **Justificación:** SWEBOK v4 (Mantenimiento de Software) [1] y Daniel Galin [4] definen el análisis de impacto técnico y el cálculo del esfuerzo de modificación como controles preventivos indispensables de la ingeniería de calidad.
*   **Artefacto asociado:** [PLT-FOR_Cotizacion_Cambios.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/08-Mantenimiento/Plantillas/Formatos/PLT-FOR_Cotizacion_Cambios.md)
*   **Evidencia de cumplimiento:** Ficha de cotización `COT-YYYY-NNN` firmada y autorizada digitalmente por el propietario del producto (Product Owner) antes del inicio del desarrollo.

---

### M-03 — Pruebas de regresión en ramas aisladas de corrección urgente (Verificar)
*   **Situación actual:** Las modificaciones de código se suben directamente a la rama principal de producción sin re-ejecutar pruebas lógicas completas (H-03).
*   **Situación propuesta:** Se prohíbe el parche directo. Los desarrollos se codifican en ramas de corrección urgente (`hotfix/`). Antes de su integración, el Analista de Pruebas re-ejecuta de inmediato los Casos de Pruebas de regresión del Plan Maestro correspondientes.
*   **Justificación:** William E. Lewis (2009) [2] promueve las Pruebas de Regresión (Regression Testing) como el único control técnico capaz de certificar que un cambio correctivo no alteró la estabilidad funcional colateral del sistema.
*   **Artefacto asociado:** [CHK-Verificacion_Cambios.md](file:///d:/Proyectos/Baul/Baul/Assignments_V2/01-Proyecto/08-Mantenimiento/Checklists/CHK-Verificacion_Cambios.md)
*   **Evidencia de cumplimiento:** Casos de prueba de regresión re-ejecutados e incluidos en la bitácora técnica de pruebas de la organización, con aprobación firmada en el checklist.

---

### M-04 — Cierre de soporte formal y actualización documental (Actuar)
*   **Situación actual:** Solucionado el problema en caliente, no se actualizan los diagramas técnicos ni el Tablero de Calidad (H-04).
*   **Situación propuesta:** Tras el despliegue de la corrección, el desarrollador actualiza si es necesario los diagramas técnicos modificados y el Analista de Control y Cambios actualiza el Tablero de Calidad de la empresa, cerrando formalmente el ciclo Deming.
*   **Justificación:** CMMI-DEV v2.0 (Gestión de la Configuración - CM) y la disciplina del ciclo continuo exigen mantener la integridad y consistencia de toda la documentación frente a la línea base de configuración modificada.
*   **Artefacto asociado:** N/A (práctica procedimental de mejora)
*   **Evidencia de cumplimiento:** Registro de actualización de diagramas de arquitectura e incremento en el total de métricas consolidadas en el Tablero de Calidad de XookTech.

---

## 5. Limitaciones del Plan
*   **Restricciones de tiempo de máxima urgencia:** Caídas catastróficas del servidor que afecten la integridad de los datos de la empresa y obliguen a actuar de inmediato (aunque el proceso requiere un hotfix rápido, la revisión técnica paso a paso se agilizará de forma excepcional).
*   **Aprobaciones comerciales:** Negativa o lentitud del cliente para firmar o validar por escrito la Cotización de Cambios, lo cual retrasará el inicio del soporte (se debe formalizar contractualmente que sin visto bueno comercial no se inicia el desarrollo técnico).
