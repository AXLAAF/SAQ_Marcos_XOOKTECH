# Convenciones de Nomenclatura y Tags — SGC XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Directrices de la configuración de software y taxonomía del vault.  
**Salidas:** Estándar de nomenclatura y etiquetas unificado en Obsidian.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | STD-02 |
| Documento | Estándar de Nomenclatura, Directorios y Tags de Obsidian |
| Marco de referencia | CMMI-DEV v2.0 CM / SWEBOK v4.0 Cap. 5 |
| Versión | 3.0 |
| Fecha | 2026-05-25 |

---

## 2. Propósito
Establecer las directrices obligatorias de organización física, nombrado de archivos y uso de etiquetas (tags) en Obsidian. Este estándar elimina la inconsistencia taxonómica, asegura la navegación interactiva y garantiza la consistencia del control de configuración en el vault.

---

## 3. Convenciones de Nomenclatura de Archivos

Todo archivo físico incorporado al Sistema de Gestión de Calidad (SGC) en Obsidian debe nombrarse estrictamente bajo las siguientes estructuras taxonómicas (excluyendo emojis de los nombres de archivos):

### 3.1 Documentos de Gobernanza y Planes de Mejora
* **Estructura:** `[Código de Fase]-[Nomenclatura]-[Nombre_Descriptivo].md`
* **Ejemplos:**
  * `02-Requisitos/00-REQ-Documentacion_Requisitos.md`
  * `02-Requisitos/00-REQ-Plan_De_Mejora_Requisitos.md`

### 3.2 Fichas de Requisitos e Historias de Usuario
* **Estructura:** `REQ-[Número Secuencial].md` o `HU-[Número Secuencial].md`
* **Ejemplos:**
  * `REQ-001.md`
  * `HU-005.md`

### 3.3 Checklists de Calidad
* **Estructura:** `CHK-[Nombre_Descriptivo_Fase].md`
* **Ejemplos:**
  * `02-Requisitos/Checklists/CHK-Verificacion_Requisitos.md`
  * `03-Diseño/Checklists/CHK-Verificacion_Diseño.md`

### 3.4 Plantillas de Formatos y Registros
* **Estructura:** `PLT-FOR_[Nombre_Plantilla].md` o `PLT-REG_[Nombre_Registro].md`
* **Ejemplos:**
  * `PLT-FOR_Reporte_Junta.md`
  * `PLT-REG_Verificacion_Requisitos.md`

## 4. Convenciones de Identificadores de SQA

Para dar seguimiento unívoco y garantizar la trazabilidad de los procesos y entregables del SGC, se declaran los prefijos y nomenclaturas obligatorias para todos los procesos del ciclo de vida:

### 4.1 Identificadores de Gobernanza y Mejora (Fase 01, Diagnósticos y Mejora)
* **`STD-XX` (Estándares Metodológicos):** Códigos para normas internas del SGC (ej. `STD-01` para el estándar ETVX).
* **`PLT-FOR_[Nombre]` (Plantillas de Formatos):** Estructuras vacías listas para instanciar (ej. `PLT-FOR_Reporte_Junta`).
* **`PLT-REG_[Nombre]` (Plantillas de Registros SQA):** Formatos de verificación de calidad (ej. `PLT-REG_Verificacion_Requisitos`).
* **`H-0X` (Hallazgos de Diagnóstico):** Brechas o problemas detectados en el análisis del proceso As-Is (ej. `H-01`).
* **`M-0X` (Acciones de Mejora):** Soluciones o actividades de remediación propuestas en los planes To-Be (ej. `M-02`).

