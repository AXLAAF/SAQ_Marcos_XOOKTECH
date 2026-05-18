---
id: META-00
titulo: Plan de Accion - Sistema Visualizador de Marcos
version: "1.0"
estado: En_Progreso
tipo: Plan
fecha_creacion: 2026-03-16
ultima_revision: 2026-03-25
responsable: Samuel Blanco
equipo:
  - Jose Samuel Blanco Cervera
  - Axel Adolfo Morales Caro
proyecto: Visualizador de Marcos
cliente: Enmarcame
referencias:
  - "SWEBOK v4"
  - "O'Regan - A Practical Approach to Software Quality"
  - "Lewis - Software Testing and Continuous Quality Improvement"
tags:
  - meta/plan
  - proyecto
  - requerimientos
  - calidad-software
---

# Dashboard de Control del Proyecto - Visualizador de Marcos

> **Proposito**: Monitorear el progreso de las fases del proyecto bajo el modelo de calidad SQA.

## 1. Estado de las Fases (Ciclo SQA)

| Fase | Proceso Asociado | Estado | Entregable Clave |
| :--- | :--- | :---: | :--- |
| **Fase 1: Baseline** | [[PROC-01_Recuperacion_Linea_Base]] | 🟡 | [[01-Propuesta_Recuperada]] |
| **Fase 2: Requerimientos** | [[PROC-02_Especificacion_Requerimientos]] | 🟡 | [[REQ-01]] a [[REQ-10]] |
| **Fase 3: Cambios** | [[PROC-03_Control_Cambios]] | ⚪ | [[CR-01]] a [[CR-04]] |
| **Fase 4: Arquitectura** | [[PROC-04_Arquitectura_Sistema]] | ⚪ | Diagramas y Flujos |
| **Fase 5: Pruebas** | [[PROC-05_Plan_Pruebas]] | ⚪ | [[00-Plan_Maestro_Pruebas]] |

*Leyenda: ⚪ Pendiente | 🟡 En Progreso | 🟢 Completado*

## 2. Metricas de Infraestructura (Daniel Galin)

- **Plantillas Disponibles**:
	- [x] [[TEMPLATE-REQ]] (Requerimientos)
	- [x] [[TEMPLATE-CP]] (Casos de Prueba)
- **Checklists de Verificacion**:
	- [x] [[CL-02_Verificacion_Requerimientos]]
- **Gobernanza**:
	- [x] [[PROC-00_Gobernanza_Vault]]

## 3. Hoja de Ruta Inmediata

1. **Sistematizar PROC-05**: Crear el procedimiento operativo para el diseño y ejecucion de pruebas.
2. **Completar REQ-07 a REQ-10**: Aplicar el [[TEMPLATE-REQ]] a los nuevos requerimientos contractuales.
3. **Auditoria Interna**: Validar que todas las notas cumplen con las [[02-Convenciones_y_Tags]].

---

## Herramientas Recomendadas

### Para Documentacion y Proyecto

| Herramienta | Uso | Link |
|---|---|---|
| **Obsidian** | Este vault, documentacion del proyecto | Local |
| **draw.io / diagrams.net** | Diagramas de arquitectura y flujo | [diagrams.net](https://diagrams.net) |
| **Notion / Jira** | Seguimiento de tareas y change requests | Segun preferencia |
| **GitHub / GitLab** | Control de versiones del codigo | Segun hosting actual |

### Para Desarrollo

| Herramienta | Uso |
|---|---|
| **Git** | Control de versiones — rama por cada nuevo requerimiento |
| **Postman** | Pruebas de endpoints si la app tiene API |
| **pytest** | Pruebas unitarias del programa Python de deteccion de ancho |
| **Playwright / Cypress** | Pruebas automatizadas de la interfaz web |
| **Lighthouse** | Auditoria de rendimiento de la app web |

### Para el Catalogo y Base de Datos

| Herramienta                     | Uso                                                        |
| ------------------------------- | ---------------------------------------------------------- |
| **DB Browser for PostgrestSQL** | Si la base de datos es SQLite                              |
| **TablePlus / DBeaver**         | Cliente visual para cualquier base de datos                |
| **OpenPyXL**                    | Migracion del Excel al sistema si aun no esta automatizada |

---

## Referencias del Marco Teorico

- [[03-Glosario]] — Glosario de terminos del proyecto
- [[02-Convenciones_y_Tags]] — Convenciones y tags del vault
- O'Regan - A Practical Approach to Software Quality — Cap. 1-3: Documentacion de calidad, propuesta, control de proceso
- SWEBOK v4 — KA Requirements §1.11, §4, §6.2: Gestion y especificacion de requerimientos, control de cambios
- Lewis - Software Testing and Continuous Quality Improvement — Cap. 21-25: Gestion de cambios, plan de pruebas, scope creep

---

*Ultima actualizacion: 2026-04-14 — Jose Samuel Blanco Cervera & Axel Adolfo Morales Caro*
*Documento movido desde raiz del proyecto como parte de la correccion de estructura*