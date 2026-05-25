# Plan de Mejora — Revisiones e Inspecciones

## 1. Información General
| Campo | Detalle |
|---|---|
| Proceso | Revisiones e inspecciones de artefactos |
| Documento base | `00-05-Documentacion_Inspecciones.md` |
| Marco de mejora | CMMI-DEV v2.0 adaptado a empresa pequeña |
| Nivel objetivo | Nivel 2 - Gestionado de forma básica |
| Versión | 1.0 |
| Fecha | 2026-05-24 |

---

## 2. Objetivo de la Mejora
Establecer un proceso de inspección ligero para XookTech. El plan busca revisar los artefactos básicos del proyecto antes de usarlos, separando la revisión interna de calidad del visto bueno funcional del Cliente.

## Tipo de intervención
[ ] Mejora de proceso existente  
[x] Implantación de proceso inexistente

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | No existía proceso formal de inspecciones. | **M-01** Definir cuándo aplicar inspección ligera. |
| **H-02** | No había roles claros de revisión. | **M-02** Registrar autor, revisor y responsable de cierre. |
| **H-03** | No se aplicaban checklists. | **M-03** Usar un checklist único de verificación. |
| **H-04** | No se registraban hallazgos. | **M-04** Registrar hallazgos y acciones correctivas. |
| **H-05** | No existía decisión formal de aprobación. | **M-05** Definir decisión final de inspección. |
| **H-06** | Se confundía validación del Cliente con inspección interna. | **M-06** Separar inspección SQA y visto bueno del Cliente. |

---

## 4. Acciones de Mejora
| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Definir cuándo aplicar inspección ligera | H-01 | Analista de Control y Cambios | Alta |
| **M-02** | Registrar autor, revisor y responsable de cierre | H-02 | Analista de Control y Cambios | Alta |
| **M-03** | Usar un checklist único de verificación | H-03 | Analista de Control y Cambios | Alta |
| **M-04** | Registrar hallazgos y acciones correctivas | H-04 | Analista de Control y Cambios | Alta |
| **M-05** | Definir decisión final de inspección | H-05 | Analista de Control y Cambios | Alta |
| **M-06** | Separar inspección SQA y visto bueno del Cliente | H-06 | Analista de Control y Cambios | Media |

---

### M-01 — Definir cuándo aplicar inspección ligera
*   **Situación actual:** No existía una regla clara para decidir qué documentos debían revisarse (H-01).
*   **Situación propuesta:** Aplicar inspección ligera a requisitos nuevos o modificados, plan de pruebas, casos de prueba usados para entregas y cambios fuera del alcance inicial.
*   **Justificación:** CMMI-DEV recomienda revisar productos de trabajo para detectar problemas temprano. En este proyecto se limita a documentos que afectan directamente la entrega.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Informe_Inspeccion.md`
*   **Evidencia de cumplimiento:** Informe de inspección o nota de revisión asociada al artefacto revisado.

---

### M-02 — Registrar autor, revisor y responsable de cierre
*   **Situación actual:** La misma persona podía crear, revisar y cerrar sin dejar claro qué responsabilidad estaba cumpliendo (H-02).
*   **Situación propuesta:** Cada informe debe indicar autor del artefacto, revisor y responsable de cierre. Si una persona cubre varios roles, se registra igual.
*   **Justificación:** Para un equipo pequeño no se exige independencia total, pero sí claridad de responsabilidades.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Informe_Inspeccion.md`
*   **Evidencia de cumplimiento:** Informe con campos de autor, revisor y responsable de cierre completos.

---

### M-03 — Usar un checklist único de verificación
*   **Situación actual:** No existía checklist formal de revisión (H-03).
*   **Situación propuesta:** Usar `CHK-Verificacion_Inspecciones.md` como filtro mínimo para revisar artefactos antes de aprobarlos.
*   **Justificación:** Un checklist único evita crear varias listas innecesarias y mantiene el proceso simple.
*   **Artefacto asociado:** `Checklists/CHK-Verificacion_Inspecciones.md`
*   **Evidencia de cumplimiento:** Checklist completado con estado y observaciones.

---

### M-04 — Registrar hallazgos y acciones correctivas
*   **Situación actual:** Las observaciones se comunicaban por conversación o WhatsApp y podían perderse (H-04).
*   **Situación propuesta:** Todo hallazgo se registra con descripción, responsable, acción correctiva y estado.
*   **Justificación:** Registrar hallazgos permite cerrar pendientes sin agregar complejidad innecesaria.
*   **Artefacto asociado:** `Plantillas/Registros/PLT-REG_Hallazgos_Inspeccion.md`
*   **Evidencia de cumplimiento:** Registro de hallazgos actualizado.

---

### M-05 — Definir decisión final de inspección
*   **Situación actual:** No existía una decisión formal sobre si un artefacto podía usarse (H-05).
*   **Situación propuesta:** Cerrar cada inspección como `Aprobado`, `Aprobado con observaciones` o `Rechazado`.
*   **Justificación:** Una decisión clara evita usar documentos incompletos como base de trabajo.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Informe_Inspeccion.md`
*   **Evidencia de cumplimiento:** Informe con decisión final y fecha de revisión.

---

### M-06 — Separar inspección SQA y visto bueno del Cliente
*   **Situación actual:** El visto bueno del Cliente se trataba como si fuera revisión interna de calidad (H-06).
*   **Situación propuesta:** Primero se realiza inspección interna ligera; después, si aplica, se muestra al Cliente para validación funcional.
*   **Justificación:** El Cliente valida si el resultado le sirve, pero el equipo debe revisar calidad, claridad y trazabilidad.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Informe_Inspeccion.md`
*   **Evidencia de cumplimiento:** Informe interno cerrado antes de solicitar visto bueno del Cliente.

---

## 5. Indicadores de Éxito
| Indicador | Métrica | Meta | Justificación de la Meta |
|---|---|---|---|
| Cobertura de inspección | % de artefactos definidos con informe o checklist. | `≥ 90%` | Permite margen para ajustes menores sin impacto. |
| Hallazgos trazados | % de hallazgos con responsable y estado. | `100%` | Todo hallazgo debe tener seguimiento. |
| Decisión documentada | % de inspecciones con decisión final. | `100%` | Evita usar artefactos sin cierre. |
| Separación de validación | % de entregas revisadas internamente antes del visto bueno del Cliente. | `≥ 90%` | Mantiene calidad sin bloquear casos simples. |

---

## 6. Limitaciones del Plan
*   **Tamaño del equipo:** No siempre habrá un revisor totalmente independiente; por eso se exige checklist y evidencia mínima.
*   **Alcance del proceso:** Este plan no cubre control de cambios completo ni auditorías externas.
*   **Canal informal del Cliente:** WhatsApp puede seguir usándose, pero las observaciones que afecten calidad deben registrarse como hallazgos o ajustes.
