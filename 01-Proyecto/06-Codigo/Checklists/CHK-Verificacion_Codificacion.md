# [CHK-Verificacion_Codificacion] Checklist de Calidad — Verificación de Codificación

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Proyecto | |
| Documento / Rama revisada | |
| Folio de Tarea | TAR-YYYY-NNN |
| Programador Responsable | |
| Revisor | |
| Fecha de revisión | |
| Resultado general | ✅ Aprobado / ❌ Rechazado |

---

## Instrucciones
Marcar cada ítem como:
- ✅ Cumple
- ❌ No cumple
- N/A No aplica al proyecto

Todo ítem marcado como ❌ representa una no conformidad que debe ser corregida antes de que la rama sea integrada en `main`.

---

## 1. Completitud de la Tarea y Trazabilidad

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| CT-01 | La funcionalidad implementada cubre al 100% el requisito asociado (`REQ-XXX`). | | |
| CT-02 | Existe un folio de tarea (`TAR-YYYY-NNN`) asignado por el Líder de Desarrollo. | | |
| CT-03 | El mensaje de confirmación (commit) en el control de versiones inicia con el folio de la tarea asociada. | | |

*Referencia: ISO/IEC 12207 §6.4.1.3 (Trazabilidad y registro)*

---

## 2. Nomenclatura y Estándares de Codificación

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| NC-01 | Se utiliza `camelCase` para variables y funciones de manera consistente. | | |
| NC-02 | Se utiliza `PascalCase` para clases y componentes lógicos principales. | | |
| NC-03 | Las constantes están escritas en `SCREAMING_SNAKE_CASE`. | | |
| NC-04 | Se evitan abreviaturas o nombres cortos ambiguos (ej. `usr`, `temp`, `f`). | | |
| NC-05 | Los nombres de funciones comienzan con un verbo de acción y son autodescriptivos. | | |

*Referencia: Estándar de Codificación v2.0 (PLT-FOR_Estandar_Codificacion)*

---

## 3. Idioma y Legibilidad

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| IL-01 | Todo el código, nombres de símbolos y comentarios técnicos están en **Español**. | | |
| IL-02 | Cada archivo de código inicia con el encabezado obligatorio de metadatos en comentarios. | | |

*Referencia: SWEBOK v4 Cap. 3 (Construcción de Software)*

---

## 4. Calidad y Arquitectura (Bajo Acoplamiento)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| AR-01 | Las consultas a base de datos y persistencia están aisladas en Modelos y Repositorios. | | |
| AR-02 | No existe lógica de base de datos dispersa en archivos de Vistas o Interfaces. | | |
| AR-03 | Se ejecutaron los analizadores estáticos locales (linters) y no hay alertas críticas. | | |
| AR-04 | Se cerraron o liberaron explícitamente todos los sockets o recursos de base de datos abiertos. | | |

*Referencia: SWEBOK v4 Cap. 2 y Cap. 3*

---

## Resumen de Hallazgos SQA

| ID Ítem | Observación técnica | Acción correctiva requerida |
|---|---|---|
| | | |

## Decisión de Integración y Ciclo de Reproceso

En caso de que se identifique cualquier no conformidad (ítem marcado con ❌), la integración de la rama queda formalmente **Rechazada**. El programador original recibirá esta lista de hallazgos y dispondrá de un plazo máximo de **24 horas** para corregir las observaciones y volver a someter el código a una nueva inspección independiente.

| Resultado | Criterio |
|---|---|
| ✅ Aprobado | 0 ítems en ❌ |
| ❌ Rechazado | 1 o más ítems en ❌ (Debe iniciar ciclo de reproceso) |

**Decisión:** 
**Firmado por:**
**Fecha:**
