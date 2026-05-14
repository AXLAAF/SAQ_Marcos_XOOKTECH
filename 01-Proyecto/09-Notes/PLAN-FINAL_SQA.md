---
id: NOTE-PLAN-FINAL
titulo: Plan de Trabajo de SQA - Entrega Final Proyecto
version: "3.0"
estado: Activo
tipo: Plan_Trabajo
fecha_creacion: 2026-05-12
responsables: [Analista Técnico, Líder SQA, Analista SQA]
referencias:
  - "Galin - Software Quality Assurance"
  - "Nuevo Ciclo de Vida: 8 Procesos (Incluye Despliegue)"
tags:
  - notes/plan
  - sqa/entrega-final
---

# Plan de Trabajo: Finalizacion del Plan de Aseguramiento Completo (V3)

> **Objetivo**: Consolidar el SGC del proyecto "Visualizador de Marcos" bajo la estructura de 8 fases, con responsabilidades claras por integrante.

## 1. Distribucion de Responsabilidades (Fuerza de Tarea)

### Integrante 1: Líder SQA (Implementacion y Operaciones)
*   **Fase 04-Codificacion**: Implementacion tecnica y modulos Python (COD).
*   **Fase 06-Mantenimiento**: Estrategia de soporte y evolucion post-entrega (MNT).
*   **Fase 08-Despliegue**: Puesta en produccion, manuales de usuario y entrega final (DESP).

### Integrante 2: Analista SQA (Analisis y Calidad)
*   **Fase 02-Requisitos**: Definicion de REQ-01 a REQ-10 y criterios de aceptacion.
*   **Fase 07-Control**: SCM, Change Requests (CR), Inspecciones y Metricas de Calidad (CTRL).
*   **Entregable**: Reporte de Inspeccion Formal de Requerimientos.

### Integrante 3: Analista Técnico (Estrategia y Verificacion)
*   **Fase 00-Meta**: Gobernanza, convenciones, tags y auditoria del Vault.
*   **Fase 01-Linea_Base**: Contexto del proyecto y acuerdos con "Enmarcame".
*   **Fase 03-Diseño**: Arquitectura del sistema, flujos y diseño de componentes (DIS).
*   **Fase 05-Pruebas**: Plan Maestro de Pruebas y ejecucion de Casos de Prueba (CP).

---

## 2. Nueva Estructura del Ciclo de Vida (SGC)

1.  **00-Meta**: Gobernanza y Estandares.
2.  **01-Linea_Base**: Contexto y Acuerdos.
3.  **02-Requisitos**: Especificacion (REQ).
4.  **03-Diseño**: Arquitectura (DIS).
5.  **04-Codificacion**: Implementacion (COD).
6.  **05-Pruebas**: Verificacion y Validacion (CP).
7.  **06-Mantenimiento**: Soporte (MNT).
8.  **07-Control**: Gestion de Calidad (CTRL).
9.  **08-Despliegue**: Entrega Final (DESP).

---

## 3. Acciones Inmediatas (Checklist de Cumplimiento)

- [ ] **Tarea 01**: (Analista Técnico) Revisar que `05-Pruebas` tenga evidencia real del prototipo.
- [ ] **Tarea 02**: (Carlos) Consolidar los resumenes de sesiones de clase en `07-Control`.
- [ ] **Tarea 03**: (Líder SQA) Crear el primer borrador de `08-Despliegue/DESP-01_Guia_Instalacion.md`.
- [ ] **Tarea 04**: (Equipo) Humanizar los documentos inyectando por ia.

---

## 4. Cronograma de Emergencia

| Fecha | Hito | Estado |
| :--- | :--- | :---: |
| 12-May | Reestructuracion Final de Roles y Fases | 🟢 |
| 13-May | Cierre de Pruebas y Codificacion | 🟡 |
| 14-May | Auditoria de Calidad y Entrega Presencial | ⚪ |
