# Gobernanza y Gestión de la Configuración — SGC XookTech

**Responsable:** Analista de Gobernanza y Diseño  
**Entradas:** Directrices del proyecto y ciclo de vida de desarrollo.  
**Salidas:** Estructura del vault de Obsidian y control de versiones en Git.  

---

## 1. Información General
| Campo | Detalle |
|---|---|
| Código | 01 |
| Proceso | Gestión de la Configuración y Gobernanza |
| Estándar de referencia | ISO/IEC 12207:2017 §6.2.2 (Proceso de gestión de la configuración de software) |
| Versión | 3.0 |
| Fecha | 2026-05-25 |
| Responsable del proceso | Analista de Gobernanza y Diseño |

---

## 2. Propósito
Definir y mantener la integridad de los entregables y la documentación técnica del proyecto a lo largo del ciclo de vida del software, asegurando un repositorio ordenado en Git y una navegación interactiva y consistente en Obsidian.

---

## 3. Alcance
* **Qué cubre:** Estructura física del vault de Obsidian, estándares de nomenclatura de documentos, políticas de ramificación y commits de Git, control de cambios y auditorías de configuración.
* **Qué NO cubre:** Diseño técnico de arquitectura (Fase 03), pruebas lógicas del sistema (Fase 04) ni el despliegue del servidor en producción (Fase 07).

---

## 4. Roles y Responsabilidades
| Rol | Responsabilidad en este proceso |
|---|---|
| Analista de Gobernanza y Diseño | Administra la estructura del vault en Obsidian, audita la consistencia de los wikilinks, resguarda el estándar de control de versiones y autoriza la integración en Git. |
| Líder de Desarrollo | Garantiza el cumplimiento de las políticas de ramificación y del formato de commits en el repositorio de codificación. |
| Equipo de Desarrollo y SQA | Aplican de forma obligatoria las plantillas y checklists del SGC en cada una de sus actividades operacionales. |

---

## 5. Directrices del Proceso

### 5.1 Estructura del Vault de Obsidian
El repositorio de documentación debe organizarse estrictamente en la siguiente estructura de carpetas físicas:
* `/01-Gestion de la configuracion/`: Documentos de gobernanza, estándares y plantillas de inicio.
* `/02-Requisitos/`: Documentación As-Is, plan de mejora de requisitos, plantillas de SRS y especificaciones del sistema.
* `/03-Diseño/`: Documentación de arquitectura As-Is, plan de mejora de diseño, diagramas técnicos y especificación SDD.
* `/04-Pruebas/`: Planes de pruebas, casos de prueba unificados y bitácoras de ejecución técnica.
* `/05-Revisiones_e_inspecciones/`: Informes de revisión por pares y bitácora técnica de inspecciones SQA.
* `/06-Codigo/`: Estándar de codificación de la organización y documentación de la fase de construcción.
* `/07-Despliegue/`: Guía de despliegue, planes de humo y bitácoras de servidores de producción.
* `/08-Mantenimiento/`: Bitácoras de incidentes y cotización de cambios del sistema.

### 5.2 Control de Cambios Documentales
Cualquier modificación o adición de requerimientos del sistema o arquitectura de software debe canalizarse formalmente a través de un folio de cambio `CR-XXX.md` utilizando la plantilla oficial de control de cambios. Un documento de la línea base aprobado no puede modificarse sin un folio `CR-XXX` autorizado por el Product Owner.

---

## 6. Políticas de Control de Versiones en Git
* **Rama Principal:** La rama `main` del repositorio se mantiene exclusivamente en un estado funcional estable y verificado.
* **Ramas de Características:** Todo desarrollo o corrección de tareas se realiza en ramas de desarrollo aisladas (`feature/TAR-YYYY-NNN` o `hotfix/incident-XXX`).
* **Mensajes de Commit:** Es obligatorio utilizar el prefijo del identificador de la tarea para cada confirmación de cambios (ej. `TAR-2026-001: Se agrega validación de...`), garantizando la trazabilidad histórica de la configuración.

---

## 7. Referencias
* [1] ISO/IEC 12207:2017 - Software Configuration Management Process.
* [2] SWEBOK v4.0 Capítulo 5 - Software Configuration Management.
