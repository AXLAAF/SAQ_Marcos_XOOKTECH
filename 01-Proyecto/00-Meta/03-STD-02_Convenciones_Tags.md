# STD-02: Estándar de Convenciones y Nomenclatura

> **Propósito**: Garantizar la uniformidad, trazabilidad y automatización de la bóveda de SQA mediante el uso de prefijos estrictos y una jerarquía de etiquetas (tags).

## 1. Nomenclatura de Archivos (Prefijos)

| Prefijo | Significado | Ubicación Recomendada |
| :--- | :--- | :--- |
| **PROC-** | Proceso (Modelo ETVX) | 00-Meta, 02-Estandar_de_Procesos |
| **REQ-** | Requerimiento de Software | 02-Requisitos |
| **CP-** | Caso de Prueba | 05-Pruebas |
| **CR-** | Change Request (Control de Cambios) | 07-Control |
| **INS-** | Reporte de Inspección | 07-Control |
| **CL-** | Checklist / Lista de Verificación | 00-Meta/99-Plantillas |
| **GLO-** | Glosario | 00-Meta |
| **PLAN-** | Plan de Acción o Estrategia | 00-Meta, 05-Pruebas |
| **STD-** | Estándar o Guía Técnica | 00-Meta |
| **REG-** | Registro o Bitácora | Diversas carpetas |
| **FOR-** | Formato o Plantilla | 00-Meta/99-Plantillas |
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
