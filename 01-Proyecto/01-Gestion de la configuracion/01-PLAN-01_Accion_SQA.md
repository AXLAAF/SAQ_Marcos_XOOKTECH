# Dashboard de Control del Proyecto - Visualizador de Marcos
**Responsable:** Analista de Gobernanza y Diseño
**Entradas:** Estándares ETVX y Gobernanza
**Salidas:** Vault de Obsidian Auditado y Coherente

---

> **Proposito**: Monitorear el progreso de las 8 fases del proyecto bajo el modelo de calidad SQA y rigor ETVX.

---

## 1. Estado de las Fases (Ciclo SQA)
>   Visualizar el flujo de trabajo y la trazabilidad del proyecto. Cada fase tiene un responsable asignado para evitar la ambiguedad y un entregable clave.

| Fase | Proceso Asociado | Responsable | Estado | Entregable Clave |
| :--- | :--- | :--- | :---: | :--- |
| **Fase 1: Linea Base** | [[09-Notes/01-Linea_Base-Original/00-PROC-01_Recuperacion_Linea_Base|PROC-01 Recuperación de Línea Base]] | Analista de Requerimientos | 🟢 | [[09-Notes/01-Linea_Base-Original/02-Propuesta_Recuperada|Propuesta de Proyecto]] |
| **Fase 2: Requisitos** | [[02-Requisitos/02-PROC-02_Especificacion_Requerimientos|PROC-02 Especificación de Requerimientos]] | Analista de Requerimientos | 🟡 | [[02-Requisitos/01-Ingenieria_Requisitos/01-Aprobados/01-REQ-01_Carga_Imagen|REQ-01 Carga de Imagen]] |
| **Fase 3: Diseño** | [[03-Diseño/03-PROC-03_Diseño_Sistema|PROC-03 Diseño de Sistema]] | Analista de Gobernanza y Diseño | ⚪ | [[03-Diseño/01-Ingenieria_Arquitectura/01-STD-04_Diagrama_Componentes|STD-04 Diagrama de Componentes]] |
| **Fase 4: Codificacion** | [[06-Codigo/04-PROC-04_Codificacion|PROC-04 Codificación]] | Líder de Desarrollo e Implementación | ⚪ | Módulos Python / GitHub |
| **Fase 5: Pruebas** | [[04-Pruebas/06-PROC-06_Plan_Pruebas|PROC-05 Plan de Pruebas]] | Analista de Verificación y Pruebas | 🟡 | [[04-Pruebas/01-Ingenieria_Pruebas/01-PLAN-02_Plan_Pruebas|PLAN-02 Plan Maestro de Pruebas]] |
| **Fase 6: Mantenimiento** | [[08-Mantenimiento/08-PROC-08_Mantenimiento|PROC-06 Mantenimiento]] | Analista de Gobernanza y Diseño | ⚪ | [[08-Mantenimiento/01-Ingenieria_Soporte/01-REG-01_Solicitudes_Mantenimiento|REG-01 Solicitudes de Soporte]] |
| **Fase 7: Control** | [[05-Revisiones e inspecciones/05-PROC-05_Control_Configuracion|PROC-07 Control]] | Analista de Control y Cambios | 🟡 | [[05-Revisiones e inspecciones/02-Calidad_Control/01-STD-08_Dashboard_Calidad|STD-08 Dashboard de Calidad]] |
| **Fase 8: Despliegue** | [[07-Despliegue/07-PROC-07_Despliegue|PROC-08 Despliegue]] | Líder de Desarrollo e Implementación | ⚪ | [[07-Despliegue/Documentos_Apoyo/02-Formatos/CL-08-01_Verificacion_Despliegue|CL-08-01 Verificación de Despliegue]] |

*Leyenda: ⚪ Pendiente | 🟡 En Progreso | 🟢 Completado*

---

## 2. Metricas de Infraestructura (Daniel Galin)
>  Verifica que el equipo cuente con las herramientas necesarias para producir documentacion de alta calidad.

- **Plantillas Disponibles**:
	- [x] [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/TEMPLATE-REQ|TEMPLATE-REQ]] (Requerimientos)
	- [x] [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/TEMPLATE-CP|TEMPLATE-CP]] (Casos de Prueba)
- **Checklists de Verificacion**:
	- [x] [[01-Gestion de la configuracion/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos|CL-02 Verificación de Requisitos]]
- **Gobernanza**:
	- [x] [[01-Gestion de la configuracion/01-PROC-01_Gobernanza_Vault|PROC-01 Gobernanza Vault]]
	- [x] [[01-Gestion de la configuracion/05-STD-03_Matriz_Responsabilidades|STD-03 Matriz de Responsabilidades (5 Roles)]]

---

## 3. Hoja de Ruta Inmediata (Sprint Final)
> Asignacion de prioridades antes de la revision. Objetivos; eliminar agujetos tecnicos y verificar la escritura de los documentos.

1. **Sistematizar Procesos 04, 06 y 08**: Líder de Desarrollo e Implementación y Analista de Gobernanza y Diseño deben documentar y auditar la codificación, soporte técnico y despliegue.
2. **Cerrar Trazabilidad (RTM)**: Analista de Requerimientos debe vincular REQ -> Control para asegurar que no hay brechas en la trazabilidad.
3. **Ejecutar Casos de Prueba (CP)**: Analista de Verificación y Pruebas debe capturar evidencia real de pruebas del prototipo en la carpeta `04-Pruebas`.

---

## Herramientas y Recursos
> Consolida los enlaces externos y las referencias bibliograficas que fundamentan el proyecto

### Repositorio y Desarrollo
- **GitHub**: [Marcos2](https://github.com/Bigsami89/Marcos2)
- **Tecnología**: Servidor de Aplicaciones y APIs Web
- **Documentacion**: Obsidian (Vault SQA)

### Referencias del Marco Teorico (Assignments_V2)
- [[PLAN-FINAL_SQA]] — Plan de trabajo detallado por integrante.
- `Reporte de Verificación` — Base para Verificacion (V&V).
- [[01-Gestion de la configuracion/03-STD-02_Convenciones_Tags|STD-02 Convenciones y Tags]] — Reglas de nomenclatura y jerarquia.