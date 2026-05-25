# Plan de Mejora — Pruebas de Software

## 1. Información General
| Campo           | Detalle                                  |
| --------------- | ---------------------------------------- |
| Proceso         | Pruebas de software                      |
| Documento base  | `04-Documentacion_Pruebas.md`            |
| Marco de mejora | CMMI-DEV v2.0 adaptado a empresa pequeña |
| Nivel objetivo  | Nivel 2 - Gestionado de forma básica     |
| Versión         | 1.0                                      |
| Fecha           | 2026-05-24                               |

---

## 2. Objetivo de la Mejora
Establecer un proceso de pruebas simple y repetible para XookTech. El plan busca reemplazar la revisión informal “a ojo” por una validación mínima documentada, usando casos de prueba cortos, evidencia básica y registro de fallos cuando sea necesario.

---

## 3. Resumen de Hallazgos (Trazabilidad)
| ID Hallazgo | Descripción breve | Acción de Mejora que lo atiende |
|---|---|---|
| **H-01** | No existía un plan de pruebas. | **M-01** Adoptar plan de pruebas ligero. |
| **H-02** | Revisión “a ojo” por el mismo rol que implementaba. | **M-02** Separar revisión local y prueba registrada. |
| **H-03** | No existían casos de prueba formales. | **M-03** Usar casos de prueba mínimos. |
| **H-04** | No se guardaba evidencia estándar. | **M-04** Registrar evidencia mínima de ejecución. |
| **H-05** | Defectos o ajustes comunicados informalmente. | **M-05** Registrar fallos y ajustes detectados. |
| **H-06** | Cambios fuera del alcance inicial sin pruebas específicas. | **M-06** Marcar y probar cambios fuera del alcance inicial. |

---

## 4. Acciones de Mejora
| ID | Acción | Hallazgo que atiende | Responsable | Prioridad |
|---|---|---|---|---|
| **M-01** | Adoptar plan de pruebas ligero | H-01 | Analista de Verificación y Pruebas | Alta |
| **M-02** | Separar revisión local y prueba registrada | H-02 | Líder de Desarrollo e Implementación / Analista de Verificación y Pruebas | Alta |
| **M-03** | Usar casos de prueba mínimos | H-03 | Analista de Verificación y Pruebas | Alta |
| **M-04** | Registrar evidencia mínima de ejecución | H-04 | Analista de Verificación y Pruebas | Alta |
| **M-05** | Registrar fallos y ajustes detectados | H-05 | Analista de Verificación y Pruebas | Alta |
| **M-06** | Marcar y probar cambios fuera del alcance inicial | H-06 | Analista de Verificación y Pruebas | Media |

---

### M-01 — Adoptar plan de pruebas ligero
*   **Situación actual:** Las pruebas se hacían después de implementar, sin plan previo.
*   **Situación propuesta:** Antes de probar una entrega o cambio visible al Cliente, se llena un plan breve indicando qué se probará, qué no se probará, qué datos se usarán y quién lo ejecutará.
*   **Justificación:** CMMI-DEV recomienda planear el trabajo para hacerlo repetible. En este proyecto basta con un plan corto, sin agregar reuniones ni documentación extensa.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Plan_Pruebas.md`
*   **Evidencia de cumplimiento:** Plan de pruebas ligero completado antes de ejecutar una prueba de entrega o cambio visible al Cliente.

---

### M-02 — Separar revisión local y prueba registrada
*   **Situación actual:** El mismo rol que codificaba revisaba visualmente si funcionaba y daba por terminado el cambio.
*   **Situación propuesta:** El Líder de Desarrollo e Implementación puede hacer una revisión local rápida, pero el resultado de prueba debe quedar registrado por el Analista de Verificación y Pruebas.
*   **Justificación:** La separación evita depender sólo de la memoria del Líder de desarrollo o criterio personal, pero se mantiene viable para un equipo pequeño.
*   **Artefacto asociado:** `Plantillas/Registros/PLT-REG_Ejecucion_Pruebas.md`
*   **Evidencia de cumplimiento:** Registro de ejecución con resultado, responsable y fecha.

---

### M-03 — Usar casos de prueba mínimos
*   **Situación actual:** No existían casos formales, por lo que no era fácil repetir la misma validación.
*   **Situación propuesta:** Crear un caso de prueba para cada requisito nuevo o modificado, cambio visible al Cliente, defecto corregido o cambio fuera del alcance inicial.
*   **Justificación:** Un caso de prueba corto permite repetir la revisión sin complicar el proceso.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Caso_Prueba.md`
*   **Evidencia de cumplimiento:** Caso `CP-XX` con pasos, resultado esperado y estado final.

---

### M-04 — Registrar evidencia mínima de ejecución
*   **Situación actual:** No se guardaban capturas, ni notas claras de lo probado.
*   **Situación propuesta:** Toda prueba de requisito, cambio visible al Cliente o defecto corregido debe incluir una evidencia mínima: captura, log o nota de resultado.
*   **Justificación:** La evidencia permite demostrar qué se revisó sin crear reportes largos.
*   **Artefacto asociado:** `Plantillas/Registros/PLT-REG_Ejecucion_Pruebas.md`
*   **Evidencia de cumplimiento:** Registro de ejecución con referencia a captura, log o nota.

---

### M-05 — Registrar fallos y ajustes detectados
*   **Situación actual:** Los fallos y ajustes se hablaban por WhatsApp y podían perderse.
*   **Situación propuesta:** Si una prueba falla o el Cliente pide ajuste, se registra el fallo o ajuste con responsable, estado y prueba relacionada.
*   **Justificación:** Registrar fallos evita repetir errores y ayuda a cerrar pendientes.
*   **Artefacto asociado:** `Plantillas/Registros/PLT-REG_Ejecucion_Pruebas.md` y registro de defectos del proceso de control.
*   **Evidencia de cumplimiento:** Defecto `DEF-XX` o ajuste `AJ-XX` asociado a una prueba.

---

### M-06 — Marcar y probar cambios fuera del alcance inicial
*   **Situación actual:** Algunos requisitos se agregaron después del acuerdo inicial y se trataban como ajustes normales.
*   **Situación propuesta:** Todo cambio fuera del alcance inicial se marca en el plan o caso de prueba y se valida antes de mostrarlo al Cliente.
*   **Justificación:** Estos cambios pueden afectar partes ya aprobadas, por eso requieren una prueba explícita.
*   **Artefacto asociado:** `Plantillas/Formatos/PLT-FOR_Plan_Pruebas.md` y `Plantillas/Formatos/PLT-FOR_Caso_Prueba.md`
*   **Evidencia de cumplimiento:** Campo “Fuera del alcance inicial” marcado y prueba ejecutada.

---

## 5. Limitaciones del Plan
*   **Tamaño del equipo:** No siempre habrá una persona totalmente independiente para ejecutar pruebas; por eso se exige evidencia mínima en lugar de auditoría pesada.
*   **Canal informal del Cliente:** WhatsApp puede seguir siendo el canal principal, pero los cambios relevantes deben resumirse en el plan o caso de prueba.
*   **Alcance del proceso:** Este plan no sustituye control de cambios ni despliegue; sólo valida funcionamiento antes de avanzar.
