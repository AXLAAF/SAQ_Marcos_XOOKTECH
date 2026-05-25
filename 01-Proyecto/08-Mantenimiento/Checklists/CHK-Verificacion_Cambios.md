# [CHK-Verificacion_Cambios] Checklist de Calidad — Verificación de Cambios y Soporte

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Proyecto | |
| Folio de Incidente (SOL / ERR) | SOL-YYYY-NNN / ERR-YYYY-NNN |
| Versión de la Rama de Corrección | correccion/ |
| Analista Revisor | |
| Fecha de revisión | |
| Resultado general | ✅ Aprobado / ❌ Rechazado |

---

## Instrucciones
Marcar cada ítem como:
- ✅ Cumple
- ❌ No cumple
- N/A No aplica al proyecto

Ninguna corrección de soporte post-despliegue se integrará en la rama principal `main` si tiene algún ítem marcado con ❌.

---

## 1. Fase de Planeación y Trazabilidad

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| PT-01 | El incidente cuenta con folio único en la bitácora de soporte. | | |
| PT-02 | Se documentó por escrito el análisis de impacto técnico del cambio. | | |
| PT-03 | Se emitió y aprobó el formato de cotización de cambios por el propietario del producto (Product Owner). | | |

*Referencia: ISO/IEC 14764 §5.2 (Análisis de Cambios) / CMMI-DEV v2.0*

---

## 2. Fase de Construcción Segura

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| CS-01 | Los cambios se implementaron en una rama de corrección urgente aislada. | | |
| CS-02 | El código fuente modificado cumple íntegramente el Estándar de Codificación de XookTech. | | |
| CS-03 | Se incluyeron comentarios explicativos en los módulos lógicos modificados. | | |

*Referencia: SWEBOK v4 Cap. 3 (Construcción de Software) / Gobernanza del control de versiones*

---

## 3. Fase de Verificación y Regresión

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| VR-01 | Se re-ejecutaron de forma exitosa los Casos de Pruebas de regresión del Plan Maestro. | | |
| VR-02 | El fallo original quedó 100% resuelto y verificado bajo condiciones de prueba reales. | | |
| VR-03 | Los cambios no introdujeron efectos colaterales adversos en otros módulos del sistema. | | |

*Referencia: William E. Lewis (2009) / Estándares de Pruebas de Regresión*

---

## 4. Fase de Cierre Técnico (Ciclo de Mejora Continua)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| CD-01 | Se actualizó el estado del incidente a "Listo" en la bitácora de soporte. | | |
| CD-02 | Se actualizaron los diagramas técnicos o inventario de módulos afectados por el cambio. | | |
| CD-03 | Las métricas del Tablero (Dashboard) de Calidad de XookTech se actualizaron con el cierre del incidente. | | |

*Referencia: CMMI-DEV v2.0 (Gestión de la Configuración - CM) / Ciclo Deming (Planear, Hacer, Verificar, Actuar)*

---

## Resumen de Hallazgos SQA

| ID Ítem | Observación técnica | Acción correctiva requerida |
|---|---|---|
| | | |

## Decisión de Integración de Cambio y Ciclo de Reproceso

En caso de que se identifique cualquier no conformidad (ítem marcado con ❌), la integración de la rama queda formalmente **Rechazada**. El programador original recibirá esta lista de observaciones y dispondrá de un plazo máximo de **24 horas** para corregir las desviaciones y volver a someter el cambio a una nueva inspección técnica.

| Resultado | Criterio |
|---|---|
| ✅ Aprobado | 0 ítems en ❌ |
| ❌ Rechazado | 1 o más ítems en ❌ (Debe iniciar ciclo de reproceso) |

**Decisión:** 
**Firmado por:**
**Fecha:**
