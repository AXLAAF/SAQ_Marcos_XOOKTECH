# Gobernanza del Sistema de Gestión de Calidad (SGC) -- XookTech
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

**Área de proceso:** 01-Gestion de la configuracion
**Nombre del proceso:** Gobernanza del SGC (Vault Obsidian)
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

> **Antecedente**: Basado en la directiva del profesor (2026-05-18), este proceso evoluciona de una simple gestión de archivos a un **Sistema de Aseguramiento**. Si un artefacto falla la validación, la Gobernanza obliga a la mejora del proceso correspondiente. La fuente de verdad bibliográfica es Daniel Galin y el SWEBOK v4.

---

## Proceso

### 1. Definición de Roles y Responsabilidades

El Sistema de Gestión de Calidad (SGC) se opera bajo una estructura de roles institucionales para asegurar la independencia y el cumplimiento normativo.

**Roles y Responsabilidades Específicas:**

1.  **Analista de Gobernanza y Diseño**:
    *   **Gobernanza (00)**: Administra el SGC, asegura la integridad del Vault y coordina las auditorías bibliográficas.
    *   **Diseño (03)**: Ejecuta la ingeniería inversa para recuperar la arquitectura y asegura la sincronización código-diseño.
2.  **Analista de Requerimientos**:
    *   **Requisitos (02)**: Gestiona la obtención, especificación y validación de necesidades del cliente mediante el estándar IEEE 830.
3.  **Líder de Desarrollo e Implementación**:
    *   **Codificación (04)**: Dirige la construcción del software bajo estándares de codificación limpios y trazables.
    *   **Despliegue (07)**: Asegura la transición segura del código a entornos de producción.
4.  **Analista de Control y Cambios**:
    *   **Control (05) y Mantenimiento (08)**: Gestiona el registro de Solicitudes de Cambio (CR), audita la trazabilidad, administra el proceso de soporte y bitácoras post-despliegue, y mantiene el Tablero de Calidad.
5.  **Analista de Verificación y Pruebas**:
    *   **Pruebas (06)**: Diseña y ejecuta los planes de prueba (Unitarias, Integración, Sistema) para validar el cumplimiento de los requisitos.

**NT-1:** Todo archivo debe llevar en su Frontmatter el **Rol Responsable** en lugar de nombres propios para cumplir con el estándar organizacional.

---

### 2. Gestión de Estructura y Rigor ETVX

**Actualmente:**
- Se creaban carpetas sin una separación clara entre el "Hacer" (Ingeniería) y el "Verificar" (Calidad).

**NT-2:** El profesor insiste: "El proceso de ingeniería es qué probar, pero la calidad es verificar el proceso". Se propone la estructura binaria en cada fase.

**Propuesta:**
- Cada fase de la 02 a la 08 debe contener al menos dos subcarpetas:
    1. `01-Ingenieria_[Nombre]`: Contiene los artefactos (ej. REQ, STD, MOD).
    2. `02-Calidad_[Revisiones]`: Contiene la evidencia de validación (ej. CL, HALLAZGO, REG).

---

### 3. Control de Cambios y Congelación de Línea Base

**Actualmente:**
- Se modificaban los documentos sin dejar rastro del motivo ni del impacto en otras fases.

**NT-3:** El refinamiento de Analista de Requerimientos establece que cualquier cambio post-aprobación es una **Solicitud de Cambio (CR)**. Se propone integrar formalmente su flujo de control.

**Propuesta:**
- Una vez que un archivo pasa a `#estado/verificado`, se considera "Congelado".
- Cualquier modificación posterior requiere la creación de un **CR (Change Request)** usando la plantilla `[[TEMPLATE-CR]]`.
- El cambio debe ser registrado en el historial de versiones del Frontmatter y validado por el responsable de la fase 07.

---

### 4. Ciclo de Mejora Continua (Aseguramiento)

**Actualmente:**
- Si un hallazgo detectaba un error, solo se corregía el archivo, no la causa raíz.

**NT-4:** Aseguramiento no es Control. Si detectamos un error recurrente, debemos cambiar el **PROC-XX**. Se propone el uso del Registro de Mejora Continua.

**Propuesta:**
- Al emitir un `[[01-Gestion de la configuracion/99-Plantillas_y_Checklists/TEMPLATE-HALLAZGO|HALLAZGO]]`, el responsable debe evaluar si el proceso (`00-PROC-XX`) fue el culpable.
- Si el proceso es deficiente, se actualiza el proceso y se documenta en el ``REG-01 Mejora Continua de Procesos``.

---

## Artefactos Producidos

| ID | Artefacto | Propósito | Ubicación |
| :--- | :--- | :--- | :--- |
| **PROC-01** | Gobernanza Vault | Definir las reglas de operación y roles. | [[01-Gestion de la configuracion/01-PROC-01_Gobernanza_Vault|PROC-01]] |
| **STD-01** | Estándar ETVX | Definir la estructura de cada proceso. | [[01-Gestion de la configuracion/02-STD-01_Estandar_ETVX|STD-01]] |
| **STD-02** | Convenciones Tags | Normalizar nombres y etiquetas. | [[01-Gestion de la configuracion/03-STD-02_Convenciones_Tags|STD-02]] |
| **HALLAZGO** | Hallazgo SQA | Documentar discrepancias bibliográficas. | [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/TEMPLATE-HALLAZGO|HALLAZGO]] |

---

## Referencias
- **Daniel Galin (2004)**: Software Quality Assurance - "Infrastructure for Error Prevention".
- **SWEBOK v4**: Knowledge Area 10 - Software Engineering Management.
- **IEEE 12207**: Lifecycle Processes - Quality Management Process.