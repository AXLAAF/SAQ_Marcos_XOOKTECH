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

---

## 4. Estándar de Tags de Estado de Configuración

Para dar seguimiento dinámico en Obsidian y Git al ciclo de vida de los artefactos de la línea base, se definen los siguientes tags de control obligatorio, los cuales deben colocarse en los metadatos de la cabecera de los archivos (100% libres de emojis):

* `#estado/pendiente`: Ficha en desarrollo técnico inicial, en borrador o pendiente de la validación del Product Owner.
* `#estado/aprobado`: Ficha validada técnicamente y que cuenta con la aprobación digital del Product Owner, resguardada de cambios.
* `#estado/verificado`: Ficha auditada de forma conforme por el Analista de Control y Cambios y congelada en la Línea Base.
* `#estado/retrabajo`: Requisito o diseño rechazado en la auditoría SQA que requiere correcciones de alcance.

---

## 5. Gobernanza y Mantenimiento
* **Revisión de Enlaces:** El Analista de Gobernanza y Diseño ejecuta análisis periódicos de enlaces rotos en el vault para garantizar que los wikilinks interactivos apunten a rutas válidas.
* **Segregación de Carpetas:** Los archivos en estado pendiente deben almacenarse en carpetas `/00-Pendientes/` y se trasladan físicamente a `/01-Aprobados/` al ser aprobados por el Product Owner.
