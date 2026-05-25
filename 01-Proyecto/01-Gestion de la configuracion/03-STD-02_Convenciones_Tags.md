# STD-02: Estándar de Convenciones y Nomenclatura
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

---

> **Propósito**: Garantizar la uniformidad, trazabilidad y automatización de la bóveda de SQA mediante el uso de prefijos estrictos y una jerarquía de etiquetas (tags).

## 1. Nomenclatura de Archivos (Prefijos)

| Prefijo | Significado | Ubicación Recomendada |
| :--- | :--- | :--- |
| **PROC-** | Proceso (Modelo ETVX) | 01-Gestion de la configuracion, 02-Estandar_de_Procesos |
| **REQ-** | Requerimiento de Software | 02-Requisitos |
| **CP-** | Caso de Prueba | 04-Pruebas |
| **CR-** | Change Request (Control de Cambios) | 05-Revisiones e inspecciones |
| **INS-** | Reporte de Inspección | 05-Revisiones e inspecciones |
| **CL-** | Checklist / Lista de Verificación | 01-Gestion de la configuracion/99-Plantillas |
| **GLO-** | Glosario | 01-Gestion de la configuracion |
| **PLAN-** | Plan de Acción o Estrategia | 01-Gestion de la configuracion, 04-Pruebas |
| **STD-** | Estándar o Guía Técnica | 01-Gestion de la configuracion |
| **REG-** | Registro o Bitácora | Diversas carpetas |
| **FOR-** | Formato o Plantilla | 01-Gestion de la configuracion/99-Plantillas |
| **NOTE-** | Nota Técnica o de Consultoría | 09-Notes |

## 2. Jerarquía de Tags (Etiquetas)

Las etiquetas deben seguir una estructura anidada para facilitar el filtrado con Dataview:

- `#meta/...`: Para gobernanza (`#meta/proceso`, `#meta/estandar`).
- `#fase/...`: Según el ciclo de vida (`#fase/requisitos`, `#fase/diseño`, `#fase/pruebas`).
- `#estado/...`: Estado del documento (`#estado/borrador`, `#estado/verificado`, `#estado/aprobado`).
- `#tipo/...`: Naturaleza del artefacto (`#tipo/requerimiento`, `#tipo/caso-prueba`).

## 3. Formato de Frontmatter (YAML)

Todos los documentos técnicos deben incluir el bloque inicial con los campos:
- `id`: Identificador único (ej. REQ-01).
- `version`: Control de versiones decimal.
- `responsable`: Persona a cargo.
- `referencias_biblio`: Alineación con Galin/Lewis/SWEBOK.