# Gestión de Control de Calidad y Cambios -- XookTech
**Responsable:** Analista de Control y Cambios
**Entradas:** Registros de Defectos e Incidentes
**Salidas:** Solicitudes de Cambio Aprobadas e Informes de Inspección

**Área de proceso:** 05-Revisiones e inspecciones
**Nombre del proceso:** Aseguramiento y Control de Configuración (SCC)
**Notación:** NT: indica una Nota Técnica con una sugerencia de mejora al proceso actual.

---

> **Antecedente**: La fase de Control evoluciona de un simple registro a un **Sistema de Control de Configuración (SCC)**. Este proceso garantiza que cada cambio en el software sea trazable, aprobado y auditado, evitando que el código en producción diverja de la documentación oficial. Se basa en el estándar IEEE 828 para la Gestión de Configuración.

---

## Proceso

### 1. Gestión de la Línea Base (Baselines)

**Actualmente:**
- Los documentos se consideran finales una vez escritos, pero no se "congelan" formalmente.

**NT-1:** Sin una línea base congelada, es imposible realizar auditorías de regresión. SWEBOK v4 establece que la Línea Base es el punto de referencia para el control de cambios. Se propone el sellado técnico de cada fase.

**Propuesta:**
- El **Analista de Control y Cambios** certifica que una fase (ej. 02-Requisitos) está completa.
- Se registra el estado en el [[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|Dashboard de Calidad]].
- Cualquier edición posterior a este sello activa automáticamente el subproceso de Control de Cambios.

---

### 2. Control de Cambios (Change Requests - CR)

**Actualmente:**
- Se realizan correcciones menores sin documentar el "por qué" ni quién autorizó el cambio.

**NT-2:** El cambio no controlado es la principal causa de fallos en sistemas complejos. Galin (2004) advierte que "un cambio sin registro es una deuda técnica invisible". Se propone la obligatoriedad del CR.

**Propuesta:**
- Para cada cambio solicitado por el cliente o detectado por el equipo, se debe crear una nota usando la plantilla `TEMPLATE-CR`.
- Se asigna un folio (ej. [[05-Revisiones e inspecciones/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01]]).
- El cambio solo se implementa si cuenta con la firma digital (check) del **Analista de Control**.

---

### 3. Inspecciones Formales (Auditoría)

**Actualmente:**
- Las revisiones son informales (peer reviews) y no dejan evidencia documental del cumplimiento normativo.

**NT-3:** La inspección formal es la técnica más potente de SQA para detectar errores antes de la codificación. Se propone el uso de Listas de Verificación (Checklists) vinculadas a los Hallazgos.

**Propuesta:**
- El responsable de esta fase ejecuta inspecciones periódicas sobre los artefactos de otras fases.
- Se generan reportes de inspección (ej. [[05-Revisiones e inspecciones/02-Calidad_Control/05-INS-01_Inspeccion_Requerimientos|INS-01]]).
- Si se detecta una no conformidad crítica, se emite un **HALLAZGO** que bloquea el despliegue.

---

### 4. Gestión de Defectos y Cierre Técnico

**Actualmente:**
- Los errores encontrados en pruebas se corrigen, pero no se analizan para mejorar el proceso.

**NT-4:** SQA implica aprendizaje organizacional. Si un error llega a producción, el proceso falló. Se propone el registro de causa raíz.

**Propuesta:**
- Todo fallo detectado en la fase 04-Pruebas se traslada al [[05-Revisiones e inspecciones/02-Calidad_Control/02-REG-03_Registro_Defectos|Registro de Defectos]].
- El defecto no se considera cerrado hasta que el **Analista de Control** verifique que no hay impacto colateral en otros módulos.

---

## Artefactos Producidos (Ingeniería de Control)

| ID | Artefacto | Propósito | Ubicación |
| :--- | :--- | :--- | :--- |
| **STD-08** | Dashboard de Calidad | Visualizar el estado de salud de todos los procesos. | [[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08]] |
| **REG-03** | Registro de Defectos | Controlar el ciclo de vida de los fallos encontrados. | [[05-Revisiones e inspecciones/02-Calidad_Control/02-REG-03_Registro_Defectos|REG-03]] |
| **INS-XX** | Inspecciones | Documentar la verificación formal de artefactos. | [[05-Revisiones e inspecciones/02-Calidad_Control/05-INS-01_Inspeccion_Requerimientos|INS-01]] |
| **CR-XX** | Control de Cambios | Gestionar las solicitudes de modificación post-baseline. | [[05-Revisiones e inspecciones/01-Ingenieria_Control/08-CR-01_Marcos_Dobles|CR-01]] |

---

## Referencias
- **SWEBOK v4**: Knowledge Area 6 - Software Configuration Management.
- **Daniel Galin (2004)**: Software Quality Assurance - "Software Configuration Management".
- **IEEE 828-2012**: Standard for Configuration Management in Systems and Software Engineering.