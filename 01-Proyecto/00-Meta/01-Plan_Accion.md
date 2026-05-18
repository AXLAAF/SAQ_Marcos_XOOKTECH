---
id: META-00
titulo: Plan de Accion - Sistema Visualizador de Marcos
version: "2.1"
estado: En_Progreso
tipo: Plan
fecha_creacion: 2026-03-16
ultima_revision: 2026-05-12
responsable: Axel Morales
equipo:
  - Axel Adolfo Morales Caro (Estrategia y Verificacion)
  - Jose Samuel Blanco Cervera (Implementacion y Operaciones)
  - Carlos Yonson (Analisis y Control de Calidad)
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

> **Proposito**: Monitorear el progreso de las 8 fases del proyecto bajo el modelo de calidad SQA y rigor ETVX.

---

## 1. Estado de las Fases (Ciclo SQA)
>   Visualizar el flujo de trabajo y la trazabilidad del proyecto. Cada fase tiene un responsable asignado para evitar la ambiguedad y un entregable clave.

| Fase | Proceso Asociado | Responsable | Estado | Entregable Clave |
| :--- | :--- | :--- | :---: | :--- |
| **Fase 1: Linea Base** | [[00-PROC-01_Recuperacion_Linea_Base]] | Axel | 🟢 | [[02-Propuesta_Recuperada]] |
| **Fase 2: Requisitos** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/PROC-02_Especificacion_Requerimientos]] | Carlos | 🟡 | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/02-Requisitos/REQ-01_Carga_Imagen]] |
| **Fase 3: Diseño** | [[00-PROC-03_Diseño_Sistema]] | Axel | ⚪ | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/03-Diseño/01-Diagrama_Componentes]] |
| **Fase 4: Codificacion** | [[00-PROC-04_Codificacion]] | Samuel | ⚪ | Modulos Python / GitHub |
| **Fase 5: Pruebas** | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/PROC-05_Plan_Pruebas]] | Axel | 🟡 | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/01- Proyecto/05-Pruebas/00-Plan_Maestro_Pruebas]] |
| **Fase 6: Mantenimiento** | [[06-Mantenimiento/00-PROC-06_Mantenimiento]] | Samuel | ⚪ | [[06-Mantenimiento/MNT-01_Plan_Soporte]] |
| **Fase 7: Control** | [[00-PROC-07_Control]] | Carlos | 🟡 | [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments_V2/01-Proyecto/07-Control/00-Dashboard_Calidad]] |
| **Fase 8: Despliegue** | [[08-Despliegue/00-PROC-08_Despliegue]] | Samuel | ⚪ | [[08-Despliegue/DESP-01_Guia_Instalacion]] |

*Leyenda: ⚪ Pendiente | 🟡 En Progreso | 🟢 Completado*

---

## 2. Metricas de Infraestructura (Daniel Galin)
>  Verifica que el equipo cuente con las herramientas necesarias para producir documentacion de alta calidad.

- **Plantillas Disponibles**:
	- [x] [[01-Proyecto/00-Meta/99-Plantillas_y_Checklists/TEMPLATE-REQ]] (Requerimientos)
	- [x] [[TEMPLATE-CP]] (Casos de Prueba)
- **Checklists de Verificacion**:
	- [x] [[01-Proyecto/00-Meta/99-Plantillas_y_Checklists/CL-02_Verificacion_Requerimientos]]
- **Gobernanza**:
	- [x] [[00-PROC-00_Gobernanza_Vault]]

---

## 3. Hoja de Ruta Inmediata (Sprint Final)
> Asignacion de prioridades antes de la revision. Objetivos; eliminar agujetos tecnicos y verificar la escritura de los documentos.

1. **Sistematizar Procesos 04, 06 y 08**: Samuel debe documentar la estrategia de codificacion, mantenimiento y despliegue.
2. **Cerrar Trazabilidad (RTM)**: Carlos debe vincular REQ -> Control para asegurar que no hay huecos en la auditoria.
3. **Ejecutar Casos de Prueba (CP)**: Axel debe capturar evidencia real del prototipo en la carpeta `05-Pruebas`.

---

## Herramientas y Recursos
> Consolida los enlaces externos y las referencias bibliograficas que fundamentan el proyecto

### Repositorio y Desarrollo
- **GitHub**: [Marcos2](https://github.com/Bigsami89/Marcos2)
- **Lenguaje**: Python (OpenCV, Pillow, Flask)
- **Documentacion**: Obsidian (Vault SQA)

### Referencias del Marco Teorico (Assignments_V2)
- [[PLAN-FINAL_SQA]] — Plan de trabajo detallado por integrante.
- [[OBS26/02-Estudios/Universidad/Aseguramiento de la Calidad de Software 1.0/Assignments/03 - Reportes/20- verificación de las fases de diseño lógico, físico, de unidad de programa y de la fase de codificación]] — Base para Verificacion (V&V).
- [[03-Convenciones_y_Tags]] — Reglas de nomenclatura y jerarquia.

---
*Ultima actualizacion: 2026-05-12 — Axel Morales (SQA Lead)*