### 4.2 Identificadores de Ingeniería (Fases 02 y 03)
* **`REQ-XXX` (Requisitos del Sistema):** Especificación secuencial de tres dígitos de requisitos de la línea base (ej. `REQ-001`).
* **`HU-XXX` (Historias de Usuario):** Especificación de flujos ágiles específicos de negocio (ej. `HU-005`).
* **`SDD-XXX` (Descripción de Diseño):** Nomenclatura del Documento de Descripción de Diseño (ej. `SDD-VAL-01` o `PLT-FOR_Plantilla_SDD`).
* **`ADR-XXX` (Decisiones de Arquitectura):** Registro de justificación técnica y tecnológica de la arquitectura (ej. `ADR-001`).
* **`DIA-XXX` (Diagramas de Arquitectura):** Diagramas técnicos Mermaid.js incorporados al SGC (ej. `DIA-VAL-01`).

### 4.3 Identificadores de Construcción y Entrega (Fases 06 y 07)
* **`EST-COD-XX` (Estándares de Codificación):** Estándares de estilo de desarrollo técnico de componentes.
* **`COD-XX` o `MOD-XX` (Módulos de Código):** Módulos, scripts y archivos de código de la aplicación.
* **`GUI-INST` (Guía de Instalación):** Guía de instalación técnica del software.
* **`SMK-XX` (Pruebas de Humo):** Planes y reportes de pruebas de humo automatizadas en servidores (ej. `SMK-01`).

### 4.4 Identificadores de Calidad y Revisiones (Fases 04 y 05)
* **`PL-PRU-XX` (Plan de Pruebas):** Plan estratégico ligero para validación funcional previa a entregas (ej. `PL-PRU-01`).
* **`CP-XX` (Casos de Prueba):** Casos de prueba individuales de la línea base (ej. `CP-01`).
* **`BIT-PRU-XX` (Bitácora de Pruebas):** Evidencias físicas de ejecución de pruebas del sistema.
* **`INF-INS-XX` (Informes de Inspección):** Reportes de revisión por pares y auditorías (ej. `INF-INS-01`).
* **`REG-SQA-XX` (Registros SQA):** Evaluaciones unificadas de conformidad cuantitativa (ej. `REG-SQA-01` o `REG-02-01`).

### 4.5 Identificadores de Mantenimiento y Soporte (Fase 08)
* **`INC-XX` (Incidentes de Soporte):** Folios de reportes de fallas del sistema en producción (ej. `INC-01`).
* **`COT-XX` (Cotización de Cambios):** Hojas de aprobación técnica y comercial de cambios correctivos (ej. `COT-01`).
* **`CR-XXX` (Solicitud de Cambio):** Folio de solicitud de cambios de alcance sobre la línea base (ej. `CR-001`).
* **`TAR-YYYY-NNN` (Tareas de Desarrollo):** Folios de seguimiento de tareas asociando año y secuencial (ej. `TAR-2026-001`).

---

## 5. Estándar de Tags de Estado de Configuración

Para dar seguimiento dinámico en Obsidian y Git al ciclo de vida de los artefactos de la línea base, se definen los siguientes tags de control obligatorio, los cuales deben colocarse en los metadatos de la cabecera de los archivos (100% libres de emojis):

* `#estado/pendiente`: Ficha en desarrollo técnico inicial, en borrador o pendiente de la validación del Product Owner.
* `#estado/aprobado`: Ficha validada técnicamente y que cuenta con la aprobación digital del Product Owner, resguardada de cambios.
* `#estado/verificado`: Ficha auditada de forma conforme por el Analista de Control y Cambios y congelada en la Línea Base.
* `#estado/retrabajo`: Requisito o diseño rechazado en la auditoría SQA que requiere correcciones de alcance.

---

## 6. Gobernanza y Mantenimiento
* **Revisión de Enlaces:** El Analista de Gobernanza y Diseño ejecuta análisis periódicos de enlaces rotos en el vault para garantizar que los wikilinks interactivos apunten a rutas válidas.
* **Segregación de Carpetas:** Los archivos en estado pendiente deben almacenarse en carpetas `/00-Pendientes/` y se trasladan físicamente a `/01-Aprobados/` al ser aprobados por el Product Owner.

