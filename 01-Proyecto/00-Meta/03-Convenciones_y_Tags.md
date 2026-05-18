---
id: META-02
titulo: Convenciones y Tags del Vault
version: "1.2"
estado: Activo
tipo: Estandar
fecha_creacion: 2026-03-19
ultima_revision: 2026-05-10
responsable: Axel Morales
referencias_biblio:
  - "Daniel Galin - SQA Components"
  - "IBM - ETVX Model"
  - "SWEBOK v4"
tags:
  - meta/estandar
  - gobernanza
---

# Convenciones y Tags del Vault (Sistematizado)

> Este documento define las reglas de infraestructura para el SGC, asegurando que cada nota sea procesable, trazable y esté escorada por importancia.

---

## 1. Regla de Jerarquía de Autoridad (Nuevo)

Para garantizar que la normativa sea lo primero que se visualice en cada carpeta, se establece el siguiente orden numérico de dos dígitos:

1.  **`00-PROC-XX`**: El proceso/metodología que gobierna la carpeta. SIEMPRE debe ser el archivo 00.
2.  **`01-` a `90-`**: Artefactos, entregables y documentos técnicos generados por el proceso, numerados según su orden de creación o relevancia.
3.  **`99-`**: Archivos auxiliares, plantillas locales o notas temporales.

---

## 2. Prefijos Estandarizados (Obligatorios)

| Prefijo | Significado | Ubicación Típica |
| :--- | :--- | :--- |
| **PROC-** | Proceso (Modelo ETVX) | Raíz de cualquier carpeta (como 00-PROC) |
| **REQ-** | Requerimiento de Software | `02-Requisitos` |
| **DIS-** | Documento de Diseño | `03-Diseño` |
| **COD-** | Documentación de Código | `04-Codificacion` |
| **CP-** | Caso de Prueba (Testing) | `05-Pruebas` |
| **MNT-** | Plan de Mantenimiento | `06-Mantenimiento` |
| **DESP-** | Documento de Despliegue | `08-Despliegue` |
| **CTRL-** | Control (Cambios/Metricas) | `07-Control` |
| **INS-** | Inspección / Revisión | `07-Control` |
| **CL-** | Checklist de Verificación | `00-Meta/99-Plantillas` |
| **NOTE-** | Nota de Consultoría / Aprendizaje | `08-Notes` |

---

## 3. Estructura de Tags (SQA Focus)

```text
Metodología y SGC:
  #etvx             - Notas que siguen estrictamente el modelo ETVX
  #sqa/infra        - Componentes de infraestructura de Galin
  #sqa/verif        - Actividades de verificación y control

Consultoría y Aprendizaje:
  #consultoria/gemini - Registro de sesiones con el agente
  #sqa/aprendizaje    - Notas de lecciones aprendidas o dudas técnicas

Estados de Artefacto:
  #estado/borrador    - En elaboración
  #estado/verificado  - Pasó checklist de calidad (CL-)
  #estado/aprobado    - Validado por el PO (Samuel) o Cliente (Gerónimo)
```

---

## 4. Trazabilidad Bidireccional

1.  **Enlaces**: Use siempre la ruta completa `[[Carpeta/Archivo]]` para evitar que Obsidian pierda el enlace al mover archivos entre fases.
2.  **Metadatos**: Todo archivo debe tener un `id` único y una `version` para control de cambios.

---
*Ultima actualizacion: 2026-05-10 | Gemini-SQA-Agent*
