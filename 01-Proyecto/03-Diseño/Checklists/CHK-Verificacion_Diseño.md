# [CHK-Verificacion_Diseño] Checklist de Calidad — Verificación de Diseño de Software

**Responsable:** Analista de Verificación y Pruebas  
**Entradas:** Documento de Descripción de Diseño de Software (SDD) completado, diagramas de arquitectura en Mermaid.js y Matriz de Trazabilidad de Requisitos (RTM) actualizada.  
**Salidas:** Evaluación de conformidad del diseño bajo IEEE Std 1016-2009 y dictamen de liberación del paquete de diseño a codificación.  

---

## Metadatos de la Revisión
| Campo | Valor |
|---|---|
| Proyecto | |
| Documento revisado | |
| Versión del SDD | |
| Analista de Diseño | |
| Revisor SQA | |
| Fecha de revisión | |
| Resultado general | ✅ Aprobado / ❌ Rechazado |

---

## Instrucciones
Marcar cada ítem como:
- ✅ Cumple
- ❌ No cumple
- N/A No aplica al proyecto

Todo ítem marcado como ❌ representa una no conformidad que debe ser corregida antes de que el paquete de diseño sea liberado a codificación.

---

## 1. Completitud del SDD y Estructura Documental

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| ED-01 | El SDD sigue la estructura de la plantilla `PLT-FOR_Plantilla_SDD.md` basada en IEEE Std 1016. | | |
| ED-02 | El documento incluye las secciones de Introducción, Propósito, Alcance y Glosario de Términos. | | |
| ED-03 | Las referencias académicas y normativas están correctamente citadas (Galin, SWEBOK, Lewis, Regan). | | |

*Referencia: IEEE Std 1016-2009 §4 (Estructura del SDD)*

---

## 2. Punto de Vista de Descomposición (Decomposition Viewpoint)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| DES-01 | El diseño describe la descomposición del sistema en componentes y subsistemas independientes. | | |
| DES-02 | Se identifican claramente las capas de Backend, Frontend y Persistencia con sus responsabilidades delimitadas. | | |
| DES-03 | El diagrama de descomposición en Mermaid.js renderiza correctamente en Obsidian. | | |

*Referencia: IEEE Std 1016-2009 §5.2 (Decomposition Viewpoint)*

---

## 3. Punto de Vista de Comportamiento Lógico (Logical Viewpoint)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| LOG-01 | El comportamiento del sistema está modelado con diagramas de secuencia que muestran la interacción temporal entre componentes. | | |
| LOG-02 | Se describen los flujos de éxito y los escenarios de error con respuestas HTTP apropiadas. | | |

*Referencia: IEEE Std 1016-2009 §5.3 (Logical Viewpoint)*

---

## 4. Punto de Vista Físico (Physical Viewpoint)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| FIS-01 | El documento detalla la estructura de directorios del repositorio Python y la ubicación de archivos críticos. | | |
| FIS-02 | Se establecen las convenciones de organización de módulos, archivos estáticos y configuraciones. | | |

*Referencia: IEEE Std 1016-2009 §5.6 (Physical Viewpoint)*

---

## 5. Punto de Vista de Datos (Data Viewpoint)

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| DAT-01 | Los tipos de datos, llaves primarias, relaciones y restricciones de integridad están especificados. | | |
| DAT-02 | Se verifica la consistencia del modelo de datos con las necesidades de persistencia de los requisitos. | | |

*Referencia: IEEE Std 1016-2009 §5.5 (Information Viewpoint)*

---

## 6. Interfaces de Componentes y APIs

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| INT-01 | Se especifican las signaturas de funciones críticas con parámetros de entrada, tipos de retorno y códigos de respuesta. | | |
| INT-02 | Las interfaces están definidas antes de iniciar la codificación y no presentan ambigüedades técnicas. | | |

*Referencia: SWEBOK v4 Cap. 2 (Diseño de Software) / CMMI-DEV v2.0 TS SP 2.1*

---

## 7. Trazabilidad del Diseño

| ID | Criterio | Estado | Observación |
|---|---|---|---|
| TR-01 | Cada componente y subsistema del SDD tiene un identificador único e inalterable. | | |
| TR-02 | El 100% de los elementos de diseño están mapeados a sus requisitos de origen en la RTM. | | |
| TR-03 | La RTM refleja trazabilidad bidireccional (requisito → diseño y diseño → requisito). | | |

*Referencia: CMMI-DEV v2.0 TS SP 2.2 / ISO/IEC 12207 §6.4.4*

---

## Resumen de Hallazgos SQA

| ID Ítem | Observación técnica | Acción correctiva requerida |
|---|---|---|
| | | |

## Decisión de Liberación y Ciclo de Reproceso

En caso de que se identifique cualquier no conformidad (ítem marcado con ❌), la liberación del paquete de diseño queda formalmente **Rechazada**. El Analista de Gobernanza y Diseño recibirá esta lista de hallazgos y dispondrá de un plazo máximo de **24 horas** para corregir las observaciones y volver a someter el SDD a una nueva inspección.

| Resultado | Criterio |
|---|---|
| ✅ Aprobado | 0 ítems en ❌ |
| ❌ Rechazado | 1 o más ítems en ❌ (Debe iniciar ciclo de reproceso) |

**Decisión:** 
**Fecha:**
