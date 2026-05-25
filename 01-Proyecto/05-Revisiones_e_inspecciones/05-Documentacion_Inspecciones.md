# Proceso de Revisiones e Inspecciones — XookTech

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 05 |
| Proceso | Revisiones e inspecciones de artefactos |
| Estándar de referencia | ISO/IEC 12207 - Aseguramiento de calidad y verificación |
| Versión | 1.0 |
| Fecha | 2026-05-24 |
| Responsable del proceso | Analista de Control y Cambios |

---

## 2. Propósito
> Derivado de ISO/IEC 12207.
> Este proceso tiene como propósito revisar artefactos importantes del proyecto antes de usarlos como base para desarrollo, pruebas o entrega al Cliente, evitando errores básicos de claridad, trazabilidad y completitud.

## 3. Alcance
*   **Qué cubre:** La revisión ligera de requisitos, plan de pruebas, casos de prueba, informes de ejecución y cambios fuera del alcance inicial cuando afecten calidad o trazabilidad.
*   **Qué NO cubre:** Control de cambios completo, auditorías externas, revisión formal de código fuente ni aprobación comercial del Cliente.

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Control y Cambios | Coordina la inspección ligera, aplica checklist y registra hallazgos. |
| Autor del artefacto | Atiende observaciones y corrige el documento revisado. |
| Analista de Verificación y Pruebas | Apoya cuando el artefacto revisado sea plan o caso de prueba. |
| Líder de Desarrollo e Implementación | Atiende observaciones que afecten código o comportamiento del sistema. |
| Cliente | Puede dar visto bueno funcional, pero no realiza inspección SQA interna. |

## 5. Entradas
| Entrada | Origen | Formato actual |
|---|---|---|
| Requisitos o cambios | Reunión inicial, WhatsApp o Cliente | Markdown o comunicación informal |
| Plan de pruebas | Proceso de Pruebas | Markdown |
| Casos de prueba | Proceso de Pruebas | Markdown |
| Informe de ejecución | Proceso de Pruebas | Markdown |
| Observaciones del Cliente | WhatsApp o demostración | Comentario informal |

## 6. Salidas (Artefactos)
| Artefacto | Destino | Formato actual |
|---|---|---|
| Informe de inspección | Aseguramiento de Calidad | Markdown |
| Registro de hallazgos | Aseguramiento de Calidad / proceso relacionado | Markdown |
| Checklist de verificación | Carpeta de checklists | Markdown |
| Artefacto corregido | Proceso correspondiente | Markdown |
| Decisión de inspección | Informe de inspección | Aprobado / Rechazado |

## 7. Pasos del Proceso
Cómo se hacía originalmente en la empresa

1.  **Revisión informal del avance:** El cambio o documento se revisaba de forma rápida, sin checklist ni registro de hallazgos.
2.  **Validación con el Cliente:** Si el avance parecía correcto, se mostraba al Cliente por WhatsApp o demostración informal.
3.  **Ajustes por conversación:** Las observaciones se atendían directamente, sin separar hallazgos internos de comentarios del Cliente.
4.  **Ausencia de checklist:** No existía una lista mínima para revisar requisitos, pruebas o entregables antes de usarlos.
5.  **Cierre no documentado:** No quedaba decisión formal de aprobación, rechazo o aprobación con observaciones.

## 8. Herramientas Utilizadas
| Herramienta | Propósito dentro del proceso |
|---|---|
| WhatsApp | Comunicación de avances y observaciones del Cliente. |
| Obsidian / Markdown | Documentación propuesta de informes, hallazgos y checklists. |
| Revisión visual del prototipo | Validación informal del comportamiento del sistema. |

## 9. Problemas y Hallazgos Identificados
Esta sección resume las brechas del proceso original frente a prácticas básicas de calidad.

| ID | Hallazgo | Criterio violado |
|---|---|---|
| **H-01** | No existía proceso formal de inspecciones. | ISO 12207 - Aseguramiento de calidad |
| **H-02** | No había roles claros de autor, revisor y responsable de cierre. | CMMI-DEV v2.0 - PPQA |
| **H-03** | No se aplicaban checklists de revisión. | CMMI-DEV v2.0 - Verificación |
| **H-04** | No se registraban hallazgos de forma estándar. | ISO 12207 - Evidencia de revisión |
| **H-05** | No existía decisión formal de aprobación o rechazo. | CMMI-DEV v2.0 - Aseguramiento de calidad |
| **H-06** | La validación del Cliente se confundía con inspección interna. | CMMI-DEV v2.0 - Independencia de revisión |

## 10. Métricas Actuales
*   **Estado de las métricas:** El proceso original de inspecciones no cuenta con métricas formales.
*   **Diagnóstico:** No se mide cuántos artefactos se revisaron, cuántos hallazgos se detectaron, cuántos fueron cerrados ni qué documentos quedaron aprobados antes de usarse.
